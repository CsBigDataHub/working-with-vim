---
title: Completions
parent: 1430
template: page-tut.php
order: 17
---

## Completions

### Built-in Completion

Vim has a powerful set of auto completion tools already built-in.

ctrl-p in insert mode for autocomplete

ctrl-x ctrl-p with context
ctrl-x ctrl-l full line with context


### Snippets

I use the [Ultisnips plugin](https://github.com/SirVer/ultisnips) to provide all my snippet needs. Snippets have replaced templates for me. Previously I setup a template file to load if a new empty file, for example a new HTML file would load a stubbed out html-head-body set of tags.

However, setting it up automatically could get annoying when doing temporary things. Plus it was fragile when template didn't exist. So now using snippets it is easily to manually insert the template I want.

Add plugin:
```
Plug 'sirver/ultisnips'
```

My configuration since I use Neovim:
```
let g:UltiSnipsSnippetDirectories=[$HOME.'/.config/nvim/UltiSnips']
let g:UltiSnipsUsePythonVersion = 3
```

You can see the snippets I have defined in my dotfiles repo here.


[1]: http://georgebrock.github.io/talks/vim-completion/

