# Merge Energy Calculator

A fan-made web app for **Travel Town**. Enter what an order asks for, your producer's level and what's already on your board, and it tells you how much energy you need and which power boost costs the least.

- Works on any phone or computer browser, no sign-in
- Install it on the iPhone home screen (Safari → Share → **Add to Home Screen**) and it works offline
- Built-in bonus chances from 22 test sessions (~435 taps, producer levels 1–7, boosts x1–x16)
- Add your own tests; they stay on your device. Export/import them as a file to back up or share

## Files

| File | What it is |
|---|---|
| `index.html` | The whole app (layout, styles, logic, built-in data) |
| `manifest.webmanifest` | Name, icon and colors for home-screen install |
| `sw.js` | Offline support. **Raise `VERSION` in it whenever you change any file** |
| `icons/` | App icons |

## Publish on GitHub Pages (free)

1. Create a new **public** repository on github.com, e.g. `merge-energy-calculator`.
2. Upload all files and the `icons` folder (Add file → Upload files), keeping the folder structure.
3. Go to **Settings → Pages**, set *Source* to **Deploy from a branch**, branch `main`, folder `/ (root)`, and save.
4. After a minute the app is live at `https://<your-user>.github.io/merge-energy-calculator/`.

Any static host works the same way (Netlify, Cloudflare Pages, your own web space): upload the folder as-is. It must be served over **https** for offline support.

## Game rules the calculator uses

- One level L item = 2^(L−1) level 1 items
- Power boost x1/x2/x4/x8/x16 makes level 1/2/3/4/5 items and costs 1/2/4/8/16 energy per tap
- x2 unlocks at player level 20, x4 at 40 (Travel Town Wiki, "Leveling Up")
- x8 can be switched on with 200+ energy, x16 with 400+ (Travel Town Wiki, "Boosters"). Once on, the boost stays on as energy drops, even across producers and pages, until you change the boost or fully close the app (observed in game)
- Energy refills 1 every 2 minutes, up to 100
- Bonus items (+1 level or more) depend on producer level and boost; values come from test taps. Gift boxes ("WOW!") count as the level of the item inside and are treated as rare lucky jumps

## Credits and license

- Code: MIT License (see `LICENSE`)
- Producer and item-line data: [Travel Town Wiki](https://travel-town-mobile-game.fandom.com/wiki/Items), licensed CC BY-SA 3.0
- Not affiliated with, endorsed by or connected to Travel Town or its developer. All game names and trademarks belong to their owners.
