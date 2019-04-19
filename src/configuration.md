---
title: Configuration
date: 2019-03-17
---

# Vimrc

You probably already know about `.vimrc` or `.config/nvim/init.vim` if you use neovim. It is where you can put your configuration and shortcuts.  I'm going to include several examples from my config to give you an idea of what you can do.

First, the `<Leader>` is a special key is intended for user definition, so any setting of it will not conflict with default vim commands. By default the leader key is `\` but it is common to map it to `,` which you do using:

```
let mapleader=","
```

You can map a set of keys to any action, to create a mapping you need to define what mode you want the mapping to work. Use `map` for normal and visual modes, `nmap` for just normal mode, and `vmap` for just visual mode.

See `:help map-commands` for additional commands for less common modes.

A mapping entry specifies `[map-mode] [user-cmd] [vim-cmd]` where `user-cmd` is what you type, and `vim-cmd` is what vim executes. The vim cmd simply translates to the keystrokes you would have typed to get the desired result.

## Configuration

Since everyone asks, I use <a href="https://sourcefoundry.org/hack/">Hack font</a>, <a href="https://github.com/mhartington/oceanic-next">Oceanic Next</a> colorscheme, and <a href="https://github.com/vim-airline/vim-airline">Airline</a> for the fancy status bar.

You can check out my <a href="https://github.com/mkaz/dotfiles/blob/master/extras/nvim/init.vim">.vimrc in my dotfiles</a> repo. I actually use neovim, so it is init.vim. I don't really recommend just copying and pasting the whole thing, it ends up being personal preferences anyways.

I do recommend using <a href="https://github.com/junegunn/vim-plug">vim-plug</a> to manage plugins, it makes it easy to install, upgrade, and remove.

My one great tip from my configuration, which credit to whoever I picked it up from years ago, this saves me so many times.


```vim
" :w!! to save with sudo
ca w!! w !sudo tee >/dev/null "%"
```

When you open a file and don't have write permissions, you can call `:w!!` and it will auto sudo the file for you. Saves me practically every time I edit a system file.


