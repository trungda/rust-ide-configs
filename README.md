# rust-ide-configs

Editor configs for Rust development.

## Layout

```
zed/
  settings.json                 # -> ~/.config/zed/settings.json
  themes/dark-plus-cursor.json  # -> ~/.config/zed/themes/
cursor/
  settings.json                 # -> ~/Library/Application Support/Cursor/User/settings.json
  keybindings.json              # -> ~/Library/Application Support/Cursor/User/keybindings.json
```

The Zed config is a port of the Cursor config: the "Dark+ (Cursor)" theme, rust-analyzer
semantic token colors (`global_lsp_settings.semantic_token_rules`), rust-analyzer options and
custom snippets, JetBrains Mono, relative line numbers, and vim mode.

## Install (Zed)

Back up any existing config first, then symlink so `git pull` keeps it up to date:

```bash
git clone https://github.com/trungda/rust-ide-configs.git ~/rust-ide-configs
mkdir -p ~/.config/zed/themes
[ -e ~/.config/zed/settings.json ] && mv ~/.config/zed/settings.json ~/.config/zed/settings.json.bak
ln -s ~/rust-ide-configs/zed/settings.json ~/.config/zed/settings.json
ln -s ~/rust-ide-configs/zed/themes/dark-plus-cursor.json ~/.config/zed/themes/dark-plus-cursor.json
```

Requires the JetBrains Mono font and Zed with LSP semantic token support (tested on 1.28).

## Install (Cursor)

```bash
CURSOR_USER="$HOME/Library/Application Support/Cursor/User"
cp ~/rust-ide-configs/cursor/settings.json ~/rust-ide-configs/cursor/keybindings.json "$CURSOR_USER/"
```

`clangd.path` in `cursor/settings.json` is machine-specific; update or remove it.
