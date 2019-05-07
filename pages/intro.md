---
title: Intro
parent: 1497
template: page-tut.php
order: 0
---

# Introduction

It helps to understand a few terms and structure of Vim, as they will be used throughout.

First, a **buffer** is a file loaded into memory for editing. The stored file is not changed, this requires you to save (or write) the file. You may also have an empty buffer unrela

A **window** is a viewport onto a buffer. There is always one window and one buffer, typically they are 1:1, one buffer open in one window.

As you'll see you can have multiple buffers and/or multiple windows open at the same time. See the [Buffers](/working-with-vim/buffers/) and [Windows](/working-with-vim/windows/) sections for more on each.

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

As you can see, there are numerous ways to exit. I find using either `ZZ` or `:x` the preferred way because it will not change the file's modified time if no changes were made.

Vim tries to save you from yourself, if there are multiple files open with changes, it will not exit. You must explictly use one of the `!` commands or save the changes first.

