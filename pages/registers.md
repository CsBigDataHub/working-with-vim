---
title: Registers
parent: 1497
template: page-tut.php
order: 12
---

# Registers

Vim stores the list of yanked or deleted text in a set of registers. To see what is stored across all registers use the `:reg` command.

The `""` register has no name, it is most similar to the clipboard. Whatever is copied or deleted is placed in the `""` register automatically.

The numbered registers `0-9` keep a stack of recently copied or deleted text.

To paste an item from a register you use `"{reg}p`. For example, to paste an item from register `0`, you use: `"0p`

<span class="tip">💡</span> Use `"0p` for paste copied content that accidentally got replaced because of a delete after a copy. Deleted text automatically goes to `""` register. This replaces any copied text there. The original copied text is register `0` so use `"0p` to paste.

## Named Registers

You copy items directly to named registers [a-z] by prepending your yank command with the register name. For example, yanking a word to register `a` use `"ayw` and then `"ap` to paste.

If you use a capital letter, [A-Z], the same corresponding named register is used, but the content is appended to the register, not replaced.

<span class="tip">📄</span> Registers are stored in `~/.viminfo` and loaded each time vim starts. So registers will persist between sessions.

## System Clipboard

The `+` register is a special register for the system clipboard. You can copy from vim to your system, and paste from your system to vim.

Use `"+yy` to copy current line to the system clipboard, and `"+p` to paste from clipboard to vim buffer.

See `:help registers` for additional information about other special registers.


