# vicinae-zoxide

Zoxide directory jumper for [Vicinae](https://github.com/vicinaehq/vicinae). Fuzzy-search your frecent directories and open them in any program — terminal, editor, file manager, or custom tools — all from a single hotkey.

Built on [zoxide](https://github.com/ajeetdsouza/zoxide), the smarter `cd` that learns your habits.

## What it does

Open Vicinae, type a few characters of any directory path, and instantly jump there. Supports **kitty**, **alacritty**, **wezterm**, **foot**, **ghostty**, **gnome-terminal**, **konsole**, or any terminal emulator — plus editors, file managers, and up to five custom program slots, all with dedicated keybinds.

## How it works

Queries zoxide's frecency database, tokenizes each path into segments and adjacent pairs for deep fuzzy matching, and spawns programs detached so the launcher closes immediately. Uses Vicinae's native fuzzy filtering via `List.Item.keywords` for full-path matching — every directory segment is searchable, not just the basename. Typing `rkit` finds `/home/me/repos/rkit` because each segment and adjacent pair is a keyword.

## Install

```bash
git clone https://github.com/holo-q/vicinae-zoxide
cd vicinae-zoxide
npm install
npx vici build
```

Requires `zoxide` on `PATH`. If your `zoxide` lives somewhere unusual (e.g. `~/.local/bin`), set the `extraPath` preference to a colon-delimited prefix that includes its directory.

## Preferences

All preferences are optional.

| Name | Default | Purpose |
|---|---|---|
| `terminal` | autodetect | Terminal emulator command (**kitty**, **alacritty**, **wezterm**, **foot**, **ghostty**, **gnome-terminal**, **konsole**, ...) |
| `editor` | `code` | Editor command, bound to `ctrl+e`. Set to `-` to disable |
| `fileManager` | `xdg-open` | File manager command, bound to `ctrl+f` |
| `program1Cmd` .. `program5Cmd` | unset | Extra program slots, bound to `ctrl+1` .. `ctrl+5` |
| `program1Label` .. `program5Label` | unset | Display label for each slot; falls back to the command name |
| `extraPath` | unset | Colon-delimited PATH prefix for finding the `zoxide` binary |

A `programN` slot only appears in the action panel when its `programNCmd` is non-empty.

## Default keybinds

| Keys | Action |
|---|---|
| `Enter` | Open in terminal (cwd = selected path) |
| `ctrl+e` | Open in editor |
| `ctrl+f` | Open in file manager |
| `ctrl+1` .. `ctrl+5` | Open with custom program slots 1-5 |
| `ctrl+c` | Copy path to clipboard |
| `ctrl+x` | Remove entry from zoxide database |

## Keywords

vicinae extension, desktop launcher, zoxide, directory jumper, fuzzy finder, terminal launcher, file manager, developer tools, Linux launcher, frecent directories, autojump alternative

## License

MIT
