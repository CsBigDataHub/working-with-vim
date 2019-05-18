---
title: Read
parent: 1497
template: page-tut.php
order: 11
---

# Read

Another useful command is `:read` which can read from external sources into the current buffer. Use `:read FILENAME` to read the content of FILENAME into the current buffer.



You can also combine read with `:read ! [shell command]` to execute the shell command and insert the output into the current buffer.



An example I use this for frequently is grabbing the salt for a WordPress config:



`:read ! curl --silent https://api.wordpress.org/secret-key/1.1/salt/`


<!-- wp:video {"autoplay":false,"id":1334,"loop":false,"muted":false,"src":"https://mkaz.blog/wp-content/uploads/2019/03/vim-curl.mp4"} -->
<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-curl.mp4"></video><figcaption>Read from curl example</figcaption></figure>
<!-- /wp:video -->


This is also quite useful for reading a list of files in and manipulating. I'm terrible at bash programming and often find it easier to do things the hard way like this:


<!-- wp:video {"autoplay":false,"id":1335,"loop":false,"muted":false,"src":"https://mkaz.blog/wp-content/uploads/2019/03/vim-notbash.mp4"} -->
<figure class="wp-block-video"><video controls src="https://mkaz.blog/wp-content/uploads/2019/03/vim-notbash.mp4"></video><figcaption>Not bash programming</figcaption></figure>
<!-- /wp:video -->

