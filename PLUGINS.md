# Bundled Packages (Add-ons / Plugins)

Every package shipped by default with this Pulsar build. Pulsar's package
model is inherited from Atom: bundled "core packages" provide most editor
features, themes, and language grammars. Users install additional community
packages from the Pulsar package registry.

**Total default packages:** 95 (93 vendored in `packages/`, 2 fetched from external repos at build time).

Most vendored packages live inside the Pulsar monorepo
(`github.com/pulsar-edit/pulsar`) under `packages/<name>`. Packages whose
`repository` points elsewhere have their own standalone repo (noted below).

Generated from each package's `package.json`.

---

## Core Features (46)

| Package | Version | Repository | Description |
|---|---|---|---|
| `about` | 1.9.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | View useful information about your Pulsar installation. |
| `archive-view` | 0.66.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | View the files and folders inside archive files |
| `autocomplete-atom-api` | 0.10.7 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Pulsar API autocompletions |
| `autocomplete-css` | 0.17.5 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | CSS property name and value autocompletions |
| `autocomplete-html` | 0.8.9 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | HTML element and attribute autocompletions |
| `autocomplete-plus` | 2.42.6 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Display possible completions in the editor while typing |
| `autocomplete-snippets` | 1.12.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Adds snippets to autocomplete+ suggestions |
| `autoflow` | 0.29.4 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Format the current selection to have lines no longer than 80 characters. This packages uses the config value of `editor.preferredLineLength` when set. |
| `autosave` | 0.24.6 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Save editors when they lose focus or are closed |
| `background-tips` | 0.28.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Displays tips about Pulsar in the background when there are no editors open. |
| `bookmarks` | 0.46.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Can mark lines, then jump back to them |
| `bracket-matcher` | 0.92.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Highlight the matching bracket for the `(){}[]` character under the cursor. Move the cursor to the matching bracket with `ctrl-m`. |
| `command-palette` | 0.43.5 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Find and run available commands using `cmd-shift-p` (macOS) or `ctrl-shift-p` (Linux/Windows). |
| `dalek` | 0.2.2 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | EXTERMINATEs built-in packages installed in ~/.pulsar/packages |
| `deprecation-cop` | 0.56.9 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Shows a list of deprecated calls |
| `dev-live-reload` | 0.48.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Live reload Pulsar themes and packages. |
| `encoding-selector` | 0.23.9 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Select the encoding to use for the current editor with `ctrl-shift-U`. |
| `find-and-replace` | 0.219.8 | [pulsar-edit/find-and-replace](https://github.com/pulsar-edit/find-and-replace) | Find and replace within buffers and across the project. |
| `fuzzy-finder` | 1.14.3 | [pulsar-edit/fuzzy-finder](https://github.com/pulsar-edit/fuzzy-finder) | Open an editor to a file in the project with `cmd-t`. |
| `git-diff` | 1.3.9 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Marks lines in the editor gutter that have been added, edited, or deleted since the last commit. |
| `github` | v0.37.0 | [pulsar-edit/github](https://github.com/pulsar-edit/github) | Git and GitHub integration (staging, commits, PRs). |
| `go-to-line` | 0.33.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Jump to a specific editor line number with `ctrl-g`. |
| `grammar-selector` | 0.50.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Select the grammar to use for the current editor with `ctrl-shift-L`. |
| `image-view` | 0.64.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Open images in an editor |
| `incompatible-packages` | 0.27.3 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Show incompatible packages |
| `keybinding-resolver` | 0.39.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Show what commands a keybinding resolves to |
| `line-ending-selector` | 0.7.7 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Select the line ending to use for the current editor. |
| `link` | 0.31.6 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Opens http(s) links under the cursor |
| `markdown-preview` | 0.160.2 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Open a rendered version of the Markdown in the current editor with `ctrl-shift-m`. |
| `notifications` | 0.73.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | A tidy way to display Pulsar notifications. |
| `open-on-github` | 1.3.2 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | View the active file on github.com |
| `package-generator` | 1.3.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Generates and opens a new sample package, language, or syntax theme. |
| `pulsar-updater` | 1.0.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Detect Pulsar updates on Launch. |
| `settings-view` | 0.261.11 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Edit config settings, install packages, and change themes |
| `snippets` | 1.8.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Expand snippets matching the current prefix with `tab`. |
| `spell-check` | 0.77.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Highlights misspelled words and shows possible corrections. |
| `status-bar` | 1.8.17 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Display information about the current editor such as cursor position, file path, grammar, current branch, ahead/behind commits counts, and line diff count. |
| `styleguide` | 0.49.12 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | A visual styleguide of the Pulsars's UI components. |
| `tabs` | 0.110.2 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Display a selectable tab for each editor open. |
| `terminal` | v0.3.2 | [pulsar-edit/terminal](https://github.com/pulsar-edit/terminal) | Integrated terminal. |
| `timecop` | 0.36.2 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Displays information about where time is spent while Pulsar loads. |
| `tree-view` | 0.229.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Explore and open files in the current project. |
| `update-package-dependencies` | 0.13.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Runs `apm install` for the current project |
| `welcome` | 0.36.9 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Welcome users to Pulsar with useful information |
| `whitespace` | 0.37.8 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Strips trailing whitespace and adds a trailing newline when an editor is saved. |
| `wrap-guide` | 0.41.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Displays a vertical line at the 80th character in the editor. This packages uses the config value of `editor.preferredLineLength` when set. |

## Language Grammars (34)

| Package | Version | Repository | Description |
|---|---|---|---|
| `language-c` | 0.60.20 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Atom language support for C/C++ |
| `language-clojure` | 0.22.8 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Clojure language support in Atom |
| `language-coffee-script` | 0.50.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | CoffeeScript language support in Atom |
| `language-csharp` | 1.1.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | C# language support for Atom |
| `language-css` | 0.45.4 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | CSS support in Atom |
| `language-gfm` | 0.90.8 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Syntax highlighting and snippets for GitHub Flavored Markdown (GFM). |
| `language-git` | 0.19.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Git editing support in Atom |
| `language-go` | 0.47.3 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Go language support in Atom |
| `language-html` | 0.53.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | HTML language support in Atom |
| `language-hyperlink` | 0.17.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Hyperlink colorization in Atom |
| `language-java` | 0.32.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Java language support in Atom |
| `language-javascript` | 0.134.2 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | JavaScript language support in Atom |
| `language-json` | 1.0.5 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | JSON language support in Atom |
| `language-less` | 0.34.3 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Less language support in Atom |
| `language-make` | 0.23.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Make language support in Atom |
| `language-mustache` | 0.14.5 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Mustache language support in Atom |
| `language-objective-c` | 0.16.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Objective-C language support in Atom |
| `language-perl` | 0.38.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Perl language support in Atom |
| `language-php` | 0.48.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | PHP language support in Atom |
| `language-property-list` | 0.9.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Property List support in Atom |
| `language-python` | 0.53.6 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Python language support in Atom |
| `language-ruby` | 0.73.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Ruby language support in Atom |
| `language-ruby-on-rails` | 0.25.3 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Ruby on Rails language support in Atom |
| `language-rust-bundled` | 0.1.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Rust support for Pulsar |
| `language-sass` | 0.62.2 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Sass/SCSS language support in Atom |
| `language-shellscript` | 0.28.2 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | ShellScript language support in Atom |
| `language-source` | 0.9.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Source code support in Atom |
| `language-sql` | 0.25.10 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | SQL language support in Atom |
| `language-text` | 0.7.4 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Plain text support in Atom |
| `language-todo` | 0.29.4 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | TODO/FIXME highlighting support in Atom |
| `language-toml` | 0.20.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Syntax highlighting for Tom's Obvious, Minimal Language (TOML). |
| `language-typescript` | 0.6.4 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | TypeScript language support in Atom |
| `language-xml` | 0.35.3 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | XML language support in Atom |
| `language-yaml` | 0.32.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | YAML language support in Atom |

## Themes & Syntax (12)

| Package | Version | Repository | Description |
|---|---|---|---|
| `atom-dark-syntax` | 0.29.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | A dark theme for syntax |
| `atom-dark-ui` | 0.53.3 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | A dark UI theme for Pulsar |
| `atom-light-syntax` | 0.29.1 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | A light syntax theme |
| `atom-light-ui` | 0.46.3 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | A light UI theme for Pulsar |
| `base16-tomorrow-dark-theme` | 1.6.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Base16 dark theme developed for Atom, repurposed for Pulsar |
| `base16-tomorrow-light-theme` | 1.6.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Base16 light theme developed for Atom, repurposed for Pulsar |
| `one-dark-syntax` | 1.8.4 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | A dark syntax theme |
| `one-dark-ui` | 1.12.5 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Pulsar One dark UI theme |
| `one-light-syntax` | 1.8.4 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | One light syntax theme developed for Atom, repurposed for Pulsar |
| `one-light-ui` | 1.12.5 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | One light UI theme developed for Atom, repurposed for Pulsar |
| `solarized-dark-syntax` | 1.3.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | A dark syntax theme using the solarized colors |
| `solarized-light-syntax` | 1.3.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | A light syntax theme using the solarized colors |

## Symbols (3)

| Package | Version | Repository | Description |
|---|---|---|---|
| `symbol-provider-ctags` | 1.0.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Provides symbols to symbols-view via ctags |
| `symbol-provider-tree-sitter` | 1.0.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Provides symbols to symbols-view based on tree-sitter queries |
| `symbols-view` | 1.0.0 | [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Jump to a function/method in the current editor or in the project. |

---

## External repositories referenced

Standalone repos (own version tags), pulled in as default packages or core libs:

| Repo | Role |
|---|---|
| [pulsar-edit/pulsar](https://github.com/pulsar-edit/pulsar) | Monorepo hosting most bundled packages under `packages/` |
| [pulsar-edit/find-and-replace](https://github.com/pulsar-edit/find-and-replace) | `find-and-replace` package (standalone repo) |
| [pulsar-edit/fuzzy-finder](https://github.com/pulsar-edit/fuzzy-finder) | `fuzzy-finder` package (standalone repo) |
| [pulsar-edit/github](https://github.com/pulsar-edit/github) | `github` package, fetched at build |
| [pulsar-edit/terminal](https://github.com/pulsar-edit/terminal) | `terminal` package, fetched at build |
| [pulsar-edit/ppm](https://github.com/pulsar-edit/ppm) | `ppm` — Pulsar package manager CLI (git submodule `ppm/`) |
| [pulsar-edit/second-mate](https://github.com/pulsar-edit/second-mate) | Grammar/tokenization library used by grammars |
| [pulsar-edit/less-cache](https://github.com/pulsar-edit/less-cache) | LESS compile cache |
| [pulsar-edit/document-register-element](https://github.com/pulsar-edit/document-register-element) | Custom-element polyfill |

## Getting more packages

- Registry: https://web.pulsar-edit.dev — browse/install community packages.
- CLI: `ppm install <package>` (bundled as `pulsar -p` / `ppm`).
- In-app: **Settings → Install** (the `settings-view` package).


---

# Third-Party (Community) Packages

Packages published to the Pulsar package registry by the community — **not**
bundled with Pulsar; installed on demand via `ppm install <name>` or
**Settings → Install**. The registry holds **~10,416** packages total; listed
below are the **top 100 by all-time download count** (the practical majority of
real-world usage). Browse the full set at https://web.pulsar-edit.dev.

Data from the Pulsar registry API (`api.pulsar-edit.dev`). ⭐ marks packages
currently featured by Pulsar.

| # | Package | Downloads | Repository | Description |
|---:|---|---:|---|---|
| 1 | `platformio-ide-terminal` | 17.5M | [platformio/platformio-atom-ide-terminal](https://github.com/platformio/platformio-atom-ide-terminal) | A terminal package for Atom, complete with themes, API and more for PlatformIO IDE. Fork of terminal-plus. |
| 2 | `linter` | 9.9M | [steelbrain/linter](https://github.com/steelbrain/linter) | A Base Linter with Cow Powers |
| 3 | `file-icons` | 9.7M | [file-icons/atom](https://github.com/file-icons/atom) | Assign file extension icons and colours for improved visual grepping |
| 4 | `atom-beautify` | 9.2M | [Glavin001/atom-beautify](https://github.com/Glavin001/atom-beautify) | Beautify HTML, CSS, JavaScript, PHP, Python, Ruby, Java, C, C++, C#, Objective-C, CoffeeScript, TypeScript, Coldfusion,  |
| 5 | `linter-ui-default` | 7.8M | [steelbrain/linter-ui-default](https://github.com/steelbrain/linter-ui-default) | Default UI for the Linter package |
| 6 | `minimap` | 7.6M | [atom-minimap/minimap](https://github.com/atom-minimap/minimap) | A preview of the full source code. |
| 7 | `busy-signal` | 5.6M | [steelbrain/busy-signal](https://github.com/steelbrain/busy-signal) | A package that provides an easy to use API to show your package is performing a task |
| 8 | `intentions` | 4.8M | [steelbrain/intentions](https://github.com/steelbrain/intentions) | Base package for showing intentions in Atom |
| 9 | `emmet` | 4.8M | [emmetio/emmet-atom](https://github.com/emmetio/emmet-atom) | Emmet – the essential tool for web developers |
| 10 | `script` | 4.4M | [atom-community/atom-script](https://github.com/atom-community/atom-script) | Run code in Atom! |
| 11 | `pigments` | 4.2M | [abe33/atom-pigments](https://github.com/abe33/atom-pigments) | A package to display colors in project and files. |
| 12 | `autocomplete-python` | 3.4M | [autocomplete-python/autocomplete-python](https://github.com/autocomplete-python/autocomplete-python) | Python completions for packages, variables, methods, functions, with their arguments. Powered by your choice of Jedi or  |
| 13 | `git-plus` | 2.9M | [akonwi/git-plus](https://github.com/akonwi/git-plus) | Do git things without the terminal |
| 14 | `highlight-selected` | 2.8M | [richrace/highlight-selected](https://github.com/richrace/highlight-selected) | Highlights the current word selected when double clicking |
| 15 | `tool-bar` | 2.6M | [atom-community/tool-bar](https://github.com/atom-community/tool-bar) | Package providing customisable tool bar |
| 16 | `hydrogen` | 2.6M | [nteract/hydrogen](https://github.com/nteract/hydrogen) | Run code interactively, inspect data, and plot. All the power of Jupyter kernels, inside your favorite text editor. |
| 17 | `atom-material-ui` | 2.5M | [atom-material/atom-material-ui](https://github.com/atom-material/atom-material-ui) | A dynamic UI theme for Atom that follows Google's Material Design Guidelines |
| 18 | `color-picker` | 2.5M | [thomaslindstrom/color-picker](https://github.com/thomaslindstrom/color-picker) | Right click or press CMD-SHIFT-C/CTRL-ALT-C to open it. |
| 19 | `linter-eslint` | 2.4M | [AtomLinter/linter-eslint](https://github.com/AtomLinter/linter-eslint) | Lint JavaScript on the fly, using ESLint (v7 or older) |
| 20 | `atom-html-preview` | 2.2M | [harmsk/atom-html-preview](https://github.com/harmsk/atom-html-preview) | A live preview tool for Atom Editor. |
| 21 | `language-babel` | 2.2M | [gandm/language-babel](https://github.com/gandm/language-babel) | JavaScript ES201x, React JSX, Flow and GraphQL Grammar. Babel Transpiler |
| 22 | `atom-ide-ui` | 2.0M | [facebook-atom/atom-ide-ui](https://github.com/facebook-atom/atom-ide-ui) | A collection of Atom UIs to support language services. |
| 23 | `atom-typescript` | 2.0M | [TypeStrong/atom-typescript](https://github.com/TypeStrong/atom-typescript) | The only TypeScript plugin you will ever need. |
| 24 | `japanese-menu` | 1.9M | [syon/atom-japanese-menu](https://github.com/syon/atom-japanese-menu) | メニューバーとコンテキストメニュー、設定画面を日本語化します。 |
| 25 | `atom-material-syntax` | 1.8M | [atom-material/atom-material-syntax](https://github.com/atom-material/atom-material-syntax) | A dark syntax theme for Atom that uses Google's Material Design color palette |
| 26 | `autoclose-html` | 1.7M | [mattberkowitz/autoclose-html](https://github.com/mattberkowitz/autoclose-html) | Automates closing of HTML Tags |
| 27 | `atom-ternjs` | 1.7M | [tststs/atom-ternjs](https://github.com/tststs/atom-ternjs) | JavaScript code intelligence for atom with tern. Adds support for ES5, ES6, ES7, ES8, Node.js and more. Extendable via p |
| 28 | `ide-python` | 1.6M | [atom-community/ide-python](https://github.com/atom-community/ide-python) | Python language support for Atom-IDE |
| 29 | `platformio-ide` | 1.5M | [platformio/platformio-atom-ide](https://github.com/platformio/platformio-atom-ide) | Official PlatformIO IDE for IoT, Arduino, ARM mbed, Espressif (ESP8266/ESP32), STM32, PIC32, nRF51/nRF52, FPGA, CMSIS, S |
| 30 | `teletype` | 1.5M | [atom/teletype](https://github.com/atom/teletype) | Share your workspace with team members and collaborate on code in real time |
| 31 | `atom-live-server` | 1.5M | [jas-chen/atom-live-server](https://github.com/jas-chen/atom-live-server) | Launch a http server with live reload capability. |
| 32 | `build` | 1.4M | [noseglid/atom-build](https://github.com/noseglid/atom-build) | Build your current project, directly from Atom |
| 33 | `language-ini` | 1.2M | [jacobbednarz/atom-language-ini](https://github.com/jacobbednarz/atom-language-ini) | Syntax support for ini files. |
| 34 | `linter-jshint` | 1.2M | [AtomLinter/linter-jshint](https://github.com/AtomLinter/linter-jshint) | Linter plugin for JavaScript, using jshint |
| 35 | `remote-ftp` | 1.2M | [icetee/remote-ftp](https://github.com/icetee/remote-ftp) | Enable browsing remote FTP/FTPS/SFTP just like the built-in Tree View. Requires a project. |
| 36 | `atom-python-run` | 1.2M | [foreshadow/atom-python-run](https://github.com/foreshadow/atom-python-run) | Run a python source file. |
| 37 | `project-manager` | 1.2M | [danielbrodin/atom-project-manager](https://github.com/danielbrodin/atom-project-manager) | Project Manager for easy access and switching between projects in Atom. |
| 38 | `autocomplete-clang` | 1.1M | [yasuyuky/autocomplete-clang](https://github.com/yasuyuky/autocomplete-clang) | autocomplete for C/C++/ObjC using clang |
| 39 | `atom-clock` ⭐ | 1.1M | [b3by/atom-clock](https://github.com/b3by/atom-clock) | Display a customizable clock in the status bar. |
| 40 | `terminal-plus` | 1.1M | [jeremyramin/terminal-plus](https://github.com/jeremyramin/terminal-plus) | A terminal package for Atom, complete with themes and more. |
| 41 | `hyperclick` | 1.0M | [facebook-atom/hyperclick](https://github.com/facebook-atom/hyperclick) | Pluggable text-clicking UI for Atom |
| 42 | `sublime-style-column-selection` | 1.0M | [bigfive/atom-sublime-select](https://github.com/bigfive/atom-sublime-select) | Enable Sublime style 'Column Selection'. Just hold 'alt' while you select, or select using your middle mouse button. Als |
| 43 | `split-diff` | 983k | [mupchrch/split-diff](https://github.com/mupchrch/split-diff) | A split pane diff tool. |
| 44 | `react` | 967k | [orktes/atom-react](https://github.com/orktes/atom-react) | React.js (JSX) language support, indentation, snippets, auto completion, reformatting |
| 45 | `autocomplete-paths` | 957k | [atom-community/autocomplete-paths](https://github.com/atom-community/autocomplete-paths) | Adds path autocompletion to autocomplete+ |
| 46 | `pretty-json` | 954k | [federomero/pretty-json](https://github.com/federomero/pretty-json) | Format JSON |
| 47 | `activate-power-mode` | 932k | [JoelBesada/activate-power-mode](https://github.com/JoelBesada/activate-power-mode) | Activate POWER MODE to write your code in style. |
| 48 | `monokai` | 930k | [kevinsawicki/monokai](https://github.com/kevinsawicki/monokai) | A monokai theme |
| 49 | `seti-ui` | 885k | [jesseweed/seti-ui](https://github.com/jesseweed/seti-ui) | A dark colored UI theme for Atom with custom file icons. |
| 50 | `markdown-preview-plus` | 885k | [atom-community/markdown-preview-plus](https://github.com/atom-community/markdown-preview-plus) | Markdown Preview + Community Features |
| 51 | `linter-gcc` | 866k | [AtomLinter/linter-gcc](https://github.com/AtomLinter/linter-gcc) | Lint C and C++ source files using gcc / g++ |
| 52 | `gpp-compiler` | 861k | [kriscross07/atom-gpp-compiler](https://github.com/kriscross07/atom-gpp-compiler) | Compile and run C and C++ within Atom |
| 53 | `vim-mode-plus` | 857k | [t9md/atom-vim-mode-plus](https://github.com/t9md/atom-vim-mode-plus) | vim-mode improved |
| 54 | `ink` | 852k | [JunoLab/atom-ink](https://github.com/JunoLab/atom-ink) | A toolkit for building IDEs in Atom |
| 55 | `go-plus` | 849k | [joefitzgerald/go-plus](https://github.com/joefitzgerald/go-plus) | Makes working with Go in Atom awesome. |
| 56 | `platformio-ide-debugger` | 845k | [platformio/platformio-atom-ide-debugger](https://github.com/platformio/platformio-atom-ide-debugger) | A debugging front-end for PlatformIO IDE |
| 57 | `atom-runner` | 844k | [lsegal/atom-runner](https://github.com/lsegal/atom-runner) | Runs scripts inside of Atom. |
| 58 | `language-ejs` | 830k | [darron/language-ejs](https://github.com/darron/language-ejs) | EJS support for Atom. |
| 59 | `markdown-writer` | 826k | [zhuochun/md-writer](https://github.com/zhuochun/md-writer) | Make Atom a better Markdown editor and an easier static blogging tool. |
| 60 | `prettier-atom` | 823k | [prettier/prettier-atom](https://github.com/prettier/prettier-atom) | Atom plugin for formatting JavaScript using prettier with (optional) prettier-eslint integration |
| 61 | `csslint` | 817k | [tcarlsen/atom-csslint](https://github.com/tcarlsen/atom-csslint) | CSSLint error reports for your Atom editor |
| 62 | `minimap-highlight-selected` | 805k | [atom-minimap/minimap-highlight-selected](https://github.com/atom-minimap/minimap-highlight-selected) | A minimap binding for the highlight-selected package |
| 63 | `docblockr` | 803k | [nikhilkalige/docblockr](https://github.com/nikhilkalige/docblockr) | A helper package for writing documentation |
| 64 | `autocomplete-plus` | 795k | [atom/autocomplete-plus](https://github.com/atom/autocomplete-plus) | Display possible completions in the editor while typing |
| 65 | `julia-client` | 778k | [JunoLab/atom-julia-client](https://github.com/JunoLab/atom-julia-client) | The core package of Juno, the Julia IDE |
| 66 | `sync-settings` | 767k | [atom-community/sync-settings](https://github.com/atom-community/sync-settings) | Synchronize package settings, keymap and installed packages |
| 67 | `merge-conflicts` | 764k | [smashwilson/merge-conflicts](https://github.com/smashwilson/merge-conflicts) | Resolve git conflicts within Atom |
| 68 | `linter-php` | 724k | [AtomLinter/linter-php](https://github.com/AtomLinter/linter-php) | Lint PHP on the fly, using php -l |
| 69 | `language-vue` | 711k | [hedefalk/atom-vue](https://github.com/hedefalk/atom-vue) | Vue component support in Pulsar |
| 70 | `linter-flake8` | 700k | [AtomLinter/linter-flake8](https://github.com/AtomLinter/linter-flake8) | Atom linter plugin for Python, using flake8 |
| 71 | `sort-lines` | 695k | [atom/sort-lines](https://github.com/atom/sort-lines) | Sorts your lines. Never gets tired. |
| 72 | `language-julia` | 693k | [JuliaEditorSupport/atom-language-julia](https://github.com/JuliaEditorSupport/atom-language-julia) | Julia language support for Atom. |
| 73 | `language-haskell` | 690k | [atom-haskell/language-haskell](https://github.com/atom-haskell/language-haskell) | Haskell language support in Atom |
| 74 | `linter-csslint` | 659k | [AtomLinter/linter-csslint](https://github.com/AtomLinter/linter-csslint) | Lint CSS on the fly, using csslint |
| 75 | `vim-mode` | 648k | [atom/vim-mode](https://github.com/atom/vim-mode) | Deprecated - please install vim-mode-plus instead |
| 76 | `latex` | 627k | [thomasjo/atom-latex](https://github.com/thomasjo/atom-latex) | Compile LaTeX documents from within Atom |
| 77 | `pdf-view` | 606k | [izuzak/atom-pdf-view](https://github.com/izuzak/atom-pdf-view) | Atom PDF viewer based on PDF.js |
| 78 | `editorconfig` | 599k | [sindresorhus/atom-editorconfig](https://github.com/sindresorhus/atom-editorconfig) | Helps developers maintain consistent coding styles between different editors |
| 79 | `autocomplete-modules` | 575k | [nkt/atom-autocomplete-modules](https://github.com/nkt/atom-autocomplete-modules) | Autocomplete for require/import statements |
| 80 | `todo-show` | 565k | [mrodalgaard/atom-todo-show](https://github.com/mrodalgaard/atom-todo-show) | Finds all the TODOs, FIXMEs, CHANGEDs, etc. in your project. |
| 81 | `atom-autocomplete-php` | 560k | [Peekmo/atom-autocomplete-php](https://github.com/Peekmo/atom-autocomplete-php) | Atom autocompletion plugin for PHP language |
| 82 | `language-latex` | 551k | [area/language-latex](https://github.com/area/language-latex) | Syntax highlighting for LaTeX for Atom |
| 83 | `simplified-chinese-menu` | 550k | [chinakids/atom-simplified-chinese-menu](https://github.com/chinakids/atom-simplified-chinese-menu) | Atom 的简体中文语言包，完整汉化，兼容所有已发布版本 Atom |
| 84 | `linter-htmlhint` | 549k | [AtomLinter/linter-htmlhint](https://github.com/AtomLinter/linter-htmlhint) | A plugin for Atom Linter providing an interface to HTMLHint. |
| 85 | `seti-syntax` | 542k | [jesseweed/seti-syntax](https://github.com/jesseweed/seti-syntax) | Seti Syntax - A subtle dark colored theme for Atom. |
| 86 | `atom-i18n` | 531k | [liuderchi/atom-i18n](https://github.com/liuderchi/atom-i18n) | Localize Atom for your locale. One i18n package for any language. Community-driven translation. |
| 87 | `python-tools` | 519k | [MichaelAquilina/python-tools](https://github.com/MichaelAquilina/python-tools) | Goto definition, show usages, refactor/rename and more for python files |
| 88 | `language-lua` | 516k | [FireZenk/language-lua](https://github.com/FireZenk/language-lua) | Add syntax highlighting and snippets to Lua files in Atom |
| 89 | `ftp-remote-edit` | 503k | [h3imdall/ftp-remote-edit](https://github.com/h3imdall/ftp-remote-edit) | Edit remotely files on your ftp/sftp(ssh) server without a project. All your connection information will be encrypted. |
| 90 | `uber-juno` | 495k | [JunoLab/uber-juno](https://github.com/JunoLab/uber-juno) | The official installer of Juno, the Julia IDE |
| 91 | `ide-php` | 494k | [atom/ide-php](https://github.com/atom/ide-php) | PHP language support for Atom-IDE |
| 92 | `latex-completions` | 479k | [JunoLab/atom-latex-completions](https://github.com/JunoLab/atom-latex-completions) | Easy input for unicode characters |
| 93 | `python-indent` | 464k | [DSpeckhals/python-indent](https://github.com/DSpeckhals/python-indent) | Python PEP8 auto-indentation |
| 94 | `find-and-replace` | 459k | [atom/find-and-replace](https://github.com/atom/find-and-replace) | Find and replace within buffers and across the project. |
| 95 | `go-debug` | 454k | [lloiser/go-debug](https://github.com/lloiser/go-debug) | go debugger using delve for atom |
| 96 | `settings-view` | 453k | [atom/settings-view](https://github.com/atom/settings-view) | Edit config settings, install packages, and change themes |
| 97 | `tree-view` | 446k | [atom/tree-view](https://github.com/atom/tree-view) | Explore and open files in the current project. |
| 98 | `markdown-preview` | 444k | [atom/markdown-preview](https://github.com/atom/markdown-preview) | Open a rendered version of the Markdown in the current editor with `ctrl-shift-m`. |
| 99 | `language-javascript` | 437k | [atom/language-javascript](https://github.com/atom/language-javascript) | JavaScript language support in Atom |
| 100 | `git-time-machine` | 436k | [littlebee/git-time-machine](https://github.com/littlebee/git-time-machine) | Visually interact with git commit history for a file |

## Featured by Pulsar

Curated highlights (may fall outside the top-100 download list):

`atom-clock`, `dracula-syntax`, `hey-pane`, `language-dart2`, `language-tiger`, `sb-atom-sonic-pi`, `tidalcycles`, `tidal-sharp`, `x-terminal-reloaded`

## Notes

- Download counts are cumulative (many inherited from the Atom era).
- A package appearing here is community-maintained; vet before installing.
- Full, sortable registry: https://web.pulsar-edit.dev — or `ppm search <term>`.

