---
title: Plugins
template: page-tut.php
parent: 1497
order: 17
---

# Plugin Management

I recommend using [vim-plug](https://github.com/junegunn/vim-plug) to manage plugins, it makes it easy to install, update, and remove plugins. There are other plugin managers, but I've found vim-plug works best for me.

## Install

Install by [downloading plug.vim](https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim) and placing it in your `autoload` directory. This directory is dependent on your install, it might be `~/.vim/autoload/` or for Neovim `~/.config/nvim/autoload/`

Add a section to your `.vimrc` to specify the plugins to load. The `plug#begin` function may also specify what directory to download the plugins to. Here is an example specifying two plugins to use.

```vim
call plug#begin('~/.config/plugged')
    Plug 'fatih/vim-go'
    Plug 'mhartington/oceanic-next'
call plug#end()
```

The plugins are specified using their Github directory. So, the above `fatih/vim-go` plugin refers to the https://github.com/fatih/vim-go repository.

After updating `.vimrc` with a new or deleted plugin, you need to reload; it is easiest to just quit and restart vim. <span class="sidenote">You can also run `:source %` to source your config when you are editing it, personally I prefer quit/restart, it's less typing.</span>

After reloading, install the plugins using the command: `:PlugInstall`

## Remove a Plugin

If you want to delete a plugin, remove the line from your config. Quit and restart Vim, and then run `:PlugClean`. You will be prompted to delete the directory, type `Y`.

## Update Plugins

Run `:PlugUpdate` to update all plugins.

Run `:PlugUpgrade` to upgrade `vim-plug` itself.

## Documentation

See [vim-plug repository](https://github.com/junegunn/vim-plug) for full documentation and features.

