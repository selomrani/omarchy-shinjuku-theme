# Contributing

Thanks for helping improve Shinjuku. The theme is intentionally small: one
palette, one shell config, and a wallpaper set.

## Ground rules

- Keep `colors.toml` as the source of truth for color. If a color is only used
  by the shell, put it in `shell.toml` as a literal hex value.
- Preserve contrast. Body text must stay at or above 4.5:1 on the background;
  the current palette is comfortably above that. See the accessibility table
  in the README for measured ratios.
- Do not rely on hue alone for state. Hover, focus, and selection should keep
  their border and fill changes.
- Keep wallpapers at 16:9 and credit new ones in `WALLPAPERS.md`.

## Testing a change

Symlink your working copy so Omarchy treats it as a local theme:

```bash
ln -s ~/code/omarchy-shinjuku-theme ~/.config/omarchy/themes/shinjuku
omarchy theme set Shinjuku
```

Check that:

1. `omarchy theme current` reports `Shinjuku`.
2. There are no failures in `~/.local/state/omarchy/theme-set.log`.
3. `hyprctl configerrors` is empty.
4. The bar, launcher, notifications, and lock screen all pick up the change.

## Pull requests

- Keep commits focused: palette changes, shell changes, and documentation in
  separate commits where practical.
- Mention which surfaces you tested and include a screenshot for visible
  changes.
- Update `CHANGELOG.md` under an `Unreleased` heading.
