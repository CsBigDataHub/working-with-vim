---
title: Plugins
template: page-tut.php
parent: 1430
order: 17
---

# Plugin Management

I recommend using [vim-plug](https://github.com/junegunn/vim-plug) to manage plugins, it makes it easy to install, update, and remove plugins. There are other plugin managers, but I've found vim-plug works best forme.

## Install

Installation is straight-forward, [download plug.vim](https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim) and place in the `autoload` directory in your vim confiugration, this might be `~/.vim/autoload/` or for Neovim `~/.config/nvim/autoload/`

Add a section to your `.vimrc` that you specify the plugins to load. The `plug#begin` function also specifies what directory to download the plugins to. Here is an example specifying two plugins to use.

```vim
call plug#begin('~/.config/plugged')
    Plug 'fatih/vim-go'
    Plug 'mhartington/oceanic-next'
call plug#end()
```

The plugins are specified by their Github directory, so the above `fatih/vim-go` plugin refers to the https://github.com/fatih/vim-go repository.

After updating `.vimrc` with a new or deleted plugin, you need to reload; it is easiest to just quit and restart vim.

You can then install the plugins using the command: `:PlugInstall`

## Remove a Plugin

If you want to delete a plugin, you remove the line from your config and then run `:PlugClean`

## Update Plugins

You update all plugins running `:PlugUpdate`

You can upgrade `vim-plug` itself by running `:PlugUpgrade`

## Documentation

See [vim-plug repository](https://github.com/junegunn/vim-plug) for full documentation and features.

