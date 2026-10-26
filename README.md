<p align="center">
  <img src="icon/icon-512.png" alt="Banner Forge logo" width="120" height="120">
</p>

<h1 align="center">Banner Forge</h1>

<p align="center">
  Turn any website screenshot into a polished project banner.<br>
  Runs entirely in your browser: no server, no build step, nothing is uploaded.
</p>

Banner Forge makes banners like the ones on portfolio project cards: a dark background with a soft glow, your text on the left (label, title, description, tags, footer) and your screenshot inside a browser window on the right.

## Quick start

1. Open `index.html`, or your deployed GitHub Pages link.
2. Add a screenshot of your site.
3. Edit the text, colors and layout.
4. Click **Download PNG**.

## Tutorial: make your first banner

### 1. Take a good screenshot

- Capture the top part of your page (the hero section) rather than the whole page. A tall full-page capture works too, since you choose which part shows later.
- A desktop-width screenshot (1200 px wide or more) looks best. Phone-width screenshots will look stretched inside the browser window.

### 2. Add it to Banner Forge

Use any of these:
- Click the dashed box under **Screenshot** and choose the file.
- Drag and drop the image anywhere on the page.
- Copy the image and paste it with Ctrl/Cmd+V.

To swap it for another image later, just add a new one. **Remove screenshot** clears it.

### 3. Write your text

Open the **Text** section:

| Field | What it does |
| --- | --- |
| Label | Small colored line on top. Always shown in uppercase, for example `WEB APP / ANIME STREAMING`. |
| Title | The big heading. Press Enter for a line break. |
| Description | One or two sentences about the project. It wraps automatically. |
| Tags | Comma separated, for example `JavaScript, REST API, Responsive UI`. Each becomes a pill. |
| Footer | Small text at the bottom left, such as your website. |

Leave a field empty to hide it.

### 4. Choose colors

Open **Colors**:
- Click one of the 21 presets (dark ones like Violet, Forge, Sunset, Mint and Midnight, plus light ones like Sand, Paper and Blush) for a quick start, or press **Shuffle** for a random palette.
- Then fine tune any color with the pickers: background, accent (label, left bar, line under the window bar), title, description, and the tag fill, border and text.
- To match your site, set the accent to your brand color, then set the glow color in **Background** to the same one.

### 5. Position the screenshot

- Under **Screenshot window**, choose **Screenshot preview**: **2D (flat)** or **3D (perspective)**. Each mode remembers its own position and size, so you can switch back and forth.
- In 3D mode, **turn left / right** and **tilt up / down** rotate the window, **perspective strength** controls how steep the angle looks, and **edge fade** melts the right and bottom edges into the background. The window shadow is hidden while edge fade is on; set the fade to 0 to bring the shadow back.
- **Drag the browser window** directly on the preview to move it.
- Open **Screenshot window** for exact control: left and top position, width and height, rotation, image zoom, and the two shift sliders.
- Use **Image scroll down** to pick which part of a tall screenshot shows, and **Image zoom** to enlarge details.
- It looks best when the window runs off the right edge of the banner, so set the width a bit larger than the space left.

### 6. Style the window and background

- **Window frame**: turn the browser bar on or off, show an address bar with your own text, switch to colored window dots, set the corner radius and shadow, and add or remove the accent line.
- **Background**: move the glow (X and Y), change its size and strength, turn the faint grid on or off, and show or hide the colored bar on the left edge.
- **Typography** and **Text position**: change the font, title weight, sizes and where the text block sits.

### 7. Pick a size and export

Open **Output**:
- **Canvas size**: 1200 × 630 for Open Graph and social previews, 1280 × 640 for the GitHub social preview, 1200 × 675 for Twitter/X cards, 1500 × 500 for an X header, 1584 × 396 for a LinkedIn banner, 1920 × 1080 for Full HD, or square.
- **Export resolution**: 2x gives the sharpest result and is a good default.

Then use the buttons at the top:
- **Download PNG** or **Download JPG** saves the file.
- **Copy PNG** copies the banner to your clipboard.

When you change the canvas size, the text scale adjusts automatically. Check the layout afterwards, since wide or square sizes may need the window and text positions nudged.

### 8. Reuse your style

- **Save settings** downloads a small JSON file of everything you set (not the screenshot).
- **Load settings** restores it, so you can make a matching banner for another project in seconds.
- **Reset** returns everything to the defaults.
- Your settings are also remembered in your browser automatically.

## Tips

- Keep the title short. One or two words look best at the default size.
- Keep text away from the busiest part of the screenshot.
- Use the same accent and glow color as your site so the banner looks like part of the project.
- To use the banner as a GitHub social preview, export at 1280 × 640 and upload it under the repository's Settings.

## Troubleshooting

- **The text uses a plain font.** The fonts load from Google Fonts, so they need an internet connection. Offline, system fonts are used.
- **My screenshot disappeared after refreshing.** Settings are remembered, but the screenshot is not. Add it again.
- **Copy PNG does not work.** Some browsers block clipboard images. Use Download PNG instead.
- **The old footer or text keeps showing.** Click **Reset**, or edit the field.

## Deploy on GitHub Pages

1. Create a new repository on GitHub (for example `banner-forge`).
2. Upload `index.html`, `favicon.ico`, the `icon` folder and `README.md` to the repository root (Add file, then Upload files). Keep the `icon` folder next to `index.html`, since the page loads its logo and favicon from there.
3. Go to **Settings, then Pages**.
4. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose the `main` branch and the `/ (root)` folder, then Save.
5. After a minute your tool is live at `https://YOUR-USERNAME.github.io/banner-forge/`.

Command line version:

```bash
git init
git add index.html favicon.ico icon README.md
git commit -m "Banner Forge"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/banner-forge.git
git push -u origin main
```

Then enable Pages as in steps 3 and 4.

## Releasing a new version

The version lives in one place: the `APP_VERSION` line near the top of the script in `index.html`.

1. Change `const APP_VERSION = "1.0.2";` to the new number, for example `"1.0.3"`.
2. Add an entry at the top of the `CHANGELOG` list just below it. This is what people see when they click the version badge.
3. Commit and push to `main`. GitHub Pages deploys in about a minute.

What visitors get:
- **Opening the site:** the page checks the deployed `index.html` and, if it is newer than the copy in the browser cache, switches to the new build by itself. Old versions do not stick around.
- **Already open in a tab:** a small "Version 1.0.3 is available" message appears with an **Update now** button. It asks first so nobody loses a screenshot they are working on. The check runs when the tab regains focus and every 5 minutes.
- **After updating:** a short "Updated to v1.0.3" message appears with a link to what's new.
- Icons and the logo are loaded with the version in their address, so a new version always fetches fresh ones.

Always change `APP_VERSION` when you push a change. Pushing without bumping it still deploys, but open pages will not know there is anything new.

## Project files

```
index.html     the whole tool (HTML, CSS and JavaScript)
favicon.ico    browser tab icon
icon/          logo and icon sizes
README.md      this file
```

## Credits

Made by [azif.me](https://azif.me).
