# vim
`:colorscheme <tab>` to select alternative color theme
`v` `V` enter visual character, visual line modes
`Ctrl+V` enter visual block mode
  - `I<space>TEXT` enter `TEXT` on each line at the position
  - `<Esc>` end insert

## Plugins
Vim 8 supports native loading of plugins (put in `.vim/pack/xx/start/` where `xx` is an arbitrary directory name

## .vimrc
`.vimrc` configuration file (`/home/user/.vimrc`)
`"` comments

## Keyboard shortcuts exported supporting Vim-like shortcuts in Firefox
  `o` open URL
  `h` `j` `k` `l` scroll left, down, up, right
  `gg` `G` top and bottom of page
  `f` trigger hint mode for clickable elements
  `r` `R` reload, hard reload
  `H` `L` go back, forward in history
  `t` `x` `X` open, close, restore tab
  `?` show help

### VimFx, Vimium
  `yy` copy URL
  `yy` copy URL
  `/` search
  `n` `N` next, previous match
  `J` `K` switch between tabs
  `space` `shift+space` page up, down
  `?` see all shortcuts
  `i` "ignore" mode

### Vimium
  `f` `F` open link in current tab, new tab, 
  `i` insert mode
  `alt+m` mute tab

### Vim Vixen
  `:` open console
  `o` `t` `w` open page in current tab, new tab, new window
  `O` `T` `W`
  `a` bookmark page
  `zi` `zo` `zz` zoom in, out, neutral
  `[[` `]]` find previous, next link and open it
  `y` copy URL of current tab
### Tridactyl
  `:` activate command line
  `ctrl+g` `ctrl+G` next, previous result

# Atom

## Key bindings
Add key bindings to the `keymap.cson` file (File menu)
- Soft wrap: `editor:toggle-soft-wrap`
- Delete line: `editor:delete-line`

# VS Code
`Alt-<Up>` `Alt-<Down>` move line up, down

## Multi-line editing
`Option-Command-<Down>` `Option-Command-<Up>`
: add a cursor up or down

`Option-Shift-<Left Mouse Button>`
: click and drag to add cursors