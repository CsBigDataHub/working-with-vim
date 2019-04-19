---
title: Registers
date: 2019-03-12
---

# Registers

Vim stores the list of yanked or deleted text in a set of registers. To see what is stored across all registers use `:reg` command.

The numbered registers `0-9` keep a stack of recently copied or deleted text.

To paste an item from register `0`, you would use: `"0p`

<span class="tip">💡</span>When copying and pasting, you might forget to delete something, then when you delete it replaces what you just copied. The original item  copied is still there, in register `0`.

Additionally, you can copy items directly to a labeled register by prepending your yank command with `"a` for register label `a`. For example, yanking a word use `"ayw` and then `"ap` to paste. You can use this for up to 26 labeled registers, each letter a-z.

The `+` register is a special register for the system clipboard. You can copy from vim to your system, and paste from your system to vim.

Use `"+yy` to copy current line to the system clipboard, and `"+p `to paste from clipboard to vim buffer.

See `:help registers` for additional information about other special registers.

