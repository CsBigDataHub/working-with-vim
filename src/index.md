---
title: Working with Vim
date: 2019-03-01
---

# Working with Vim

A set of vim tips and features I use often, the goal is to help you improve your fluency with vim. I initially titled this post "Intermediate Vim" but experiences vary and non-linear, so what may be intermediate for some is basic or advanced for others.

A basic understanding of vim is a prerequisite, I try to explain everything but assume some base knowledge.  At minimum you should know moves (`h,j,k,l`), entering INSERT mode (`i,a`), or escaping to NORMAL mode (`esc`), and how to quit (`:q`).

The program `vimtutor` is a great way to learn the basics of vim. It is an interactive tutorial in vim walking through vim. Depending on your OS and how vim is installed, you may need to install the full vim package. Ubuntu for example ships with a tiny vim setup, you need to run `apt install vim`. If you use Neovim, run `:Tutor` inside the editor.

In the videos, the big yellow text in the bottom right are the key presses I do. They are overlayed using <a href="https://gitlab.com/wavexx/screenkey">screenkey</a> and not part of vim. I recorded videos so you can start/stop at will and see what is happening.


## Working Mode

First up, I don't really like telling people what to do, no vim shaming here. I use arrow keys. Use arrows keys. They are great keys with labels and everything. I do have one recommendation, <strong>make NORMAL mode your default mode</strong>. I mash the Esc key about hundred times a minute. Every time I finish a sentence. Escape. There is a reason it is called NORMAL mode, it is the mode where you can do everything fancy.

INSERT mode is just typing text, any editor can do that.

Be NORMAL.


### Visual Mode

<span class="sidenote">When I use a capital letter, you use a capital letter. Capital. Capital.</span>

You can highlight multiple lines using `V`.  Press `V` in NORMAL mode, and the whole line will be highlighted and you will be in VISUAL mode, as you move up or down it will highlight other lines.

The `shift-v`, aka capital V, is VISUAL LINE mode, selecting whole lines at once.

<span class="sidenote">I capitalize the modes because vim does, I'm not shouting them.</span>

If you type `ctrl-v` it is VISUAL BLOCK mode, it selects by characters. Press `ctrl-v` and move around to select things, try left or right movements to see by character. You can also use `ctrl-v` to do fancy multi-cursor things, see video example below.

Psst, don't tell the purists, but if you `set mouse=a` you can use your mouse to highlight things too.

VISUAL mode is pretty powerful, I use it frequently since it provides feedback seeing what is selected, and then unselected after the action.


<!-- wp:video {"autoplay":false,"id":1452,"loop":false,"muted":false,"src":"https://mkaz.blog/wp-content/uploads/2019/03/visual-mode-exs.mp4"} -->
<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/visual-mode-exs.mp4"></video><figcaption>Visual Mode example</figcaption></figure>
<!-- /wp:video -->

<!-- wp:proximo/tips -->
<p class="wp-block-proximo-tips"><i class="proximo-tips-icon">💡</i><span>After performing an action in VISUAL MODE the selection is no longer highlighted. Use `gv` to automatically reselect the area previously highlighted.</span>
<!-- /wp:proximo/tips -->


## Quickies

A couple of quick tips I use all the time, you might already know these, consider it a warm up. One way to go through this tutorial is open vim in another window and follow along trying things out as you go. It is like learning a language, repetition and practice helps.

First up, the most common actions are `y` for yank (copy), `d` for delete, and `p` for put (paste).

### Copy / Delete Lines

Deleting a full line is so common, the `dd` shortcut exists.

If you delete a line and want to paste it elsewhere, use `p` to paste.

Likewise, you can copy a line using `yy` shortcut.

### Merge lines

Use `J` to merge lines together. If you press `J` with nothing highlighted, it will remove the current line ending and white-space bringing the next line up. If multiple lines are highlighted, pressing `J` will merge them all into a single line.

### Wrap Lines at Length

Use `gq` to wrap lines to a specified length defined by `textwidth`. If the `textwidth` option is not set the default is 79. I use this daily in commit messages to fit within 80 characters. To use, just highlight the lines you want and then type `gq`

### Delete to End of Line

Did you know `D` deletes from your cursor to end of line? It does. Try it. It's wonderful. I use this all the time.

You have to type `d^` to do the opposite and delete to the front of the line, I almost never do this, probably why there is a shortcut for the previous delete and not this one.

### Repeat That

Press `.` to repeat the last command.

If you start with a number and then command it executes the command that many times. For example, if you want to delete three lines, `3dd`

<!-- wp:video {"autoplay":false,"id":1331,"loop":false,"muted":false,"src":"https://mkaz.blog/wp-content/uploads/2019/03/vim-quickies.mp4"} -->
<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-quickies.mp4"></video><figcaption>Quickies example</figcaption></figure>
<!-- /wp:video -->


### Undo / Redo

Use `u` for undo, and `ctrl-r` for redo.

## Help Yourself

Vim has extensive documentation on every command and feature. Type `:help [command]` to see help for any command. For example, `:help gg` will explain what the `gg` command does.

Help opens in a new window split horizontally, see Windows section below for working with windows. The two items I do most is `ctrl-w o` so it is the only window (not split), and `ctrl-w c` to close. Help is just a read-only buffer, so you can navigate, highlight, copy, paste, the same as any other buffer.


## The Tao of Vim

The underlying principle of Vim is the action-motion pair, the language equivalent is a sentence with a verb-noun pair. You perform an action on a subject, for example delete a line.

You can create action-motion pairs basically in two ways.

First, in non-Visual mode, ie. NORMAL mode, you specify the action first and then motion. Like the delete to beginning of the line example above. You type `d` for delete action and then `^` as the motion for beginning of the line.

If I just type `^` with no action, the cursor moves to the beginning of the line. Move is the default action.

The second way of defining a pair is VISUAL mode, except you do the opposite. You specify the noun (motion) part first by highlighting, and then perform the action on what is highlighted.

For example, type `gg` to move to the top of the file. `shift-v` to enter VISUAL LINE Mode and then `G` will move to end of file selecting all the lines. With the subject highlighted, you can use `d`or `y` to delete or copy.

I do this all the time to copy from one buffer to another. There might be a shortcut, but then I would need to remember it as a shortcut. Knowing how to highlight and move is less to remember, since it is the base of knowledge.

Note: You can perform this same action without using VISUAL mode by using `ggyG` but I tend to highlight. By selecting, I can see what is happening, what part highlighted and then get feedback when the action is performed.

### Basic Motions

```vim
w        " Forward to next word
b        " Backward to start of word
e        " Forward to end of word
gg       " Top of file
G        " Bottom of file
fx       " Forward to 'x'
Fx       " Backward to 'x'
_        " Current line (underscore)
```

Practice the basic motions by just pressing the motion character, while in NORMAL mode, the cursor will move. So pressing `w` moves the cursor forward to the next word.

If you put an action first, it will perform that action on the motion. For example `dw` it will delete to the next word, including the space.

If you start with `v` it will highlight based on the motion in VISUAL mode, so `ve` will highlight to the end of the word.

If you `p` paste with something highlighted, it will replace the highlighted section.

<!-- wp:video {"autoplay":false,"id":1386,"loop":false,"muted":false,"src":"https://mkaz.blog/wp-content/uploads/2019/03/copy-vis-paste.mp4"} -->
<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/copy-vis-paste.mp4"></video></figure>
<!-- /wp:video -->


### Text Object Selection

<span class="sidenote">See `:help text-object`</span>

Vim can operate on text based on its objects and structure. The inner object `i` is quite useful to select chunks of text inside parentheses, brackets, quotes, or other pairs.

For example, to copy the arguments in a function use `yi(`

If you want delete a block of code in a `{ ... }`with your cursor inside the block, type `di{`

This also works for text in quotes, if you typed `yi"` it will copy the word without the quotes. If you want copy to include the quotes use `a` instead of `i`, this works for all the examples above.

<!-- wp:video {"autoplay":false,"id":1333,"loop":false,"muted":false,"src":"https://mkaz.blog/wp-content/uploads/2019/03/vim-selection.mp4"} -->
<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-selection.mp4"></video><figcaption>Selection example</figcaption></figure>
<!-- /wp:video -->

<strong>Extra</strong>: The inner selection motions work with words `w`, sentences `s`, and paragraphs `p`. So if the cursor is in the middle of a word, sentence, or paragraph you can use `i` paired with the motion and it will select the full object. This is so you don't need to first navigate to the start of a word to select the whole word.


### Quick Search

<span class="sidenote">See `:help *`</span>
Use `*` and `#` to navigate to the word under the cursor, `*` forward and `#` backwards. I'll use this to check the spelling of variables, by using `*` on a variable it highlights all the words spelled the same. A nice quick way to check for misspellings.

<!-- wp:video {"autoplay":false,"id":1332,"loop":false,"muted":false,"src":"https://mkaz.blog/wp-content/uploads/2019/03/vim-star-nav.mp4"} -->
<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-star-nav.mp4"></video><figcaption>Quick Search Examples</figcaption></figure>
<!-- /wp:video -->


### Navigation Marks

<span class="sidenote">See `:help marks`</span>
Navigation marks allow you to mark spots in your buffer and jump back and forth between marks. This is useful if you find yourself moving around a buffer, say for table of contents, imports, or constructor.

```vim
ma       " mark spot label it a
`a       " jump to spot labeled a
```

Vim automatically creates some marks:

```vim
``       " jump back to previous position
`.       " jump to last spot edited
```

Use `:marks` command to see all available marks.

<span class="tip">💡</span>You can mark spots in different files by using capital letter, and jump back and forth. Vim will even open the file in a buffer if closed. See buffer video below for an example.


### Regex Motions

Use `/term` to move forward to next "term", and use `?term` to move backwards to previous "term".

<span class="sidenote">See `:help pattern-searches`</span>

You can combine with delete and yank, and any other action. For example: `d/apple` will delete from current spot to the string apple. Vim highlights the words to show and you press enter to confirm.

I don't use the delete or copy features with regex, but do use frequently to navigate around.


## Command-line Mode

You enter into command-line mode using `:`


### Search and Replace

<span class="sidenote">See `:help substitute`</span>

Substitute allows you to search and replace using regular expressions. The command `s/find/replace/g` will replace "find" with "replace", the `s` is for substitute, the `g` (global) option replaces every occurrence in a line, without the `g` it will only replace the first occurrence in a line.

Prefix the command with the range to work on, if no range is specified it will only search and replace on the current line.


<span class="sidenote">The space between range and `s` is not necessary, but I find it more legible.</span>

Use `%` to search and replace across the whole document. `:% s/find/replace/g`

Specify a line number range using `:137,140 s/find/replace/g` will replace all "find" with "replace" between lines 137 and 140.

You can also define the range using VISUAL mode. First highlight the area you want and then type `:` to go into command-line mode. Vim will automatically insert `'&lt;,'&gt;` which is its magical incantation to work over the selection, leave it there, and type your substitute command `s/find/replace`



Besides search and replace, you can use `g/find/d` to delete all lines that match find, or `v/find/d` to delete all lines that do not match find.


<!-- wp:video {"autoplay":false,"id":1348,"loop":false,"muted":false,"src":"https://mkaz.blog/wp-content/uploads/2019/03/vim-search.mp4"} -->
<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-search.mp4"></video><figcaption>Search examples</figcaption></figure>
<!-- /wp:video -->

<!-- wp:heading {"level":3} -->
### Read



Another useful command is `:read` which can read from external sources into the current buffer. Use `:read FILENAME` to read the content of FILENAME into the current buffer.



You can also combine read with `:read ! [shell command]` which will execute the shell command and insert the output into the current buffer.



An example I use this for frequently is grabbing the salt for a WordPress config:



`:read ! curl --silent https://api.wordpress.org/secret-key/1.1/salt/`


<!-- wp:video {"autoplay":false,"id":1334,"loop":false,"muted":false,"src":"https://mkaz.blog/wp-content/uploads/2019/03/vim-curl.mp4"} -->
<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-curl.mp4"></video><figcaption>Read from curl example</figcaption></figure>
<!-- /wp:video -->


This is also quite useful for reading a list of files in and manipulating. I'm terrible at bash programming and often find it easier to do things the hard way like this:


<!-- wp:video {"autoplay":false,"id":1335,"loop":false,"muted":false,"src":"https://mkaz.blog/wp-content/uploads/2019/03/vim-notbash.mp4"} -->
<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-notbash.mp4"></video><figcaption>Not bash programming</figcaption></figure>
<!-- /wp:video -->


## Registers



Vim stores the list of yanked or deleted text in a set of registers. To see what is stored across all registers use `:reg` command.



The numbered registers `0-9` keep a stack of recently copied or deleted text.



To paste an item from register `0`, you would use: `"0p`


<!-- wp:proximo/tips -->
<p class="wp-block-proximo-tips"><i class="proximo-tips-icon">💡</i><span>When copying and pasting, you might forget to delete something, then when you delete it replaces what you just copied. The original item  copied is still there, in register `0`. </span>
<!-- /wp:proximo/tips -->


Additionally, you can copy items directly to a labeled register by prepending your yank command with `"a` for register label `a`. For example, yanking a word use `"ayw` and then `"ap` to paste. You can use this for up to 26 labeled registers, each letter a-z.



The `+` register is a special register for the system clipboard. You can copy from vim to your system, and paste from your system to vim.



Use `"+yy` to copy current line to the system clipboard, and `"+p `to paste from clipboard to vim buffer.



See `:help registers` for additional information about other special registers.



## Buffers



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


## Windows

As mentioned above windows are viewports into buffers. So a window is a different editing pane. There is always one main window, but you can also have multiple windows at the same time. Multiple windows can be the same or different buffers, so you can have the same buffer open in two different windows.


```vim
:split     " Horizontal split, current buffer
:vsplit    " Vertical split, current buffer
:new       " Horizontal split, new buffer
:vnew      " Vertical split, new buffer

ctrl-w s   " Horizontal split current buffer
ctrl-w v   " Vertical split current buffer
ctrl-w n   " Horizontal split, new buffer

ctrl-w q   " Quit window, closes buffer
ctrl-w c   " Close window, leave buffer
ctrl-w o   " Only one window, closes down to just one
```

To navigate between open windows use `ctrl-w [hjkl]` or `ctrl-w [arrows]` mapping to the same directions used to navigate.

I rarely use multiple windows open at the same time, I'm  comfortable bouncing around buffers that I tend not to need more things on the screen at the same time.

A tab page is a collection of windows. So tabs may be useful if you rely on multiple different window layouts. I rarely use windows, so tabs are just too much for me. If interested, you can learn more about tabs using `:help tab-page`


<span class="tip">💡</span> Tab pages are nice to open help in. This will open help in a full window, instead of a split. Prefix with `:tab` first, for example `:tab help tab-page`<br><br>You can use `:tabclose` or `ctrl-w c` to close, the latter closes since closing the last window in a tab page, closes the tab.


## Misc Actions

Once you get a handle on the motions, then it is a matter of learning additional actions to pair with them. Here are a couple of useful actions.


### Uppercase &amp; Lowercase

Use `gu{motion}` for lowercase, use `gU{motion}` for uppercase, or use `g~{motion}` to toggle case. So `guiw` will switch the current word to lowercase, or `g~_` will toggle the case of each character on the current line.


### Indent

The brackets `&gt;` and `&lt;` will shift the line one `shiftwidth` length to the right, or left. These can also be paired with VISUAL mode , ranges, and motions.

For example, use `shift-v` to select a line, use arrows or other motions to expand the range, and then type `&gt;` or `&lt;` to shift the lines.

Use `&gt;&gt;` and `&lt;&lt;` to shift using a count. For example `5&gt;&gt;` will shift 5 lines once to the right. If you want to shift more use `.` to repeat the command.

See `:help shift-left-right`


### Formatting

The `=` command will automatically format text based on internal formatting rules for the language, or as defined by a plugin. The typical way I use is highlight the section I want using VISUAL mode and then pressing `=` to format.

## Recording and Playback

<span class="sidenote">See `:help recording`</span>

Recording in vim is similar to what other editors calls macros, it is a way to record and playback a set of commands. You record to a named label, similar to marks, or registers, .

Using `qa` will start recording to label `a`. You will see in the bottom left corner `recording @a`.

You now perform the actions you want, and then when done press `q` to stop recording.

You replay back the commands using `@a`, use a count if you want to replay multiple times, for example `3@a`.

<!-- wp:video {"autoplay":false,"id":1337,"loop":false,"muted":false,"src":"https://mkaz.blog/wp-content/uploads/2019/03/vim-macros.mp4"} -->
<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-macros.mp4"></video><figcaption>Recording example</figcaption></figure>
<!-- /wp:video -->


<span class="tip">💡</span>Your macro just duplicates your commands, so make sure you end/start at the right spot. Basically, you probably want to end all macros at the start of the next line.

## Configuration

Since everyone asks, I use <a href="https://sourcefoundry.org/hack/">Hack font</a>, <a href="https://github.com/mhartington/oceanic-next">Oceanic Next</a> colorscheme, and <a href="https://github.com/vim-airline/vim-airline">Airline</a> for the fancy status bar.

You can check out my <a href="https://github.com/mkaz/dotfiles/blob/master/extras/nvim/init.vim">.vimrc in my dotfiles</a> repo. I actually use neovim, so it is init.vim. I don't really recommend just copying and pasting the whole thing, it ends up being personal preferences anyways.

I do recommend using <a href="https://github.com/junegunn/vim-plug">vim-plug</a> to manage plugins, it makes it easy to install, upgrade, and remove.

My one great tip from my configuration, which credit to whoever I picked it up from years ago, this saves me so many times.


```vim
" :w!! to save with sudo
ca w!! w !sudo tee >/dev/null "%"
```

When you open a file and don't have write permissions, you can call `:w!!` and it will auto sudo the file for you. Saves me practically every time I edit a system file.

For more, see my article <a href="https://mkaz.blog/code/unix-is-my-ide/">Unix is my IDE</a> for an explanation on how I setup vim using fzf and ripgrep for advanced searching, including a quick way I switch buffers using fzf.

