# AGENTS.md

Guidance for AI agents working in the Pulsar repository. Human contributors should read `CONTRIBUTING.md`; this file adds rules specific to automated agents.

## What Pulsar is

Pulsar is a community-led, hackable text editor — a maintained fork of Atom. It is an Electron desktop application written primarily in JavaScript (with some CoffeeScript and native modules). Core editor code lives in `src/`; bundled first-party packages live in `packages/` (a workspace); tests live in `spec/` and inside each package.

## Repository layout

- `src/` — core editor and main-process code (`src/main-process/main.js` is the entry point).
- `packages/` — bundled packages, each a workspace member with its own `package.json`.
- `spec/` — core editor test suites (Jasmine).
- `script/` — build, packaging, and release tooling.
- `docs/` — contributor and architecture docs. Start with `docs/README.md`, `docs/Building.md`, `docs/dev/testing.md`, and `docs/architecture/`.
- `ppm/` — the Pulsar Package Manager (submodule-style, built separately).
- `resources/`, `static/`, `menus/`, `keymaps/`, `locales/` — app resources.

## Toolchain

- **Node.js**: pinned to `20.16.0` (see `.nvmrc`); `package.json` requires `>=20.16.0`. Note: `docs/Building.md` mentions older Node versions and is out of date — follow `.nvmrc`.
- **Package manager**: use `yarn`. `npm` is not supported. `.yarnrc` sets `ignore-engines true` for native-module compatibility.
- **Runtime**: Electron `30.5.1`.

## Setup / build / run

```shell
yarn install      # install dependencies
yarn build        # electron-rebuild native modules
yarn build:apm    # build the Pulsar Package Manager (ppm)
yarn start        # launch the editor (accepts the same args as the final binary)
```

## Testing

Run tests the same way you run the binary — by passing `--test`:

```shell
yarn start --test spec        # run the core editor test suite
yarn test:editor              # alias for the core suite (spec/)
yarn start --test <path>      # run a specific test file or package suite
```

- Core tests use Jasmine (`runners/jasmine2-test-runner`). Some packages specify their own runner via `atomTestRunner` in their `package.json` (e.g. mocha).
- Tests boot a real Electron window, so they need a display. In headless environments use a virtual framebuffer (e.g. `xvfb-run`).
- Add or update tests for any behavior change and run the relevant suite before claiming a change works.

## Linting / style

- ESLint config is `.eslintrc.js`. Match surrounding style:
  - No space before named function parens; space before anonymous/async-arrow parens.
  - Prefix intentionally-unused vars/args with `_`.
  - `atom` is a global.
- Match the existing conventions of the file you are editing (indentation, quoting, comment density). Do not reformat unrelated code.

## Agent rules

**These rules are mandatory for AI agents.**

1. **Do not author commits.** Agents must not run `git commit`. Leave changes in the working tree for a human to review and commit. Do not add `Co-Authored-By` or otherwise attribute commits to an AI on this repo.
2. **Do not push upstream.** Agents must not run `git push`, and must not push to any remote or branch of this repository. No `gh pr create`, no branch publishing, no release/tag pushes.
3. **No destructive git.** Do not run `git reset --hard`, `git rebase`, `git clean -f`, force-pushes, or history rewrites unless a human explicitly asks in the same session.
4. **Human owns integration.** Propose diffs and explain them; a human decides what lands. Surface uncertainty instead of guessing.
5. **Stay in scope.** Change only what the task requires. Don't touch `yarn.lock`, dependency versions, or `packages/` members unrelated to the task without being asked.
6. **Verify before claiming done.** Run the relevant tests/lint and report the actual output. If a step was skipped or failed, say so.
7. **Respect security and licensing.** Don't add dependencies or code that change the license posture. Report anything sensitive rather than acting on it. See `SECURITY.md` and `CODE_OF_CONDUCT.md`.

## References

- `CONTRIBUTING.md` — full contributor guide.
- `docs/Building.md` — build instructions (cross-check Node version against `.nvmrc`).
- `docs/dev/testing.md` — testing details.
- `docs/architecture/` — how the editor is structured.
