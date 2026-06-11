# Better Export PDF Auto Save

Better Export PDF Auto Save is an Obsidian plugin forked from [`l1xnan/obsidian-better-export-pdf`](https://github.com/l1xnan/obsidian-better-export-pdf).

This fork preserves the original Better Export PDF feature set and adds an optional auto-save mode that exports the current Markdown file to a PDF file in the same folder as the source note.

## Author

This modified plugin is maintained by **Myeongju Cha**.

## Original Project

This project is based on:

- Original plugin: [Obsidian Better Export PDF](https://github.com/l1xnan/obsidian-better-export-pdf)
- Original author: `l1xnan`
- Original license: MIT

The original license file is kept in this repository.

## Added Feature

This fork adds a plugin setting:

```text
Auto-save next to markdown
```

When this option is enabled, the normal Better Export PDF command keeps the original export dialog and settings flow, but skips the final save-location dialog for single-note exports.

The PDF is saved next to the source Markdown file.

Example:

```text
Research/CP/ankle_assistance.md
Research/CP/ankle_assistance.pdf
```

If the timestamp option is enabled:

```text
Research/CP/ankle_assistance.md
Research/CP/ankle_assistance-1712345678901.pdf
```

When `Auto-save next to markdown` is disabled, the plugin behaves like the original Better Export PDF and asks for the output path.

## Preserved Better Export PDF Features

This fork aims to keep the original Better Export PDF behavior, including:

- Export preview
- PDF outline/bookmark generation
- Header and footer templates
- Page size and margin settings
- CSS snippet support
- PDF metadata from front matter
- Internal link handling
- Multi-file and folder export features from the original plugin

## Manual Installation

Build the plugin and copy the generated files into your vault:

```bash
npm install
node esbuild.config.mjs production
```

Then copy these files:

```text
main.js
manifest.json
styles.css
```

to:

```text
<VaultFolder>/.obsidian/plugins/better-export-pdf-auto-save/
```

Reload Obsidian and enable `Better Export PDF Auto Save` in Community Plugins.

## Development

Install dependencies:

```bash
npm install
```

Run development build/watch:

```bash
npm run dev
```

Create a production bundle:

```bash
node esbuild.config.mjs production
```

Note: the upstream project currently has TypeScript checking issues with the installed dependency versions, so `npm run build` may fail at the type-check step even when the esbuild bundle succeeds.

## GitHub Repository Contents

Do not commit generated or local files such as:

- `node_modules/`
- `main.js`
- `data.json`
- `*.map`

The compiled `main.js` should be attached to GitHub Releases together with `manifest.json` and `styles.css`.

## License

MIT License.

This fork keeps the original MIT license from `l1xnan/obsidian-better-export-pdf`.
