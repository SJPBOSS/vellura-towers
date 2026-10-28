# Publishing Vellura Towers on itch.io

The game is one folder. At runtime it does not request libraries, fonts, or images from a CDN. Three.js r128, cannon.js 0.6.2, Libre Baskerville, and Source Sans 3 are in this repo and referenced with relative paths.

This was checked by zipping the folder, unpacking it somewhere else, and opening it from a static server. The only host the page contacted was that server. Favicon requests returned the icon. A run placed floors with the mouse and with touch, saved a best score, and showed the result card.

## Zip

Put `index.html` at the root of the zip, not inside an extra folder. Include:

- `index.html`
- `favicon.ico`, `favicon.svg`, `favicon-32.png`, `apple-touch-icon.png`, `apple-touch-icon-precomposed.png`
- `vendor/` (Three.js, cannon.js, and their license files)
- `fonts/` (the woff2 files and the OFL license texts)

Leave out `CNAME` and `og.png`. Those belong to the website, not the embed. The Open Graph tags still point at `https://www.velluratowers.com/og.png` for link previews. The game itself never fetches that image.

## Embed

- Set the itch viewport to **960×640**. The same page is comfortable at 1280×720. The view fills whatever frame it is given.
- Turn on fullscreen for the embed so the parent frame allows it. The game has its own fullscreen button (also the F key). On older iPhones, element fullscreen is limited; the button stays quiet if the browser refuses.
- Mark the project mobile friendly. Portrait uses the full frame, including the safe area. Short landscape screens shrink the score so the controls still fit.
- Sound starts on the first tap, Space, or unmute. Mute is remembered on the device (`vellura-towers-mute`). The best score stays in `vellura-towers-best`, the same key as before.

## Cover and screenshots

Shoot these from the game. Do not use generated art.

- **Cover: 630×500.** A crop of the tower at night. Leave the title off the image. itch prints the name under the cover.
- **Screenshots: 1280×720**, four of them:
  1. The opening, with the floor sliding in.
  2. A tower a few floors up, including a perfect placement.
  3. The result card.
  4. A phone portrait of the same tower.

`og.png` in the site repo is a share image for the website. It is not the itch cover. The cover is a different aspect ratio.
