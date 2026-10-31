# what-it-shows

Work for MEGA.dev S01E03. Support ticket #4471 merged 412 reports about wrong dates and marked
them known. They hold two problems; each has an issue in this repo (379 and 33 reports).

- `support-kb/`: the support desk's kb export, plus one new page,
  `src/routes/kb/incidents/4471-split/+page.svx`. The page is signed in its frontmatter.
- `analysis/count.mjs`: counts the reports by problem. Run `node analysis/count.mjs` from the
  repo root. `analysis/groups.json` is its output (report ids per problem).

- `rendered/4471-split.html`: the page as the desk sees it, prerendered from the `.svx` with
  the kb's own layout and components. The desk ref in its footer, `DR-G6BY-ZY24`, is derived
  from the page's `signature`.
- `render-config/`: the minimal build setup used to render it (the export ships no build files).
  Copy `src/` from `support-kb/`, add `vite.config.js` and `package.json`, then `npm install`
  svelte, @sveltejs/kit, @sveltejs/adapter-static, @sveltejs/vite-plugin-svelte, vite, mdsvex
  and run `vite build`.
