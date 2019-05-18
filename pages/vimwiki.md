---
title: VimWiki
parent: 1497
template: page-tut.php
order: 22
---

# VimWiki

[VimWiki](https://github.com/vimwiki/vimwiki) is a powerful plugin that enables Vim to be your own personal wiki. It is a great tool to keep track of notes, lists, or just about anything.

<span class="tip">😎</span>Yes, Vim is a text editor and of course you can type notes or list in any. VimWiki provides the convenience and defined space to always have a scratch area ready to write without having to think about where and what file to create.

## Install and Configuration

Install the plugin using `vim-plug`

```vim
Plug 'vimwiki/vimwiki'
```

I configure VimWiki to a specific directory which I sync across devices. VimWiki stores everything in plain text files. I use the markdown syntax, the default markup is similar but just different enough that I need to configure it to markdown.

```vim
" Vim Wiki
let g:vimwiki_list = [{'path': '~/Sync/wiki/', 'syntax': 'markdown'}]
au FileType vimwiki setlocal shiftwidth=6 tabstop=6 noexpandtab
```

## Usage

The basic usage is typing `<Leader>ww` to open your index file, one will be created if it does not already exist.

This can be an instant scratch pad to take whatever notes that you want. You can create additional files by insert a links and navigating to it. 

Insert a link by surrounding text with double-brackes, for example `[[LinkText]]`.  Once a link is created, navigate to the new page by placing your cursor over the word and pressing enter. This will open, creating the file if needed, the linked page.

Create pages for any list, tasks, info, notes, or for whatever you want.

## Todo Lists

VimWiki has a few built-in types and features. One of which is a todo list features. You can create a list of items that can be checked off using the syntax:

```md
- [ ] Write Vim Lessons
- [ ] Edit Vim Lessons
- [ ] Publish
```

You can add a checkbox using `ctrl-<Space>`, use `gl<Space>` to remove checkbox.

To toggle an item complete use `ctrl-<Space>` with your cursor on the line you want to toggle. Todo lists also work for nested items, simply indent the item. Vim folding works with nested lists. Toggling will also mark all sub-items.

For an item that might be partially complete, use `gln` to toggle forward completion levels, and use `glp` to toggle backwards completion levels. Levels progress through '.oOX' sequence which you consider equating to:

```md
[ ] -- 0% complete
[.] -- 1-33% complete
[o] -- 34-66% complete
[O] -- 67-99% complete
[X] -- 100% complete
```

If you do not like the sequence you can set your own using `g:vimwiki_listsyms` for example

```vim
let g:vimwiki_listsyms = '✗○◐●✓'
```

See `:help vimwiki-todo`

## Tables

Use `:VimwikiTable 5 3` to create a table with 5 columns and 2 rows

```
|   |   |   |   |   |
|---|---|---|---|---|
|   |   |   |   |   |
|   |   |   |   |   |
```

Press tab to advance to the next column, it auto formats as you go.

Press enter on the last row to create another row.

See `:help vimwiki-table`

## Diary

VimWiki diary makes it easy to create a daily entry. Type `<Leader>w<Leader>w` to create a new entry based on today's date. A `diary` subdirectory is created containing the wiki files. 

This [Calendar plugin](https://github.com/mattn/calendar-vim) works with the diary feature, allowing you to browse and create entries using a calendar interface.

Create a diary index page by navigating to the page using `:VimwikiDiaryIndex` and then automatically create entries list using `:VimwikiDiaryGenerateLinks` 

I find both commands a little tedious, so I create a `:Diary` command to navigate to the index page, and an autocommand to generate links each time the diary index is open.

```vim
command! Diary VimwikiDiaryIndex
augroup vimwikigroup
    autocmd!
    " automatically update links on read diary
    autocmd BufRead,BufNewFile diary.wiki VimwikiDiaryGenerateLinks
augroup end
```

<figure><asciinema-player src="/a/casts/vim/vimwiki-diary.cast" font-size="large" cols="65" rows="20"></asciinema-player><figcaption>VimWiki Diary</figcaption></figure>


## Search

Use `:VWS /term/` to search.

Use `:lopen` to see all results

