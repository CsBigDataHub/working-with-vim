---
title: VimWiki
parent: 1430
template: page-tut.php
order: 22
---

# VimWiki

[VimWiki](https://github.com/vimwiki/vimwiki) is a powerful plugin that enables Vim to be your own personal wiki. It is a great tool to keep track of notes, lists, or just about anything.

It is hard to describe the usefulness of VimWiki, since it just sounds like writing text in a text editor. However, the convenience to always have a scratch area to write and collect stuff I've found to be extremely valuable.

## Install and Configuration

Install the plugin using `vim-plug`

```vim
Plug 'vimwiki/vimwiki'
```

I configure VimWiki to a specific directory which I sync across devices. I set the syntax to markdown and some formatting that I prefer for the wiki.

```vim
" Vim Wiki
let g:vimwiki_list = [{'path': '~/Sync/wiki/', 'syntax': 'markdown'}]
au FileType vimwiki setlocal shiftwidth=6 tabstop=6 noexpandtab
```

## Usage

The basic usage is typing `<Leader>ww` opens your index file, one will be created for you if it does not already exist.

This can be an instant scratch pad to take whatever notes that you want. You can create additional links to new wiki files by insert `[[LinkText]]` or by placing your cursor over a word in NORMAL mode and pressing enter.

Once a link is created, navigate to the new page by placing your cursor over the word and pressing enter. This will open (create if needed) the linked page.

You can create pages for any list, tasks, info, notes, or whatever you want.

## Todo Lists

VimWiki has a few built-in types and features. One of which is a todo list features. You can create a list of items that can be checked off using the syntax:

```
- [ ] Write Vim Lessons
- [ ] Edit Vim Lessons
- [ ] Publish
```

You can add a checkbox using `ctrl-<Space>`, use `gl<Space>` to remove checkbox.

To toggle an item complete use `ctrl-<Space>` with your cursor on the line you want to toggle. Todo lists also work for nested items, simply indent the item. Vim folding works with nested lists. Toggling will also mark all sub-items.

Maybe an item is not all the way complete, use `gln` to toggle forward completion levels, and use `glp` to toggle backwards completion levels.

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

VimWiki supports diary entries, typing `<Leader>w<Leader>w` creates a new entry based on today's date. This makes it easy to create a new entry to jot down notes to.


