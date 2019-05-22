---
title: Git
parent: 1497
template: page-tut.php
order: 23
---

# Git Integration

There are numerous plugins to integrate git with Vim. I still prefer to do all my committing on the command-line, but there are a few niceties by integrating.

## View Git Changes

For viewing differences in a single-file, the [gitgutter plugin](https://github.com/airblade/vim-gitgutter
) adds visual cues for additions, subtractions, and modifications in the gutter left of the line numbers.

The vim-gitgutter plugin also provides functions to navigate to changed chunks of code. I setup the following two maps to navigate to next and previous chunks:

```vim
nmap <Leader>gn <Plug>GitGutterNextHunk  " git next
nmap <Leader>gp <Plug>GitGutterPrevHunk  " git previous
```

=> ADD CASY

## Git Blame History

The [git-messenger plugin](https://github.com/rhysd/git-messenger.vim) provides blame information in a pop-up window, requires Neovim 0.40 support. On any line, activating the plugin function `:GitMessenger` will display the last commit message that modified the line.

=> ADD CAST

## View Git History

The [Agit plugin](https://github.com/cohama/agit.vim) displays the full repository history in a tabpage with multiple windows. 

