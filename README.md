<p align="center">
<img src="https://astronvim.com/logo/astronvim.svg" width=100/>
</p>

<h1 align="center"> AstroTheme </h1>

<p align="center">The default colorscheme used by <a href="https://github.com/AstroNvim/AstroNvim">AstroNvim</a> an aesthetically pleasing and feature-rich neovim config that is extensible and easy to use with a great set of plugins  </p>

## ✨ Features

- **Automatic** plugin detection and highlight setting (Packer and lazy.nvim supported)
- Override or modify **_EVERYTHING._**
- Global & Theme specific overrides
- Vim terminal colors
- Heirline highlights
- Lualine support

## 🎨 Palettes

<p align="center">
<img src="https://astronvim.com/themes/overview.png"/>
</p>

<details>
<summary>AstroDark (default)</summary>

```vim
colorscheme astrodark " Dark theme (default)
```

<p align="center">
<img src="https://astronvim.com/themes/astrodark.png"/>
</p>

</details>

<details>
<summary>AstroLight</summary>

```vim
colorscheme astrolight " Light theme
```

<p align="center">
<img src="https://astronvim.com/themes/astrolight.png"/>
</p>

</details>

<details>
<summary>AstroMars</summary>

```vim
colorscheme astromars " Red theme
```

<p align="center">
<img src="https://astronvim.com/themes/astromars.png"/>
</p>

</details>

## 🛠 Options

```lua
require("astrotheme").setup({
  palette = "astrodark", -- String of the default palette to use when calling `:colorscheme astrotheme`
  background = { -- :h background, palettes to use when using the core vim background colors
    light = "astrolight",
    dark = "astrodark",
  },

  style = {
    transparent = false,         -- Bool value, toggles transparency.
    inactive = true,             -- Bool value, toggles inactive window color.
    float = true,                -- Bool value, toggles floating windows background colors.
    neotree = true,              -- Bool value, toggles neo-trees background color.
    border = true,               -- Bool value, toggles borders.
    title_invert = true,         -- Bool value, swaps text and background colors.
    italic_comments = true,      -- Bool value, toggles italic comments.
    simple_syntax_colors = true, -- Bool value, simplifies the amounts of colors used for syntax highlighting.
  },


  termguicolors = true, -- Bool value, toggles if termguicolors are set by AstroTheme.

  terminal_color = true, -- Bool value, toggles if terminal_colors are set by AstroTheme.

  plugin_default = "auto", -- Sets how all plugins will be loaded
                           -- "auto": Uses lazy / packer enabled plugins to load highlights.
                           -- true: Enables all plugins highlights.
                           -- false: Disables all plugins.

  plugins = {              -- Allows for individual plugin overrides using plugin name and value from above.
    ["bufferline.nvim"] = false,
  },

  palettes = {
    global = {             -- Globally accessible palettes, theme palettes take priority.
      my_grey = "#ebebeb",
      my_color = "#ffffff"
    },
    astrodark = {          -- Extend or modify astrodarks palette colors
      ui = {
        red = "#800010", -- Overrides astrodarks red UI color
        accent = "#CC83E3"  -- Changes the accent color of astrodark.
      },
      syntax = {
        cyan = "#800010", -- Overrides astrodarks cyan syntax color
        comments = "#CC83E3"  -- Overrides astrodarks comment color.
      },
      my_color = "#000000" -- Overrides global.my_color
    },
  },

  highlights = {
    global = {             -- Add or modify hl groups globally, theme specific hl groups take priority.
      modify_hl_groups = function(hl, c)
        hl.PluginColor4 = {fg = c.my_grey, bg = c.none }
      end,
      ["@String"] = {fg = "#ff00ff", bg = "NONE"},
    },
    astrodark = {
      -- first parameter is the highlight table and the second parameter is the color palette table
      modify_hl_groups = function(hl, c) -- modify_hl_groups function allows you to modify hl groups,
        hl.Comment.fg = c.my_color
        hl.Comment.italic = true
      end,
      ["@String"] = {fg = "#ff00ff", bg = "NONE"},
    },
  },
})
```

## 📃 Palette Properties

<details>
<summary>modifiable palette names</summary>

```lua
--------------------------------
--- Syntax
--------------------------------
-- only syntax colors.

syntax.red
syntax.blue
syntax.green
syntax.yellow
syntax.purple
syntax.cyan
syntax.orange
syntax.text
syntax.comment
syntax.mute

--------------------------------
--- UI
--------------------------------
-- everything UI and none-text related.
ui.red
ui.blue
ui.green
ui.yellow
ui.purple
ui.cyan
ui.orange

ui.accent

ui.tabline
ui.winbar
ui.tool
ui.base
ui.inactive_base
ui.statusline
ui.split
ui.float
ui.title
ui.border
ui.current_line
ui.scrollbar
ui.selection
ui.menu_selection
ui.highlight
ui.none_text
ui.text
ui.text_active
ui.text_inactive
ui.text_match

ui.prompt

--------------------------------
--- terminal
--------------------------------
-- terminal colors.
term.black
term.bright_black

term.red
term.bright_red

term.green
term.bright_green

term.yellow
term.bright_yellow

term.blue
term.bright_blue

term.purple
term.bright_purple

term.cyan
term.bright_cyan

term.white
term.bright_white

term.background
term.foreground
```

</details>

## ⚡ Requirements

- Neovim >= 0.8

## 🔌 Supported Plugins

| Plugin                                                                          | Key                  |
| ------------------------------------------------------------------------------- | -------------------- |
| [aerial.nvim](https://github.com/stevearc/aerial.nvim)                          | `aerial`             |
| [avante.nvim](https://github.com/yetone/avante.nvim)                            | `avante`             |
| [beacon.nvim](https://github.com/DanilaMihailov/beacon.nvim)                    | `beacon`             |
| [blink.cmp](https://github.com/Saghen/blink.cmp)                                | `blink-cmp`          |
| [bufferline.nvim](https://github.com/akinsho/bufferline.nvim)                   | `bufferline`         |
| [dashboard-nvim](https://github.com/glepnir/dashboard-nvim)                     | `dashboard-nvim`     |
| [flash.nvim](https://github.com/folke/flash.nvim)                               | `flash`              |
| [fzf-lua](https://github.com/ibhagwan/fzf-lua)                                  | `fzf`                |
| [gitsigns.nvim](https://github.com/lewis6991/gitsigns.nvim)                     | `gitsigns`           |
| [hop.nvim](https://github.com/phaazon/hop.nvim)                                 | `hop`                |
| [indent_blankline.nvim](https://github.com/lukas-reineke/indent-blankline.nvim) | `indent-blankline`   |
| [lazy.nvim](https://github.com/folke/lazy.nvim)                                 | `lazy`               |
| [lightspeed.nvim](https://github.com/ggandor/lightspeed.nvim)                   | `lightspeed`         |
| [lualine.nvim](https://github.com/nvim-lualine/lualine.nvim)                    | `lualine`            |
| [mason.nvim](https://github.com/williamboman/mason.nvim)                        | `mason`              |
| [mini.nvim](https://github.com/echasnovski/mini.nvim)                           | `mini`               |
| [mini.icons](https://github.com/echasnovski/mini.icons)                         | `miniicons`          |
| [mini.starter](https://github.com/echasnovski/mini.starter)                     | `ministarter`        |
| [neo-tree.nvim](https://github.com/nvim-neo-tree/neo-tree.nvim)                 | `neo-tree`           |
| [neogit](https://github.com/NeogitOrg/neogit)                                   | `neogit`             |
| [noice.nvim](https://github.com/folke/noice.nvim)                               | `noice`              |
| [nvcheatsheet.nvim](https://github.com/smartinellimarco/nvcheatsheet.nvim)      | `nvcheatsheet`       |
| [nvim-cmp](https://github.com/hrsh7th/nvim-cmp)                                 | `nvim-cmp`           |
| [nvim-dap-ui](https://github.com/rcarriga/nvim-dap-ui)                          | `nvim-dap-ui`        |
| [nvim-notify](https://github.com/rcarriga/nvim-notify)                          | `nvim-notify`        |
| [nvim-tree.lua](https://github.com/nvim-tree/nvim-tree.lua)                     | `nvim-tree`          |
| [nvim-ts-rainbow](https://github.com/p00f/nvim-ts-rainbow)                      | `nvim-ts-rainbow`    |
| [nvim-ts-rainbow2](https://github.com/HiPhish/nvim-ts-rainbow2)                 | `nvim-ts-rainbow2`   |
| [nvim-web-devicons](https://github.com/nvim-tree/nvim-web-devicons)             | `nvim-web-devicons`  |
| [nvim-window-picker](https://github.com/s1n7ax/nvim-window-picker)              | `nvim-window-picker` |
| [rainbow-delimiters.nvim](https://github.com/HiPhish/rainbow-delimiters.nvim)   | `rainbow-delimiters` |
| [snacks.nvim](https://github.com/folke/snacks.nvim)                             | `snacks`             |
| [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim)              | `telescope`          |
| [todo-comments.nvim](https://github.com/folke/todo-comments.nvim)               | `todo-comments`      |
| [vimwiki](https://github.com/vimwiki/vimwiki)                                   | `vimwiki`            |
| [vim-illuminate](https://github.com/RRethy/vim-illuminate)                      | `vim-illuminate`     |
| [which-key.nvim](https://github.com/folke/which-key.nvim)                       | `which-key`          |

## 📦 Installation

Lazy:

```lua
{ "AstroNvim/astrotheme" }
```

Packer:

```lua
 use "AstroNvim/astrotheme"
```

## 🚀 Contributing

If you plan to contribute, please check the [contribution guidelines](https://github.com/AstroNvim/.github/blob/main/CONTRIBUTING.md) first.

When contributing to the extras, we use a templating system for automatically generating extra files for all of the different color palettes. Here are some steps to get started:

1. Create a file like `lua/astrotheme/extras/cool-app.lua`
2. Add the name and output file extension to the `extras` table in `lua/astrotheme/extra/init.lua`
3. Generate the new extra theme files by running the following command in the root of the repository:
   ```sh
   make extras
   ```
4. Verify the new templates are working by checking the generated files in the `extras/` directory. Please **DO NOT** commit them, as they get automatically built by the CI.
