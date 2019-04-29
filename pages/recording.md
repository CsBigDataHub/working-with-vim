---
title: Recording
parent: 1430
template: page-tut.php
order: 15
---

# Recording and Playback

<span class="sidenote">See `:help recording`</span>

Recording in vim is similar to what other editors calls macros, it is a way to record and playback a set of commands. You record to a named label, similar to marks, or registers, .

Using `qa` will start recording to label `a`. You will see in the bottom left corner `recording @a`.

You now perform the actions you want, and then when done press `q` to stop recording.

You replay back the commands using `@a`, this replays everything you did while recording.

Use a count if you want to replay multiple times, for example `3@a`.

<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-macros.mp4"></video><figcaption>Recording example</figcaption></figure>

<span class="tip">💡</span>Your macro just duplicates your commands, so make sure you end/start at the right spot. Basically, you want to start all macros at the start of a line, and end at the start of the next line. This helps when repeating.

