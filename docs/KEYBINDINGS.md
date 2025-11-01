# Key Bindings

## Quick Jump

- [Vim Bindings](#vim-bindings)
  - [Normal Mode](#normal-mode)
    - [Editing and File Management](#editing-and-file-management-stuff)
    - [LSP](#lsp-stuff)
    - [Harpoon](#vscode-harpoon)
  - [Visual Mode](#visual-mode)
    - [Moving and Replacing Text](#moving-and-replacing-text)
    - [Wrapping Text With Enclosing Punctuation](#giving-text-punctuation-hugs)
- [VSCode Bindings](#vscode-bindings)
  - [Group Navigation](#navigating-panes-like-a-window-manager)
  - [Moving Files Between Groups](#moving-files-around-the-panes)

## Vim Bindings

### Normal Mode

#### Editing and file management stuff

- `J`: Join lines while keeping the cursor in place
- `<C-u>`: Scroll up half a page, keeping cursor centered
- `<C-d>`: Scroll down half a page, keeping cursor centered
- `n`: Search next occurrence, center view on match
- `<leader>s`: Find and replace current word under cursor
- `<leader>ff`: Open a file by quick searching the workspace
- `<leader>fs`: Search for a string in the workspace

#### LSP stuff

- `gd`: Go to definition
- `gr`: Find Usages
- `K`: Hover information
- `<leader>r`: Rename all instances of the symbol under cursor

#### VSCode-Harpoon

- `<leader>a`: Add current file to Harpoon
- `<C-t>`: Toggle Harpoon quick menu
- `<C-q>`: Navigate to 1st file in Harpoon list
- `<C-w>`: Navigate to 2nd file in Harpoon list
- `<C-e>`: Navigate to 3rd file in Harpoon list
- `<C-r>`: Navigate to 4th file in Harpoon list

### Visual Mode

#### Moving and Replacing Text

- `<Tab>`: Indents selected lines
- `<S-Tab>`: Outdents selected lines
- `<leader>p`: Paste over selected text without changing copy buffer
- `<leader>y`: Yank selection to system clipboard
- `J`: Move selected block down
- `K`: Move selected block up

#### Giving Text Punctuation Hugs

- `"`: Wrap selected text with quotation marks "${TEXT}"
- `'`: Wrap selected text with single quotes '${TEXT}'
- `` ` ``: Wrap selected text with backticks \`${TEXT}\`
- `[`: Wrap selected text with square brackets [${TEXT}]
- `{`: Wrap selected text with curly braces {${TEXT}}
- `(`: Wrap selected text with parenthesis (${TEXT})

## VSCode Bindings

### Navigating Panes Like a Window Manager

- `<ALT-h>`: Navigate to the view on the right
- `<ALT-j>`: Navigate to the view below
- `<ALT-k>`: Navigate to the view above
- `<ALT-l>`: Navigate to the view on the left
- `<C-i>`: Toggle the chat window. This one is 2 actions in one bind.

  - Just doing the sidebar toggle didn't change the focus between the chat and the editor when toggling, this is the best solution I could make.

    ```javascript
    if (!chatSetupDisabled && !chatSetupHidden) {
    	workbench.action.chat.open;
    }

    if (auxiliaryBarVisible) {
    	// The right-side panel
    	workbench.action.toggleAuxiliaryBar;
    }
    ```

### Moving Files around the panes

Whenever there isn't a group/pane, moving the file will create one, and if you move the last file in a group, It'll delete the group.

- `<ALT-h>`: Move current file to the group on the right
- `<ALT-l>`: Move current file to the group on the left
