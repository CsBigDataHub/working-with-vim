---
title: Recording
parent: 1497
template: page-tut.php
order: 15
---

# Recording and Playback

<span class="sidenote">See `:help recording`</span>

Recording in vim is similar to what other editors calls macros, it is a way to record and playback a set of commands. You record to a named register, in fact a recording is simply just that, saving the commands you type to the register.

Using `qa` will start recording to named register `a`. You will see in the bottom left corner `recording @a`.

You now perform the actions you want, and then when done press `q` to stop recording.

Replay back the commands using `@a`, this replays everything you did while recording.

Use `@@` to repeat the previous replay, you can combine with a count so `3@@` will repeat previous replay 3 times, or you can use `3@a` to repeat.

<figure><asciinema-player src="/a/casts/vim/recording.cast" font-size="large" cols="58" rows="15"></asciinema-player><figcaption>Recording example</figcaption></figure>

<span class="tip">💡</span>Your macro just duplicates your commands, so make sure you end/start at the right spot. Basically, you want to start all macros at the start of a line, and end at the start of the next line. This helps when repeating.


## Recording in Register

As mentioned above, your recordings are stored as commands in the registers. This allows you to see what is recorded by using the `:registers` command to view all registers. Additionally, you can copy a set of commands to a register and then replay them.

You can prove this by copying the text `oText from Register` to a register and replay. Note: the `o` is for append after, it is the command to enter into INSERT mode.

Here's the example yanking text to register using `"byy`, confirming the text is there, and then replaying using `@b`.

<figure><asciinema-player src="/a/casts/vim/recording2.cast" font-size="large" cols="58" rows="15"></asciinema-player><figcaption>Recording example</figcaption></figure>
