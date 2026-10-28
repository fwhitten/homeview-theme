# HomeView Theme

[![hacs][hacs-badge]][hacs-url]
[![release][release-badge]][release-url]
[![license][license-badge]](LICENSE)

Liquid glass over a photo wallpaper, in the style of Apple HomeView, for
Home Assistant wall panels. Light and dark modes follow your device or your
profile setting. The theme styles every built-in card and the rest of the
interface. It also supplies the `--hv-*` tokens that
[HomeView Cards](https://github.com/fwhitten/homeview-cards) read.

[![Open your Home Assistant instance and open a repository inside the Home Assistant Community Store.][hacs-button]][hacs-url]

## Install

**With HACS (recommended)**

1. Click the button above and confirm when HACS offers to add the repository.
2. Download **HomeView Theme**.
3. Make sure your `configuration.yaml` loads themes:

   ```yaml
   frontend:
     themes: !include_dir_merge_named themes
   ```

4. Restart Home Assistant, or run the **Reload themes** action
   (`frontend.reload_themes`).
5. In your profile, pick **HomeView** under **Theme**, and set
   **Dark mode** to Auto, Light or Dark.

To add it by hand: in HACS open ⋮ → **Custom repositories**, paste
`https://github.com/fwhitten/homeview-theme`, choose **Theme**, and click **Add**.

**Manually**

Copy `themes/homeview.yaml` into your `/config/themes/` folder, then follow
steps 3 to 5.

## Wallpapers

The theme looks for two photos:

| Mode | File |
| --- | --- |
| Dark | `/config/www/homeview/wall-dusk.jpg` |
| Light | `/config/www/homeview/wall-day.jpg` |

Download them from [`wallpapers/`](wallpapers) (HACS only installs the theme
file) and put them in `/config/www/homeview/`. Files in `www` are served under
`/local/`, so these become `/local/homeview/wall-dusk.jpg` and
`/local/homeview/wall-day.jpg`.

To use your own photos, change `lovelace-background` in each mode. Soft,
out-of-focus photos work best behind glass. For the HomeView wall-panel view,
set `wallpaper` on the view instead.

The same folder has two depth-photo pairs for the HomeView clock and ambient
clock: a background, plus a foreground with the subject cut out on a
transparent background.

| Pair | Background | Foreground |
| --- | --- | --- |
| Mountain | `alpine-bg.jpg` | `alpine-fg.webp` |
| Coast | `coast-bg.jpg` | `coast-fg.webp` |

They're placeholders. Make your own pairs from a photo: on a Mac, use
**Lift subject from background** in Photos or Preview for the foreground.

## Night mode

Home Assistant themes only have light and dark modes. HomeView's dimmed,
warm night look is drawn by HomeView Cards, from `night_entity`. The
`hv-night-*` variables in this theme set its colours.

## Tokens

| Variable | What it sets |
| --- | --- |
| `hv-glass`, `hv-glass-strong` | Tile and control glass |
| `hv-rim`, `hv-rim-soft`, `hv-sheen` | The specular edge and highlight |
| `hv-blur` | Backdrop filter behind tiles |
| `hv-ink`, `hv-ink-2`, `hv-ink-3` | Text, secondary and tertiary |
| `hv-track` | Unfilled tracks and dividers |
| `hv-radius` | Tile corner radius |
| `hv-font`, `hv-font-rounded` | Type, and the clock numerals |

## License

MIT — see [LICENSE](LICENSE). The wallpapers were generated for this project
and are covered by the same licence.

[hacs-badge]: https://img.shields.io/badge/HACS-Custom-41BDF5.svg?style=flat-square
[hacs-button]: https://my.home-assistant.io/badges/hacs_repository.svg
[hacs-url]: https://my.home-assistant.io/redirect/hacs_repository/?owner=fwhitten&repository=homeview-theme&category=theme
[release-badge]: https://img.shields.io/github/v/release/fwhitten/homeview-theme?style=flat-square
[release-url]: https://github.com/fwhitten/homeview-theme/releases/latest
[license-badge]: https://img.shields.io/github/license/fwhitten/homeview-theme?style=flat-square
