---
title: Terminal
parent: 1497
template: page-tut.php
order: 20
---

## Terminal Built-in

You can run a terminal inside of Vim since Vim 8.1 and in Neovim. Use the `:terminal` command which will start a terminal session in a new buffer.

I use this feature but normally only for quick one-off processes, like a build. If I'm going to do much more I'll drop to the shell using `ctrl-z` and return using `fg` in bash.

## Script the Terminal

What I really like about the built-in terminal is you can script it. This makes automating some tasks quite easy and useful. For example, writing this tutorial I run my [wpsync program](https://github.com/mkaz/wpsync) which copies the markdown files I am authoring in Vim, to my WordPress site that hosts.

I'll run this within vim using: `:terminal wpsync`


### Build Your Program

You can create a config mapping to make it even easier. I map the following to build a Go binary using the `,b` shortcut.

```vim
autocmd FileType go nmap <leader>b :terminal go build<CR>
```

