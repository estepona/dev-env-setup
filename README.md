# dev-env-setup

## tmux

`sudo apt install tmux`

`vim .tmux.conf`
```bash
# vim-like pane switching
bind -r k select-pane -U
bind -r j select-pane -D
bind -r h select-pane -L
bind -r l select-pane -R
```

Custom script to create a "tmux IDE"  
`vim Documents/scripts/bin/ide`
```bash
#!/bin/bash
tmux split-window -v -p 30
tmux split-window -h -p 66
tmux split-window -h -p 50
```
`chmod +x Documents/scripts/bin/ide`

Add `export PATH=$PATH:$HOME/Documents/scripts/bin` to `.bashrc`

## Neovim

### Plugins

#### NERDTREE
