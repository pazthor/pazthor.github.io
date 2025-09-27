# Repository Guidelines

## Project Structure & Module Organization
The repository hosts a Jekyll-powered GitHub Pages site. Keep page-level content in the project root or a `pages/` folder, blog posts in `_posts/` using `YYYY-MM-DD-title.md`, shared templates in `_layouts/` and `_includes/`, and styles or images under `assets/`. Generated output belongs only in `_site/`, which remains untracked per `.gitignore`.

## Build, Test, and Development Commands
- `bundle install` — install Ruby gems declared in `Gemfile` before first run.
- `bundle exec jekyll serve --livereload` — start the local server at `http://127.0.0.1:4000` for iterative development.
- `bundle exec jekyll build` — produce a production build in `_site/`; use this to verify Pages deployments.
- `bundle exec htmlproofer ./_site` — optional link and HTML validation prior to merging.
- `docker compose up hugo` — launch the containerized dev server at http://localhost:1313 using the bundled compose file.

## Coding Style & Naming Conventions
Use Markdown (CommonMark) for content pages and Liquid for templating. Indent HTML/Liquid with two spaces, keep YAML front matter compact, and prefer descriptive section headings. Include alt text for images, and store reusable includes with kebab-case filenames (e.g., `_includes/site-footer.html`). Posts follow the standard dated filename plus a concise, hyphenated slug. Keep CSS modular inside `assets/css/` and avoid inlining styles.

## Testing Guidelines
Always run `bundle exec jekyll build` before pushing to catch Liquid or front matter errors. When adding navigation, verify links via `htmlproofer` or the browser inspector. For data-driven pages, add sanity checks in `_data/` by validating keys and running a local build with `JEKYLL_ENV=production` to mirror deployment behavior.

## Commit & Pull Request Guidelines
Recent commits use brief, imperative statements (e.g., "delete old file blogs"); continue this style but add context when touching multiple areas. Reference related issues in the body, summarize user-facing changes, and include before/after screenshots for visual tweaks. For pull requests, list build or validation commands executed, note any content migrations, and flag follow-up tasks so maintainers can deploy confidently.

## Deployment & Maintenance
GitHub Pages builds directly from `main`, so merge-ready branches must pass local builds. Update dependencies periodically with `bundle update` and document any version bumps in the PR. After merge, confirm the live site renders as expected and roll back promptly if regressions appear.
