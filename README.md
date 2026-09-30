# Your next deck starts here.

English | [한국어](README.ko.md)

Great slides should not mean rebuilding the editor every time. ww-w Slide Gen gives you a copyable HTML presentation engine, editable text, and a design system you can make your own.

Copy the folder. Set your brand. Write your story.

## Start

Requires Node.js 20 or later. No package installation is needed.

```sh
cp -R /absolute/path/ww-w-slide-gen /absolute/path/my-deck
node /absolute/path/my-deck/scripts/build-deck.js
open /absolute/path/my-deck/html/deck.html      # macOS
start /absolute/path/my-deck/html/deck.html     # Windows
xdg-open /absolute/path/my-deck/html/deck.html  # Linux
```

The destination should be a new directory. The generated deck includes local images and fonts in one HTML file. Use any desktop browser to view it. Print from the browser to save a PDF.

## Make it yours

| Edit | Purpose |
|---|---|
| `deck.config.json` | Title, footer, export filename, page order, storage namespace |
| `html/theme.css` | Brand colors, typography, spacing, surfaces |
| `html/components.css` | Shared title, card, screenshot, and footer components |
| `html/pages.css` | Page-specific layouts |
| `html/pages/*.html` | Editable slide content |
| `templates/blank-slide.html` | Copyable starting point for a new page |
| `assets/` | Fonts, original screenshots, and text-free artwork |

The included gallery covers a cover, three-column content, screenshot evidence, process, comparison, and artwork with editable text.

Try a second visual direction by adding `themes/cobalt.css` immediately after `theme.css` in the stylesheet list. It changes the palette, margins, and corners while using the same components and engine.

Read [CUSTOMIZE.md](CUSTOMIZE.md) for the step-by-step walkthrough, [the design-system guide](docs/design-system-guide.md) to define your brand, and [the CSS guide](docs/css-customization.md) to implement it. The [default design system](docs/design-system.md) is a working example you can replace.

## Present and edit

Use **← / →** to navigate, **E** to edit, and double-click text to change it. **M** reorders pages. **?** opens the shortcut guide. **Cmd/Ctrl+S** downloads the live edited deck; it does not overwrite your source files. Save browser edits before rebuilding. Source files remain the authority for the next build.

**Cmd/Ctrl+P** prints the current slide. For a whole-deck PDF, add `print-all` to the body in browser developer tools (`document.body.classList.add('print-all')`) before printing. Print at the CSS page size, with background graphics enabled and browser headers/footers disabled.

Text removal can use the image-generation workflow. The optional legacy AI eraser model and runtime are not bundled; see [the image workflow](docs/image-workflow.md).

## Check a copy

```sh
npm --prefix /absolute/path/my-deck test
```

Node checks cover assembly, asset closure, runtime syntax, and relocated builds. Browser layout, editing, downloads, and PDF appearance still require a browser check. This template targets trusted local HTML sources, not untrusted uploads.

Code (scripts, CSS, HTML) is [MIT](LICENSE); documentation prose is [CC BY 4.0](LICENSE-CONTENT.md). Bundled Pretendard fonts retain their SIL OFL license. See [third-party notices](THIRD-PARTY-NOTICES.md).
Official workflow: [Compare originals, then create a separate final deck](docs/comparison-workflow.md). Preserve the comparison deck. Run `npm run build:final` to create a published-only clone.
