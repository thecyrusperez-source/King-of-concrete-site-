# King of Concrete — Website

Single-file production site for **King of Concrete LLC** — West Palm Beach, FL. Everything (CSS + JS) lives inline in `index.html`; the only external requests are Google Fonts and the assets below. Deploy by pointing any static host (Netlify, Vercel, GitHub Pages, cPanel) at the repo root.

## What's already live in the file

- 3D textured logo (`assets/logo.png`, transparency restored from the flattened original) used everywhere — the opening animation assembles the actual PNG from four slices (crown / KING / of / chevron), holds the finished mark ~3s, then wipes to the hero; the crown scroll-progress indicator and section watermarks are CSS crops of the same file.
- Hero background video (`assets/video/hero.mp4`) blurred to silhouettes; if a browser can't play it, a Ken-Burns pan over the crew photo takes over automatically.
- **11 real job photos** in `assets/gallery/` wired into the service blocks (Repair & Leveling shows the before/after pair) and the masonry gallery (below Contact) with descriptive alt text.
- Animated growth chart beside the real **Facebook 96% recommend (19 reviews)** stat; **BBB "A"** badge. Confirmed ratings only.
- Phone (561) 410-6277 wired as `tel:` links throughout; quote form opens the visitor's email app pre-filled (no backend needed).

## Adding more assets (the site adapts automatically)

| Path | What | Current behavior |
|---|---|---|
| A concrete-cutting photo | The one service with no photo yet — add the `<img>` in its block (marked `TODO(Cyrus)`) | Designed crown-watermark panel shows |
| More gallery photos | Copy any `<button class="tile">` line in the masonry section and point it at the new file | Tiles appear automatically once the file exists |

Any mix of portrait/landscape works in the gallery — the masonry layout uses natural aspect ratios.

## TODOs before launch (search `TODO(Cyrus)` in index.html)

1. **Domain** — find/replace `kingofconcretefl.com` once the real domain is bought (canonical, OG tags, JSON-LD).
2. **Quote inbox** — form currently mails `thecyrusperez@gmail.com`; change `QUOTE_EMAIL` in the script at the bottom of `index.html` if you want a different inbox.
3. **Google & Yelp ratings** — two badge cards ship `hidden` with `[RATING]` placeholders. Fill in the real verified numbers, then delete the `hidden` attribute. Don't guess.
4. **Instagram** — footer has a marked spot; add the link when the account is live.
5. **Hero footage** — current clip is AI-generated; swap in real job-site video at `assets/video/hero.mp4` whenever you have it (same filename, nothing else to change).

## Magic MCP (21st-dev)

`.mcp.json` registers the `@21st-dev/magic` MCP server for Claude Code sessions in this repo. It needs an API key from <https://21st.dev/magic/console>:

```bash
export MAGIC_API_KEY="your-key-here"
```

Set that in your environment (or in the Claude Code environment settings for web sessions) and the `/ui` component-generation tools load on the next session start.
