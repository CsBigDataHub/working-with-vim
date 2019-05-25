---
title: Git
parent: 1497
template: page-tut.php
order: 23
---

# Git Integration

By default, Vim provides no integration with git, all functionality is provided by plugins. There are a wide range of plugins and features to choose from, so your setup will depend on what you want to do. 

I prefer to do my gitting on the command-line, so I know exactly what is happening. However, there are still a few plugins that I use to make things a bit easier.

## View Git Changes

For viewing changes in a single-file, the [gitgutter plugin](https://github.com/airblade/vim-gitgutter) adds visual cues for additions, subtractions, and modifications in the gutter left of the line numbers.

The vim-gitgutter plugin also provides functions to navigate to changed hunks of code. I setup the following two maps to navigate to next and previous hunks:

```vim
nmap <Leader>gn <Plug>GitGutterNextHunk  " git next
nmap <Leader>gp <Plug>GitGutterPrevHunk  " git previous
```

The plugin also provides features beyond just visual cues. Here are the top ones that I use frequently: 

1. Use `:GitGutterPreviewHunk` to see hunk changes
2. Use `:GitGutterUndoHunk` to revert hunk
3. Use `:GitGutterStageHunk` for selective staging of hunks

<figure><asciinema-player src="/a/casts/vim/git1.cast" font-size="large" cols="58" rows="15"></asciinema-player><figcaption>gitgutter examples</figcaption></figure>

## Git Blame History

The [git-messenger plugin](https://github.com/rhysd/git-messenger.vim) provides blame information on a per-line basis. It will display the info in a Scratch window, or if your Vim supports it a fancy new pop-up window. Activate the plugin using the `:GitMessenger` function to display the last commit message that modified the line.

=> ADD CAST

## View Git History

The [Agit plugin](https://github.com/cohama/agit.vim) displays the full repository history in a tabpage with multiple windows. 

