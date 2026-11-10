# site/

The static pages served at www.openpb.org. They are temporary: `plans/app-migration/` ends with deleting this folder.

- `public/` is the only folder that gets published.
- `public/index.html` is the teaser, styled with the Tailwind CLI. `src/input.css` compiles to `public/assets/css/main.css`. The output is generated, so edit the input.
- `public/about/` is the longer page about how OPEN works, linked from the teaser's "Learn more". It has its own plain `styles.css`, `rating-sketch.js` and `assets/`, and the Tailwind build skips it. The two pages have different design languages on purpose for now.
- `public/404.html` uses the teaser's styles.

## Commands

- `pnpm dev` rebuilds the CSS on change.
- `pnpm build` produces the minified CSS.

To view the pages, serve `public/` (the `teaser` entry in `.claude/launch.json` does this) and open `/` or `/about/`. Opening the HTML files directly breaks the `/about/` link.

## Deployment

Merging changes under `site/` to `main` deploys both pages to production. PRs run the build only.
