# AGENTS.md

## What This Is

A zero-dependency, client-side-only translation tool for localization files (JSON, Android XML, YAML, Properties, CSV, INI, PO). The entire app is a single HTML file with inline JS — no build step, no server, no Node.js required.

## Architecture

- **`index.html`** — the entire application (HTML + Tailwind CSS via CDN + inline `<script>` with all logic). This is the only source file that matters.
- **`tests.html`** — browser-based unit tests with a custom minimal test runner (no framework). Utility functions are duplicated here from `index.html`.
- **No separate JS/CSS files.** All code lives inside `<script>` tags in the HTML files.

## Running / Testing

- **Run**: Open `index.html` in a browser. No `npm start`, no dev server, no build.
- **Test**: Open `tests.html` in a browser. Tests auto-run on load. There is no CLI test command.
- **No lint, typecheck, or formatter** is configured. There is no `package.json` at the project root.

## Conventions

- **RTL/Persian UI**: The HTML uses `dir="rtl"` and `lang="fa"`. Persian number conversion (`toPersianNumber`) is used throughout the UI. When modifying UI strings, keep the Persian context in mind.
- **Tailwind via CDN**: Styles use Tailwind utility classes loaded from `https://cdn.tailwindcss.com`. Do not look for a Tailwind config file — there isn't one.
- **Content Security Policy**: The `index.html` has a strict CSP. External scripts are limited to Tailwind CDN. If you add external resources, update the CSP `meta` tag or they will be blocked.
- **Prototype pollution protection**: `unflattenJSON` explicitly blocks `__proto__`, `constructor`, and `prototype` keys. Preserve this when modifying.

## Key Patterns

- All file format parsing (JSON, XML, YAML, Properties, CSV, INI, PO) is handled by `FormatHandlers` object (~line 918 in `index.html`) with `parse()` and `serialize()` methods per format.
- Data is stored in `localStorage`. There is optional AES-256-GCM encryption via Web Crypto API.
- `Ctrl+Enter` saves and jumps to the next untranslated field.
- Export reconstructs the original nested structure via `unflattenJSON` before serializing.

## Gotchas

- `tests.html` duplicates utility functions from `index.html` rather than importing them. If you change a core function in `index.html`, update the corresponding copy in `tests.html`.
- The project has `.flowbaby/` and `.kilo/` directories — these are agent/tool artifacts, not application code. They are gitignored.
- There is no `node_modules` at the project root. The `.kilo/` directory has its own, unrelated.
