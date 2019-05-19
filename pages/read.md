---
title: Read
parent: 1497
template: page-tut.php
order: 11
---

# Read

Use `:read` command to read from an external sources into the current buffer. 

## Read from File

Use `:read FILENAME` to read the content of FILENAME into the current buffer.

## Read from Commands

Read can also insert results from external commands. Combine read with `:read ! [shell command]` to execute the shell command and insert the output into the current buffer.

An example I use for grabbing the salt for a WordPress config:

`:read ! curl --silent https://api.wordpress.org/secret-key/1.1/salt/`

<figure><asciinema-player src="/a/casts/vim/read1.cast" font-size="large" cols="58" rows="15"></asciinema-player><figcaption>Read from curl example</figcaption></figure>


## Bash Programming the Vim Way

I will often use the read command to grab a list of files to manipulate. I'm terrible at bash programming and often find it easier to do things the hard way like this:

<figure><asciinema-player src="/a/casts/vim/read2.cast" font-size="large" cols="58" rows="15"></asciinema-player><figcaption>Not bash programming</figcaption></figure>
