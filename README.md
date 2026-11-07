# Silva OS GitHub Pages upload

Upload the **contents of this folder** to the root of the repository connected to `os.silvaquieta.com`. Do not upload this folder as a nested directory.

The repository root should contain `CNAME`, the landing page files, icons, and the `app/` directory:

```text
CNAME
index.html
style.css
app.js
icon.svg
icon-192.png
icon-512.png
app/
  index.html
  style.css
  app.js
  theme-init.js
  manifest.webmanifest
  sw.js
```

In GitHub, open **Settings → Pages** and publish the root of the `main` branch. Set the custom domain to `os.silvaquieta.com` and wait for the deployment to finish.

- Landing page: `https://os.silvaquieta.com/`
- Silva OS app: `https://os.silvaquieta.com/app/`

The app is a Progressive Web App (PWA). The folder contains no Tauri build cache or native `.dmg`, `.msi`, or `.exe` installers.
