#### Neovim Keyboard Shortcuts Cheat Sheet

#### Quadrant 1: Save and Exit

- `:e filename` - Open file for editing
- `:w` - Save current buffer to disk
- `:w filename` - Save current buffer to filename
- `:q` - Close the current window
- `:wq` - Save and close the current window
- `:q!` - Close the current window without saving
- `:wa` - Save all open buffers to disk

#### Quadrant 2: Moving and Jumping

- `h, j, k, l` - Move cursor left, down, up, right respectively
- `w` - Move cursor to the start of the next word
- `b` - Move cursor to the start of the previous word
- `0` - Move cursor to the start of the line
- `$` - Move cursor to the end of the line
- `gg` - Move cursor to the start of the file
- `G` - Move cursor to the end of the file
- `Ctrl + f` - Page down
- `Ctrl + b` - Page up
- `)` - Move forward by sentence
- `(` - Move backward by sentence
- `}` - Move forward by paragraph
- `{` - Move backward by paragraph

#### Quadrant 3: Editing

- `i` - Enter insert mode
- `a` - Append text after the cursor
- `o` - Open a new line below the current line and enter insert mode
- `O` - Open a new line above the current line and enter insert mode
- `u` - Undo the last operation
- `Ctrl + r` - Redo the last operation
- `dd` - Delete the current line
- `yy` - Copy the current line
- `p` - Paste after the cursor
- `P` - Paste before the cursor

#### Quadrant 4: Searching and Visual Mode

- `/pattern` - Search forward for a pattern
- `?pattern` - Search backward for a pattern
- `n` - Repeat the last search in the same direction
- `N` - Repeat the last search in the opposite direction
- `v` - Enter visual mode
- `V` - Select entire lines
- `Ctrl + v` - Select rectangular blocks
- `y` - Copy selected text
- `d` - Delete selected text
- `o` - Move to the other end of the selected text
