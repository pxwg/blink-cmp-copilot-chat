# Copilot-Chat Source for Blink.cmp

A simple [blink.cmp](https://github.com/saghen/blink.cmp) completion source for [CopilotChat.nvim](https://github.com/CopilotC-Nvim/CopilotChat.nvim).
Used for providing `@`, `#` and `/` completions for [CopilotChat.nvim](https://github.com/CopilotC-Nvim/CopilotChat.nvim).

## Installation

Using [lazy.nvim](https://github.com/folke/lazy.nvim):
```lua
return {
  "saghen/blink.cmp",
  dependencies = {
    "pxwg/blink-cmp-copilot-chat",
  },
  opts = {
    -- other configurations
    sources = {
      per_filetype = {
        -- Add the copilot-chat source for relevant filetype
        ["copilot-chat"] = { "copilot_c" },
      },
    },
    providers = {
      copilot_c = {
        name = "CopilotChat",
        module = "blink-cmp-copilot-chat",
      },
    },
  },
}
```
