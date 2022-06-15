# dev-env-setup

## tmux

### Install

`sudo apt install tmux`

### vim-like pane switching

`vim .tmux.conf`
```bash
bind -r k select-pane -U
bind -r j select-pane -D
bind -r h select-pane -L
bind -r l select-pane -R
```

### Custom script to create a "tmux IDE"  

`vim Documents/scripts/bin/ide`
```bash
#!/bin/bash
tmux split-window -v -p 30
tmux split-window -h -p 66
tmux split-window -h -p 50
```

Make it executable: `chmod +x Documents/scripts/bin/ide`

Finally, add `export PATH=$PATH:$HOME/Documents/scripts/bin` to `.bashrc`.

## [Neovim](https://neovim.io/)

### [Install](https://github.com/neovim/neovim/wiki/Installing-Neovim)

Ubuntu: `sudo apt install neovim`

### Config

`nvim ./config/nvim/init.vim`

My [init.vim](./init.vim) config file.

### Plugins

#### [vim-plug](https://github.com/junegunn/vim-plug)

Required to install all plugins.

#### NERDTREE

##### Switch windows

`Ctrl + w` + `w`

Ref
- [How to switch between different windows](https://github.com/preservim/nerdtree/wiki/F.A.Q.#how-do-i-switch-between-the-different-windows)

#### Switch tabs

- `gt` to next tab
- `gT` to prev tab

##### Add, Remove, Rename file/dir

Type `m` to invoke an interactive dialog
- add: `m` + `a`
- remove: `m` + `d`
- move (rename): `m` + `m`

### Vim tips

How to copy to and paste from system clipboard
1. `"+y` instead of `y` after selecting texts from visual mode
2. Then use `"+p` instead of `p` to paste
