# Repository Guidelines

## Project Structure & Module Organization
This is a Hugo site targeted at GitHub Pages. Author content in `content/` (posts in `content/posts/`), companion data in `_data/` if needed, and archetypes in `archetypes/`. Site-wide settings live in `config.toml`. The `themes/` directory is populated on demand with `hugo-theme-console`; it is retrieved during local/dev workflows, so the repository only keeps configuration and content. Generated artifacts land in `public/` (ignored via `.gitignore`).

## Build, Test, and Development Commands
- `docker compose up hugo` — run the console-themed dev server at `http://localhost:1313` with live reload; first launch fetches the theme automatically.
- `hugo server` — alternative local preview if Hugo is installed natively (ensure `themes/hugo-theme-console/` exists by cloning the theme).
- `hugo --minify` — production build used by GitHub Actions.
- `npm run htmlproofer` — placeholder for optional static checks; replace with your preferred validation if added later.

## Coding Style & Naming Conventions
Write posts in Markdown with front matter in YAML. Keep filenames lowercase and hyphenated (e.g., `disable-laptop-monitor-omarchy.md`). Use Hugo shortcodes instead of raw HTML when practical, and limit inline styling so the theme controls presentation. Tag names and categories should use kebab-case for consistency with the console theme’s tag listing.

## Testing Guidelines
Before committing, run either `docker compose up hugo` or `hugo server` and confirm the console interface renders correctly, navigation works, and syntax highlighting matches expectations. For new shortcodes or partials, add minimal sample content and verify layout in multiple terminal color schemes if relevant. For deployment parity, execute `hugo --minify` locally to surface build errors that live reload might hide.

## Commit & Pull Request Guidelines
Keep commit messages imperative and scoped (e.g., “add containerized hugo workflow”). Mention significant content additions, configuration changes, or theme overrides in the body. Pull requests should summarize reader-facing changes, list local verification commands (include whether the Docker workflow was run), and link any related issues. Screenshot updates aren’t required unless you customize the theme’s visuals.

## Theme & Deployment Notes
GitHub Actions clones `hugo-theme-console` during each build (`.github/workflows/gh-pages.yml`). If you need to customize the theme, fork it and change the clone URL. Pages deploys from `main` via the workflow; verify results after merge by visiting `https://pazthor.github.io/` once the action completes.
