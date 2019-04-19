---
title: Recording
date: 2019-03-16
---

# Recording and Playback

<span class="sidenote">See `:help recording`</span>

Recording in vim is similar to what other editors calls macros, it is a way to record and playback a set of commands. You record to a named label, similar to marks, or registers, .

Using `qa` will start recording to label `a`. You will see in the bottom left corner `recording @a`.

You now perform the actions you want, and then when done press `q` to stop recording.

You replay back the commands using `@a`, use a count if you want to replay multiple times, for example `3@a`.

<!-- wp:video {"autoplay":false,"id":1337,"loop":false,"muted":false,"src":"https://mkaz.blog/wp-content/uploads/2019/03/vim-macros.mp4"} -->
<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-macros.mp4"></video><figcaption>Recording example</figcaption></figure>
<!-- /wp:video -->


<span class="tip">💡</span>Your macro just duplicates your commands, so make sure you end/start at the right spot. Basically, you probably want to end all macros at the start of the next line.
