# Code Review — Improvements

**Scope:** Core editor source in `src/` (~61k LOC across 121 files). This is a
sampling review of representative core modules, not an exhaustive audit of every
file or the bundled `packages/`. No working-tree diff existed to review (only
`yarn.lock` deletion), so findings target the codebase as it stands.

**Method:** Five axes — correctness, readability, architecture, security,
performance. Findings are categorized **Critical / Important / Suggestion** with
`file:line` references. No code was changed.

---

## Critical

### C1. `windowShouldOpenFile` crashes on nonexistent path
`src/core-uri-handlers.js:22-30`

```js
const stat = fs.statSyncNoException(filename);
return win =>
  win.containsLocation({
    pathToOpen: filename,
    exists: Boolean(stat),
    isFile: stat.isFile(),        // TypeError when stat === false
    isDirectory: stat.isDirectory()
  });
```

`statSyncNoException` returns `false` when the file does not exist. `exists:
Boolean(stat)` handles that, but `stat.isFile()` / `stat.isDirectory()` are then
called on `false`, throwing `TypeError: stat.isFile is not a function`. A
`pulsar://open/file?filename=<missing path>` URI crashes the handler.

**Fix:** guard — `isFile: stat && stat.isFile()`, `isDirectory: stat &&
stat.isDirectory()`, or return early when `!stat`.

---

## Important

### I1. URI handler opens arbitrary local paths — no validation (security)
`src/core-uri-handlers.js:10-18`

`openFile` passes `query.filename` straight to `atom.workspace.open` with no
validation or user confirmation. External `pulsar://open/file?filename=...`
links (OS protocol handler) can point at any local path. Editors intentionally
open files, but a protocol handler is a remote-triggerable surface. Consider:
scope/allowlist checks, or a confirmation prompt for URIs originating outside the
app. At minimum, document the trust boundary.

### I2. `doLocalesMatch` falls through to `undefined`
`src/i18n.js:85-106`

When `want.endsWith("-*")` and every subtag matches without hitting a wildcard,
the `for` loop completes and the function returns `undefined` instead of `true`.
Return value is inconsistent (`true` / `false` / `undefined`). Callers treat it
as boolean, so an exact wildcard-prefixed match may be silently dropped.

**Fix:** add explicit `return true;` after the loop.

### I3. `IntlMessageFormat` recompiled on every translate call (performance)
`src/i18n.js:262`

```js
const msg = new IntlMessageFormat(stringLocales[bestLocale], bestLocale, undefined, { formatters: this.formatters });
```

`translate()` is a hot path (called per UI string). The `formatters` are
memoized, but the message *compile* (`new IntlMessageFormat(...)`) is not, so
every call reparses the ICU pattern. Memoize the compiled `IntlMessageFormat`
keyed on `(bestLocale, pattern)` — mirrors the existing `formatters` memoize
approach at lines 116-126.

### I4. Preload loads all locales into memory; pruning never implemented
`src/i18n.js:129-170`

`preload()` loads *every* available locale string (comment: "we load all
available locales, and MUST prune them later"), but no prune step exists. Memory
holds unused translations for the whole session. Acknowledged tech debt — track
and implement the prune task, or scope preload to the fallback locale + `en`.

---

## Suggestions

### S1. `console.*` used as logging (116 occurrences in `src/`)
`grep "console\.(log|warn|error)" src/*.js` → 116 hits (e.g.
`src/i18n.js:267`). No structured/leveled logging; noise in production, hard to
silence or route. Consider a thin logging wrapper with levels.

### S2. Loose equality `==` / `!=` (176 occurrences)
E.g. `src/i18n.js:86,94,97`, `src/ui.js:359,493`. Many are intentional
`== null` idioms, but the type-coercing cases (`wantArr[i] == "*"`) are risk-prone.
Prefer `===` except for the deliberate null-check idiom. An ESLint `eqeqeq`
rule (`null: "ignore"`) would enforce this — `eslint` is already a devDependency
(`package.json:306`).

### S3. `var` still in use (127 occurrences)
Legacy `var` scattered through `src/`. Migrate to `const`/`let` for block scoping
and to avoid hoisting surprises. Mechanical; low risk with lint backing.

### S4. Synchronous fs on startup paths (35 occurrences)
E.g. `src/file-system-blob-store.js:36-37,50-54`, `src/i18n.js:153-159`,
`src/config-file.js:69`. Some are legitimately startup-only (blob store, config
bootstrap), but blocking I/O on the main process stalls the UI. Audit which run
after the window is interactive and move those to async.

### S5. `FileSystemBlobStore` — no write to temp + rename
`src/file-system-blob-store.js:53-54`

`save()` writes `BLOB` then `MAP` in place. A crash between the two writes leaves
the map inconsistent with the blob. The `LOCK` file guards concurrent writers but
not torn writes. Consider write-to-temp + atomic `rename`.

### S6. High-churn TODO/FIXME backlog (46 in `src/`)
Several flag known-convoluted logic: `src/grammar-registry.js:287,494`,
`src/scope-resolver.js:5` (duplicated utility functions across files),
`src/context-menu-manager.js:52` (private-data coupling to color-picker package).
Worth tracking as issues rather than inline debt. Notably `scope-resolver.js:5`
documents duplicated utilities — a real DRY/architecture cleanup.

---

## Notes / Non-findings

- Error handling in `file-system-blob-store.js:35-40` (reset on corrupt cache)
  and `i18n.js:261-271` (fall back to keyPath) is sound — good defensive design.
- `getDump()` (`file-system-blob-store.js:105-130`) correctly dedupes keys
  already dumped from memory before pulling from storage.

## Suggested next steps
1. Fix **C1** (one-line guard, crash fix).
2. Add ESLint `eqeqeq` + `no-var` (autofixable) to lock in S2/S3 going forward.
3. Memoize I18n message compile (**I3**) — cheap, measurable win on a hot path.
4. File issues for **I4**, **S5**, **S6** as tracked debt.
