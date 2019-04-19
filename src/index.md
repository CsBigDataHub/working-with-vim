---
title: Working with Vim
---

# Working with Vim

A set of vim tips and features I use often, the goal is to help you improve your fluency with vim. I initially titled this post "Intermediate Vim" but experiences vary and non-linear, so what may be intermediate for some is basic or advanced for others.

A basic understanding of vim is a prerequisite, I try to explain everything but assume some base knowledge.  At minimum you should know moves (`h,j,k,l`), entering INSERT mode (`i,a`), or escaping to NORMAL mode (`esc`), and how to quit (`:q`).

The program `vimtutor` is a great way to learn the basics of vim. It is an interactive tutorial in vim walking through vim. Depending on your OS and how vim is installed, you may need to install the full vim package. Ubuntu for example ships with a tiny vim setup, you need to run `apt install vim`. If you use Neovim, run `:Tutor` inside the editor.

In the videos, the big yellow text in the bottom right are the key presses I do. They are overlayed using <a href="https://gitlab.com/wavexx/screenkey">screenkey</a> and not part of vim. I recorded videos so you can start/stop at will and see what is happening.

## Lessons

I recommend as you go through the lessons here, open vim in another window and follow along. You need try things out with your hands typing them as you go. It is like learning a language, repetition and practice helps.

Also, there is a lot to learn here. Don't try to cram it all in. Pick up an item at a time and slowly work in to your methodology.



### Repeat That

Press `.` to repeat the last command.

If you start with a number and then command it executes the command that many times. For example, if you want to delete three lines, `3dd`

<figure class="wp-block-video">
<video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-quickies.mp4"></video><figcaption>Quickies example</figcaption></figure>



#### Instant Quotes

Wrap a word in single or double quotes.

```
" Surround with Quote
map <Leader>' ysiw'
map <Leader>" ysiw"
```

--- TODO: animated gif wrapping word ---


#### Auto Command

`Autocmd` is a powerful tool to configure vim to automatically run on a specific event. See `:help autocmd-events` for a listing of available events.

Here is a common usage, setting a parameter based on the type of file. In this case, I want PHP files to use tabs and not spaces, because that is the WordPress standard.

```
" PHP File Types (WordPress, use tabs)
autocmd FileType php set noexpandtab
```

#### Edit Config File

A shortcut to open my config file using `:Edrc` command. User defined commands must start with a capital letter to distinguish from built-in commands.

```
" edit config file
command Edrc edit ~/.config/nvim/init.vim
```


