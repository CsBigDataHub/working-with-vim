---
title: Search
parent: 1430
template: page-tut.php
order: 8
---

# Search

A few different ways to search within a single buffer.


### Quick Search

<span class="sidenote">See `:help *`</span>
Use `*` and `#` to navigate to the word under the cursor, `*` forward and `#` backwards. I'll use this to check the spelling of variables, by using `*` on a variable it highlights all the words spelled the same. A nice quick way to check for misspellings.

<!-- wp:video {"autoplay":false,"id":1332,"loop":false,"muted":false,"src":"https://mkaz.blog/wp-content/uploads/2019/03/vim-star-nav.mp4"} -->
<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-star-nav.mp4"></video><figcaption>Quick Search Examples</figcaption></figure>
<!-- /wp:video -->



### Regex Motions

Use `/term` to move forward to next "term", and use `?term` to move backwards to previous "term".

<span class="sidenote">See `:help pattern-searches`</span>

You can combine with delete and yank, and any other action. For example: `d/apple` will delete from current spot to the string apple. Vim highlights the words to show and you press enter to confirm.

I don't use the delete or copy features with regex, but do use frequently to navigate around.

#### Remove Highlight

Search results remain highlighted after a search, the following maps `<Leader><Space>` to unhighlight.

```
" Unhighlight Search using ,SPC
nmap <silent> <Leader><Space> :nohlsearch<CR>
```

You can also try out the [vim-slash plugin](https://github.com/junegunn/vim-slash) which clears highlighting when cursor is moved.

I setup the command to clear, but since installing vim-slash plugin, it ends up clearing most of the time, so the plugin may be all you need.
