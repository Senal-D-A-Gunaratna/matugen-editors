# matugen-editors

Wallpaper-driven theming for VSCodium + Neovim from a single JSON — with hot reload.

## Setup

Add this to your matugen config:

> **Note:** Make sure to use the correct output path for your matugen-generated `code-colors.jsonc` and update the python-script and lua-plugin paths to match your setup.

```toml
[templates.code]
input_path = "~/.config/matugen/templates/code-colors.jsonc"
output_path = "~/.config/matugen/themes/code-colors.jsonc"
post_hook = "python ~/.config/scripts/merge-vscode.py && pkill -SIGUSR1 nvim"
```

## Hyprland Window Rules

Apply opacity via Hyprland window rules — the blur effect won't look right without it:

```conf
windowrule = opacity 0.8 0.85, match:class codium
windowrule = opacity 0.75 0.8, match:class kitty
```
