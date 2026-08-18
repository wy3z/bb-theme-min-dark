# Min Dark for BB

A minimal dark theme for [BB](https://getbb.app), based on the **Min Dark (Solid)** theme for Zed.

## Palette

- Main panel: `#141414` at 90% opacity
- Sidebar: `#141414`
- Raised messages and code: `#242424`–`#333333`
- Border and selection: `#2A2A2A`
- Foreground: `#BBBBBB`
- Muted text: `#999999`
- Accent: `#79B8FF`

The repository also includes a matching Pierre/VS Code code theme for diffs and file previews.

## Install

Copy the repository into BB's custom theme directory:

```bash
mkdir -p "$(bb theme dir)/min-dark"
cp theme.css theme.json pierre-dark.json "$(bb theme dir)/min-dark/"
bb theme set min-dark
```

The stylesheet uses BB's bundled Inter Variable for the interface and FiraCode Nerd Font for code when available.
