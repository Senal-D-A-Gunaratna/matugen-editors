# matugen-editors


add this in your matugen congifig
>pleas note
- use your correct matugen generated "code-colors.jsonc" output path
- edit the scripts according to your file paths
```toml
[templates.code]
input_path = "~/.config/matugen/templates/code-colors.jsonc"
output_path = "~/.config/matugen/themes/code-colors.jsonc"
post_hook = "python ~/.config/scripts/merge-vscode.py && pkill -SIGUSR1 nvim"

```
apply opacty using hyprland otherwis it dusnt look good

```conf
windowrule = opacity 0.8 0.85, match:class codium
windowrule = opacity 0.75 0.8, match:class kitty
```
