# Silva OS GitHub Pages and desktop release

Publish the contents of this folder in the root of the `silvaos` repository. Keep
the `app/`, `desktop/`, and `.github/` directories in place, and include the
hidden `.github` directory.

## GitHub Pages

Publish the root of the `main` branch in **Settings → Pages**, and set the
custom domain to `os.silvaquieta.com`.

- Landing page: `https://os.silvaquieta.com/`
- Browser and iOS version: `https://os.silvaquieta.com/app/`

On Windows or macOS, open `/app/` in Chrome or Edge and choose
**Install Silva OS** in the browser menu (or use the install button in the
Silva OS top bar) to install the PWA as a separate, standalone app window; the
browser and operating system provide that window's native controls. The
macOS and Windows landing-page buttons look for the newest published release
that includes a `.dmg` or `.msi`/`.exe` and download that asset directly.
Until a matching installer release exists, the buttons explain that the
desktop build has not been published yet. On
macOS Safari, use **File → Add to Dock**. On iPhone/iPad, use Safari's
**Share → Add to Home Screen**. iOS does not provide desktop-style minimize or
resize controls for home-screen web apps.

## Native macOS and Windows apps

The Tauri project in `desktop/` builds a real desktop application with a
resizable native window and operating-system window controls. Within Silva OS,
apps can stay in a normal window or expand to fill the workspace; the app's
minimize, restore, and close controls remain available in either mode. It does
not open as a PWA. The GitHub Actions workflow in
`.github/workflows/release-desktop.yml` builds macOS and Windows installers
when a version tag is pushed.

The current desktop version is `1.0.0`, so the first release can use the tag
`v1.0.0`. Create and publish that release in GitHub; pushing the tag triggers
the workflow. After it finishes, the installers appear in GitHub Releases and
the landing-page buttons automatically download the matching platform file.
For later releases, update the version in `desktop/src-tauri/tauri.conf.json`
and `desktop/src-tauri/Cargo.toml` to the same value before creating the
matching version tag.

The workflow and source tree must be committed to GitHub; uploading only the
visible static website files will not create desktop installers. iOS continues
to use the browser installation flow because this package does not contain a
signed iOS app.
