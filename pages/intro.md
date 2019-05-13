---
title: Intro
parent: 1497
template: page-tut.php
order: 0
---

# Introduction

First, let's define a few terms around the structure of Vim. By understanding the words Vim uses, helps you understand the shortcuts and commands related. 

A **buffer** is a file loaded into memory for editing. In other editors or programs you'd call it a file, or open file, but in Vim parlance it is called a buffer. The actual file on the file system is not changed until you to save (or write) the file. 

A **window** is a viewport onto a buffer. There is always at least one window and one buffer in Vim, typically they are 1:1, one buffer open in one window. When you start Vim without specifying a file, it is an empty buffer.

You can also have multiple buffers and/or multiple windows open at the same time. These are covered in the [Buffers](/working-with-vim/buffers/) and [Windows](/working-with-vim/windows/) sections for more on each.

## Exiting Vim

There are a meme of jokes about exiting Vim, the truth is once you grok using vim, you don't want to exit. 🙂

`:w`
: Write current file

`:w [file]`
: Write buffer to `file`

`:q`
: Quit

`:wq`
: Write current file and Quit

`:x` or `ZZ`
: Write if changes made and Quit

`:q!` or `ZQ`
: Quit without save

`:wqa`
: Save all changed files, and quit

`:qa!`
: Quit all files, without save

Yes, there are numerous ways to exit. I find using either `ZZ` or `:x` my preferred way because it will not change the file's modified time if no changes were made.

Vim will try to protect you from yourself, if there are multiple files open with changes, it will not exit. You must explictly use one of the `!` commands or save the changes first.

