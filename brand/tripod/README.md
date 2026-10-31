# The AI tripod's pictures

Three CEO-approved pictures of the AI tripod, for `/tripod` (and `/tripod/buy` while it is built). Approved on the drip
hero sheet (lane HS1b, 2026-10-26); re-approved for the page on 2026-10-31. Never recoloured, never a picture made here.

| file here (1200 and 720 wide, webp) | source (app repo `trent-stonehouse/socialrealtr`, branch `v6-ui-overhaul`) | what it is |
|---|---|---|
| `tripod-1-1200.webp` · `tripod-1-720.webp` | `features/drip-hero-slot-2026-10-26/publish/tripod-1.jpg` (1200×600) | the device on black with a green glow |
| `tripod-2-1200.webp` · `tripod-2-720.webp` | `features/drip-hero-slot-2026-10-26/publish/tripod-2.jpg` (1200×600) | on a wooden desk by a window with a coffee cup — the page's lead picture |
| `tripod-3-1200.webp` · `tripod-3-720.webp` | `features/drip-hero-slot-2026-10-26/publish/tripod-3.jpg` (1200×600) | close on the base, a green ring on a dark surface |

**Status (lane VS67, 2026-10-31): the files are NOT here yet.** The app repo was not reachable from lane VS67's session
(the repository request was refused and `git clone` had no credential), and the brief's rule stands: no substitute, no
generated picture. To land them, from a machine that holds the app repo:

```bash
node scripts/tripod-pictures.mjs <path to the app repo>/features/drip-hero-slot-2026-10-26/publish
```

writes the six webp files here from the three jpgs (the repo's own image tooling, PIL as in `scripts/prepare-shots.mjs`;
Lanczos resample to 720, quality 88, no colour change). Then set `photo`, `photoAlt` and `photos` in `site.config.ts`
`tripod` to the values its block comment spells out, and run `npm run test:tripod` on a staging build — it demands all
three on the page the moment the files exist.
