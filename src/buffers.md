---
title: Buffers
date: 2019-03-13
---

# Buffers

Buffers in vim are the in-memory text of files. A window is a viewport on a buffer. You can switch between open buffers, which works similar in concept to tabs in other editors. Vim does have a concept of tabs too, but they are slightly different, more in Windows section below.

I generally keep it pretty simple and just use buffers as my multiple files open at the same time. Here is a post about <a href="https://joshldavis.com/2014/04/05/vim-tab-madness-buffers-vs-tabs/">Buffers vs Tabs</a>, and the author agrees just using buffers are easier.

My main reason is if you specify multiple files on the command-line, or use `:ed FILE` to open additional files, they are opened in extra buffers. Buffers seem to be the default mode, so it is what I learned.


```vim
:buffers  " Show open buffers
:bn       " Next buffer in list
:bp       " Previous buffer in list
:b#       " Last buffer visited, actual # sign
:b1       " Open buffer 1
```

<!-- wp:video {"autoplay":false,"id":1336,"loop":false,"muted":false,"src":"https://mkaz.blog/wp-content/uploads/2019/03/vim-buf-mark.mp4"} -->
<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-buf-mark.mp4"></video><figcaption>Buffers example</figcaption></figure>
<!-- /wp:video -->

#### Buffer Navigation

To make buffer navigation easier, I map `<Leader>3` to jump back to last buffer, and `<Leader>n` to navigate to next buffer, so in my case this is `,3` and `,n`. I also map `;` to open the buffer list to select a buffer.

```vim
" Buffer Navigation
nmap <Leader>3 :b#<CR>	" previous buffer
nmap <Leader>n :bn<CR>	" next buffer
nnoremap Q :bd!<CR>	    " close buffer
nmap ; :Buffers<CR>		" browse buffers
```
For more, see my article <a href="https://mkaz.blog/code/unix-is-my-ide/">Unix is my IDE</a> for an explanation on how I setup vim using fzf and ripgrep for advanced searching, including a quick way I switch buffers using fzf.
