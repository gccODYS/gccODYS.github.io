# Codex Notes

## Procedure Notes
- Keep responses as concise as possible while communicating necessary information
- Assume user has basic familiarity with coding, but not in depth knowledge

## Context
- Hugo portfolio/resume site in `/Users/ogallagher27/my-portfolio`.
- Active theme: `paper` via `theme = 'paper'` in `hugo.toml`.
- Site-owned source files are small: `hugo.toml`, `content/posts/about.md`, `layouts/_default/baseof.html`, `archetypes/default.md`, and `static/pp.jpeg`.
- `public/` and `resources/` are generated Hugo output/cache.

## Hugo Notes
- Local Hugo: `v0.161.1+extended`.
- Project templates override theme templates at the same virtual path.
- Current project override: `layouts/_default/baseof.html`, copied from Paper with avatar URL handling adjusted for root-relative paths.
- Hugo warns that `.Site.LanguageCode` is deprecated; use `.Site.Language.Locale`.

## Current Site State
- `hugo build` succeeds.
- `content/posts/about.md` contains front matter only, so the About page body is empty.
- Homepage profile uses `[params]` in `hugo.toml`: name, bio, avatar, GitHub, LinkedIn, RSS.
- No `menu.main` entries are configured.

## Design Direction
- Add films as a separate `films` section.
- Desired format: short text beside a film thumbnail, similar to Worth It Films.
- Use Vimeo for video hosting/embeds, not YouTube.
- Keep film descriptions short.

## Log
- 2026-05-03: Read project files, Paper/Ananke theme context, and current Hugo docs. Added this notes file.
- 2026-05-03: Noted films-section direction and Vimeo preference.
- 2026-05-04: Scaffolded draft `films` section with alternating thumbnail/text layout and Vimeo-ready single pages.
- 2026-05-04: Added six draft film entries from supplied Vimeo links.
- 2026-05-04: Enlarged film thumbnails, uppercased film titles, and hid role metadata.
- 2026-05-04: Made films index break out of Paper's narrow prose column and removed prose link/image styling from film cards.
- 2026-05-04: Reworked films index width to use a centered wide container with symmetric gutters and no viewport overflow.
- 2026-05-04: Added `main-films` class so film pages use a wider centered main container instead of viewport breakout CSS.
- 2026-05-04: Overrode Paper's `max-w-(--w)`/padding utilities for `main-films` so desktop film rows can use most of the viewport width.
- 2026-05-04: Added cache-busting query to Vimeo fallback thumbnails.
- 2026-05-04: Added explicit Vimeo CDN thumbnail URLs from oEmbed and made film cards prefer `thumbnailUrl`.
- 2026-05-04: Added homepage `FILMS` link via `layouts/index.html`.
- 2026-05-04: Moved homepage `FILMS` link below profile block and removed featured labels.
- 2026-05-04: Filtered `films` out of the Paper-style homepage page list.
- 2026-05-04: Changed homepage page list to explicitly show only `posts` so draft films never appear there.
- 2026-05-04: Enlarged homepage profile image/name and added configurable `aboutMe` homepage section.
- 2026-05-04: Added `main-home` class so homepage uses the same wide centered main container as films.
- 2026-05-04: Centered homepage profile image/name and moved the bio text into the About Me section.
- 2026-05-04: Added homepage `YOUTUBE` action in the center slot of a three-column action row and scaffolded empty `/youtube/` page.
- 2026-05-04: Copied films-style list/single templates for `/youtube/` and added three YouTube video entries.
- 2026-05-04: Added draft homepage reel below the profile name, driven by `data/home_reel.toml`, rotating 10-second muted clips from YouTube/Vimeo embeds.
