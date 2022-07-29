# dev-env-setup

## OS

### Mac

Install **homebrew**.

```bash
brew install tmux
brew install neovim
```

### Ubuntu

#### Update

```bash
sudo apt update
sudo apt install build-essential
```

## Terminal

### Windows Terminal

Appearance
- Color scheme: `Tango Dark`
- Font face: `Hack NF`
- Font size: `12`
- Font weight: `Semi-bold`
- Retro terminal effects: `Off`
- Cursor shape: `Filled box`
- Intense text style: `Bright colors`
- Background opacity: `40%`
- Enable acrylic material: `On`
- Padding: `8`
- Scrollbar visibility: `Visible`

Advanced
- Bell notification style: `Flash window`

## zsh

### Install

`sudo apt install zsh`, then set it as default shell with `chsh -s $(which zsh)`

### ohmyzsh

Follow https://github.com/ohmyzsh/ohmyzsh.

#### Nerd Fonts

Required to customize ohmyzsh. Download and install one (i.e. Hack) from https://github.com/ryanoasis/nerd-fonts/releases, then set it as the default font.

#### Theme

```vim
ZSH_THEME="robbyrussell"
```

#### Plugins

- git
- [auto suggestions](https://github.com/zsh-users/zsh-autosuggestions)

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

## [nvm](https://github.com/nvm-sh/nvm)

`curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash`

### npm

### yarn

## [Neovim](https://neovim.io/)

### [Install](https://github.com/neovim/neovim/wiki/Installing-Neovim)

Install from releases page.

### Uninstall or Update

Delete (`sudo apt-get remove --auto-remove neovim`) and then install from releases.

### Config

`nvim ./config/nvim/init.vim`

My [init.vim](./init.vim) config file.

### Plugins

#### [vim-plug](https://github.com/junegunn/vim-plug)

Required to install all plugins.

#### [Coc](https://github.com/neoclide/coc.nvim)

##### Install

Follow the official guide to install coc with nodejs, then add the plugin to `init.vim` file:  
`Plug 'https://github.com/neoclide/coc.nvim'`

Then, install essential LSPs:  
`:CocInstall coc-json coc-sh coc-yaml coc-markdownlint`

##### Config

`:CocConfig`

My [coc-settings.json](./coc-settings.json) config file.

#### NERDTREE

##### Switch windows

`Ctrl + w` + `w`

Ref
- [How to switch between different windows](https://github.com/preservim/nerdtree/wiki/F.A.Q.#how-do-i-switch-between-the-different-windows)

#### Switch tabs

- `gt` to next tab
- `gT` to prev tab
- `{count}gt` to tab page {count}. The first tab page has number one.

Ref
- Official Guide](https://neovim.io/doc/user/tabpage.html)

##### Add, Remove, Rename file/dir

Type `m` to invoke an interactive dialog
- add: `m` + `a`
- remove: `m` + `d`
- move (rename): `m` + `m`

#### [Telescope](https://github.com/nvim-telescope/telescope.nvim)

#### [markdown-preview](https://github.com/iamcco/markdown-preview.nvim)

### Vim tips

How to copy to and paste from system clipboard
1. `"+y` instead of `y` after selecting texts from visual mode
2. Then use `"+p` instead of `p` to paste
