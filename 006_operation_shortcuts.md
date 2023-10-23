# Operation shortcuts

We've been heavily using the "operator + text object" syntax to make changes to our code.

Vim has a shortcut where typing the operation twice or using an upper cased version
applies the operator on a default text object (usually related to the current line).

For example:

- `yy` and `Y` yank the current line
- `D` deletes from the cursor to the end of the line (so part of a line)
- `dd` deletes the entire line
- `C` mirrors `D` in that it deletes to the end of the line then puts you in insert mode
- `cc` kinda mirrors `dd` in that it clears the line (doesn't delete it entirely) then puts you in insert mode
- `!!` will use the current line as input to the external program (and then you enter your program)
- `gUgU` will uppercase the whole line (`gUU` is a shortcut)
- `gugu` and `guu` are the lowercase equivalent

These are handy particularly because vim doesn't come with a simple text object for the current line (which is odd).
You have to resort to motions, highlighting or using the shortcuts above.

There is a nice plugin `kana/vim-textobj-line` which adds the `il` (inside line) and `al` (around line) text objects.
More on that in [kata 36](036_line_and_buffer_text_objects.md)!

# Exercises

## Exercise 1

Remember these guys? They're one line inputs so we can use `!!` to execute them:

- move your cursor to anywhere on the json line
- do `!!jq .<enter>`
- move your cursor to anywhere on the python print statement
- do `!!python`

```json
{
  "fire": [
    "joban",
    "joey-jo-jo-junior-shabadoo"
  ],
  "dontFire": [
    "zij",
    "james",
    "jonathan"
  ]
}
```

```python
2497
```

## Exercise 2

Duplicate each of the lines below.

- move your cursor to anywhere on "Line 1" 
- do `Yp` (yank the current line then paste it below)
- move your cursor to anywhere on "Line 2"
- do `yyp` (yank the current line then paste it below)
- move your cursor to anywhere on "Line 3"
- do `.`
- (whoops! That pasted another copy of line 2 as "paste 'Line 2'" was our last change)
- do `u`
- do `Yp` or `yyp` again

```
Line 1
Line 1
Line 2
Line 2
Line 3
Line 2
```

## Exercise 3

Completely delete all the lines that start with "Boban"
and crop the lines with "Boban" in the middle by removing from "Boban" to the right.

- move your cursor to "Boban is supreme"
- do `dd`
- (now your cursor should be on the next line)
- move your cursor to the space just before "Boban"
- do `D`
- move your cursor to the next line down
- do `dd`
- (now your cursor should be on the last line)
- move your cursor to the space just before "Boban"
- do `D`

```
We ate a super supreme. Boban did too.
We saw a python eat someone. Boban is gone.
```

# Summary

Vim has a lot of these seemingly cryptic ad-hoc shortcuts,
but there is actually a basic pattern to them.

Once you understand the pattern it becomes a lot easier to remember them.

Today's kata showed that for most operators, when they're used in the uppercase or repeated form,
they tend to operate on the current line or something related to it.
