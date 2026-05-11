# matugen-editors

### Wallpaper-driven theming for VSCodium + Neovim from a single JSON — with hot reload.
[![matugen theming VSCodium + Neovim WITH hot reload!](https://img.youtube.com/vi/SxhlFnLyLbQ/maxresdefault.jpg)](https://youtu.be/SxhlFnLyLbQ)

## How it works

matugen generates a `code-colors.jsonc` from your wallpaper → a Python script merges the colors into your VSCodium settings → a `SIGUSR1` signal hot reloads Neovim instantly. Change your wallpaper, everything repaints.

## Setup

### 1. matugen config

Add this to your matugen config. Make sure to confirm the `input_path` and `output_path` match your system and update the script path to match your setup:

```toml
[templates.code]
input_path = "~/.config/matugen/templates/code-colors.jsonc"
output_path = "~/.config/matugen/themes/code-colors.jsonc"
post_hook = "python ~/.config/scripts/merge-vscode.py && pkill -SIGUSR1 nvim"
```

### 2. VS-Code/Codium

- Copy [`code-colors.jsonc`](code-colors.jsonc) to your matugen templates directory
- Copy [`merge-vscode.py`](merge-vscode.py) to your scripts directory
- Set your VSCodium color theme to **Dark Modern**

### 3. Neovim (LazyVim)

Copy both files from the [`plugins/`](plugins/) directory into your LazyVim plugins directory (`~/.config/nvim/lua/plugins/`):

- [`plugins/load-matugen.lua`](plugins/load-matugen.lua) — plugin spec
- [`plugins/matugen.lua`](plugins/matugen.lua) — UI theme

Then open `plugins/matugen.lua` and confirm the `JSON_PATH` at the top matches your `code-colors.jsonc` output path.

### 4. Hyprland opacity

Apply opacity via Hyprland window rules — neovim won't look good without it:

```conf
windowrule = opacity 0.8 0.85, match:class codium
windowrule = opacity 0.75 0.8, match:class kitty
```

> **Note:** Double check all file paths throughout the config match your specific system setup.
