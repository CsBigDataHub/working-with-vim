---
title: Help Yourself
parent: 1497
template: page-tut.php
order: 2
---

# Help Yourself

Vim has extensive documentation on every command and feature. This is the first place to turn if you ever have a question.

Type `:help [command]` to see help for any command.

For example, `:help gg` will explain what the `gg` command does.

Help opens in a new window split horizontally, see [Windows section](/working-with-vim/windows/) for working with windows.

You can close the window split using `ctrl-w c` or `:close`

To make help the only window, use `ctrl-w o` this removes the split but does not close help or your original buffer. Close the help buffer using `:bd`, to switch back to your original buffer.

Help is simply a read-only buffer. You can navigate, highlight, copy, paste, search, and do any vim things as any other buffer, except edit. See [Buffers section](/working-with-vim/buffers/) for more on working with buffers.

## Navigate Help Tags

The help pages include tags to other help sections, depending on your colorscheme it might be blue. With your cursor on an item type `ctrl-]` to jump to that definition. This actually works for any words in help.

<figure><asciinema-player src="/a/casts/vim/help.cast" font-size="large" cols="80" rows="25"></asciinema-player><figcaption>Example using Help</figcaption></figure>
