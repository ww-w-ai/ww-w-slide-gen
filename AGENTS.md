# ww-w Slide Gen source rules

Read CUSTOMIZE.md and docs/design-system.md before editing slides.
Follow docs/comparison-workflow.md for every designer-to-HTML deck.
Preserve alternating original/published comparison slides. Build a separate final clone with npm run build:final.
Never delete originals from the comparison source. Remove reference entries only from the final clone.
Do not distort font proportions. Anchor annotation lines to their matching evidence.
Use deck.config.json for page order and project metadata.
Use html/theme.css for brand tokens.
Use html/components.css for shared components.
Use html/pages.css for page-specific composition.
Keep slide content in html/pages/. Do not nest section elements.
Keep the fixed 1920x1080 canvas and #track > .slide contract.
Preserve native editable text. Keep original screenshots separate from generated artwork.
Read live edits before reloading or rebuilding. Downloads do not update source files.
Run npm test and inspect the rendered deck after layout changes.
Open html/deck.html in a browser to verify. If the browser blocks file:// access, serve the folder locally, e.g. `python3 -m http.server 8765 --bind 127.0.0.1 --directory /absolute/path/my-deck`, and open http://127.0.0.1:8765/html/deck.html. Reuse a preview server already running for this project instead of starting a new one.
Codex and Claude Code use the same source and build commands.
Codex uses its built-in image_gen. Claude Code dispatches the same work to Codex non-interactively when the Codex CLI is installed, e.g. `codex exec --skip-git-repo-check -C /absolute/path/my-deck -s workspace-write "<instruction: use built-in image_gen, full prompt, target path>"`, one call per asset, then verifies the file exists. If Codex is not available, use whatever image tool the host provides. The build itself never calls an image API.
Keep AGENTS.md and CLAUDE.md identical when changing these instructions.
