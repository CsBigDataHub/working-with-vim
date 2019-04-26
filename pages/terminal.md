---
title: Terminal
parent: 1430
template: page-tut.php
order: 20
---

## Terminal Built-in

I'm neutral on the built-in terminal, it doesn't take much effort to `ctrl-z` to drop to shell and then `fg` in bash to return.

`:terminal`

However, the built-in terminal is useful for issuing key commands, for example I use the following to build a Go binary using the `,b` shortcut.

```vim
autocmd FileType go nmap <leader>b :terminal go build<CR>
```
