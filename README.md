

```toml
[templates.code]
input_path = "~/.config/matugen/templates/code-colors.jsonc"
output_path = "~/.config/matugen/themes/code-colors.jsonc"
post_hook = "python ~/.config/scripts/merge-vscode.py && pkill -SIGUSR1 nvim"

```
