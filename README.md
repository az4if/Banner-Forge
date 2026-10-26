# Banner Forge

Turn any website screenshot into a project banner (dark background, text on the left, browser-framed screenshot on the right). Everything runs in your browser: no server, no build step, nothing is uploaded.

## Use it

1. Open `index.html` (or your deployed GitHub Pages link).
2. Click, drop or paste (Ctrl/Cmd+V) a screenshot.
3. Edit the label, title, description, tags and footer.
4. Pick colors (or a preset), move the glow, change the window size and rotation. Drag the browser window directly on the preview to move it.
5. Choose a canvas size and export resolution, then click **Download PNG**.

Tips:
- Use a tall page screenshot and the **Image scroll down** slider to choose which part shows.
- Export at 2x for a sharp result.
- **Save settings** downloads a JSON file; **Load settings** restores it, so you can make the same style for another project in seconds.

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

Then enable Pages as in step 3 and 4.

## Notes

- Fonts (Inter, Poppins, Space Grotesk, DM Sans, Outfit, JetBrains Mono) load from Google Fonts. Offline, it falls back to system fonts.
- Your settings are remembered in your browser's local storage. The screenshot itself is not stored, so load it again after a refresh.
