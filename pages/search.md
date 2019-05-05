---
title: Search
parent: 1497
template: page-tut.php
order: 8
---

# Search


## Quick Search

<span class="sidenote">See `:help *`</span> Use `*` and `#` to navigate to the word under the cursor, `*` forward and `#` backwards. This searches within the current buffer.

I'll use this to check the spelling of variables, by using `*` on a variable it highlights all the words spelled the same. A nice quick way to check for misspellings.

<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-star-nav.mp4"></video><figcaption>Quick Search Examples</figcaption></figure>

## Regex Motions

Use `/term` to move forward to next "term", and use `?term` to move backwards to previous "term".

<span class="sidenote">See `:help pattern-searches`</span>

You can combine with delete and yank, and any other operator. For example: `d/apple` will delete from current spot to the string apple. Vim highlights the words to show and you press enter to confirm.

I don't use the delete or copy features with regex, but do use frequently to navigate around.

### Remove Highlight

Search results remain highlighted after a search, the following maps `<Leader><Space>` to unhighlight.

```vim
" Unhighlight Search using ,SPC
nmap <silent> <Leader><Space> :nohlsearch<CR>
```

Try out the [vim-slash plugin](https://github.com/junegunn/vim-slash) to clear highlighting automatically when the cursor is moved. This works pretty nicely, though additional changes the `*` search.

I setup the shortcut above to clear, but since installing vim-slash plugin, I use it less frequently, the plugin ends up clearing it most of the time, so the plugin may be all you need.

## Multiple Files

<span class="sidenote">See `:help vimgrep`</span> Use `:vimgrep /pattern/ {file}` to search across multiple files.

For example: `:vimgrep /TODO/ *.go` would search all files with go extension for the text TODO.

Use `:cn` to jump to next match.

Use `:cp` to jump to previous match.

Use `:copen` to open list of matches in quickfix window

You can use `**/*.go` or `**/*` to recursively search through directories.

### Ripgrep and FZF

The `:vimgrep` works ok, but a bit verbose and not as smart for searching code, I prefer to use [ripgrep](https://github.com/BurntSushi/ripgrep) for search and [fzf](https://github.com/junegunn/fzf) for fuzzy matching. Ripgrep by default ignores items in .gitignore, binary, and other bits, and easy to configure how you want.

See my [Unix is my IDE](https://mkaz.blog/code/unix-is-my-ide/) for the full setup. Installing and using both are a bit easier now that binaries are included in recent package repostiories.

I use these two plugins for `fzf`. The first provides basic support, and the second provides some useful and common mappings using the basic support.

```vim
Plug 'junegunn/fzf',  { 'dir': '~/.fzf' }
Plug 'junegunn/fzf.vim'               " fuzzy search
```

I then configure a custom `:Find` command to use fzf and ripgrep to perform a search.

```vim
" use ripgrep for finding text
noremap <Leader>f :Find<space>
command! -bang -nargs=* Find call fzf#vim#grep(
    \ 'rg --column --line-number --no-heading
    \ --fixed-strings --ignore-case --hidden --follow
    \ --color "always" '.shellescape(<q-args>), 1, <bang>0)
```
