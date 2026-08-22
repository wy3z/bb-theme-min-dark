# Min Dark for BB

Two minimal dark themes for [BB](https://getbb.app), using BB's default neutral
palette with Min-inspired terminal and code colours.

## Variants

- `min-dark-opaque` keeps BB's normal opaque window and sidebar surfaces.
- `min-dark-transparent` makes the desktop window transparent and renders the
  project sidebar at 90% opacity. Sidebar hover and selected states use 30%
  opacity.

Both variants include:

- Inter Variable for interface text.
- Fira Code for code and other monospace text.
- A matching Pierre/VS Code dark code theme for diffs and file previews.
- An auto-hiding project-sidebar scrollbar that appears on hover or keyboard
  focus.

The root-level theme files mirror `min-dark-transparent` for compatibility with
older installations of this repository.

## Requirements

BB bundles Inter Variable. Install `Fira Code` locally if it is not already
available; otherwise, the theme falls back to the browser's default monospace
font.

The transparent variant also requires a BB desktop build whose Electron window
uses these non-macOS options:

```js
{
  autoHideMenuBar: true,
  backgroundColor: "#00000000",
  transparent: true
}
```

For a completely hidden native menu, the desktop build must also call:

```js
Menu.setApplicationMenu(null)
```

The opaque variant works with an unmodified BB desktop or browser client.

## Install

Clone the repository, then copy either variant into BB's custom theme directory:

```bash
git clone https://github.com/wy3z/bb-theme-min-dark.git
cd bb-theme-min-dark

theme=min-dark-transparent # or min-dark-opaque
mkdir -p "$(bb theme dir)/$theme"
cp "$theme"/* "$(bb theme dir)/$theme/"
bb theme set "$theme"
```

To install both variants:

```bash
for theme in min-dark-opaque min-dark-transparent; do
  mkdir -p "$(bb theme dir)/$theme"
  cp "$theme"/* "$(bb theme dir)/$theme/"
done

bb theme set min-dark-transparent
```

Re-run `bb theme set <name>` after editing an active theme so BB reloads it.
