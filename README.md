# mime.nvim

Copy code from Neovim as rich text. Select code, run a command, paste into Slack, Notion, Google Docs, or slides — with syntax highlighting intact.

## Features

- Copies code with full syntax highlighting as rich text (RTF/HTML)
- Uses Neovim's built-in treesitter for accurate color extraction
- Respects your current colorscheme — what you see is what you paste
- Works with visual selections and range commands
- Cross-platform clipboard support (macOS, Linux, Windows)

## Requirements

- Neovim 0.9+
- Treesitter parsers installed for your languages
- System clipboard tool: `pbcopy` (macOS), `xclip` or `xsel` (Linux), `win32yank` (Windows)

## Installation

Using [lazy.nvim](https://github.com/folke/lazy.nvim):

```lua
{
  "yourusername/mime.nvim",
  config = function()
    require("mime").setup()
  end,
}
```

## Usage

1. Visual select the code you want to copy
2. Run `:Mime`
3. Paste into any rich text editor

## How It Works

1. Reads treesitter highlight groups for each token in the selection
2. Resolves highlight groups to RGB colors from your current colorscheme
3. Builds an RTF string with the styled text
4. Writes it to the system clipboard via platform clipboard tool
