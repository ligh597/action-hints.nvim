# :zap: Action Hints

![action-hints Screenshot](https://github.com/roobert/action-hints.nvim/assets/226654/501d8e4a-d501-4af4-a4e4-f6aed78974ca)

A Neovim plugin to show information about the word under the cursor in the statusline or as virtual text.

Available hints:

- `⊛` - go-to-definition (`gd`) is available
- `↱` reference list (`gr`) available / number of references

## Installation

### Lazy

```lua
{
  "roobert/action-hints.nvim",
  config = function()
    require("action-hints").setup()
  end,
},
```

### Packer

```lua
use({
  "roobert/action-hints.nvim",
  config = function()
    require("action-hints").setup()
  end,
})
```

## Configuration

```lua
{
  "roobert/action-hints.nvim",
  config = function()
    require("action-hints").setup({
      template = {
        { " ⊛", "ActionHintsDefinition" },
        { " ↱%s", "ActionHintsReferences" },
      },
      use_virtual_text = true,
      definition_color = "#add8e6",
      reference_color = "#ff6666",
    })
  end,
},
```

## Usage

As a lualine component:

```lua
require("lualine").setup({
  sections = {
    lualine_x = { require("action-hints").statusline },
  },
})
```
