# Copilot-Chat Source for Blink.cmp

A simple [blink.cmp](https://github.com/saghen/blink.cmp) completion source for [CopilotChat.nvim](https://github.com/CopilotC-Nvim/CopilotChat.nvim).
Used for providing `@`, `#`, `$` and `/` completions for [CopilotChat.nvim](https://github.com/CopilotC-Nvim/CopilotChat.nvim).

<img width="1133" alt="example" src="https://github.com/user-attachments/assets/1c179db4-1514-442a-ba89-44b4f1d66afc" />

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

Also, in order to avoid conflicts with CopilotChat's own completion source, you should disable it by adding the following line to your CopilotChat configuration:
```lua
opts = {
  -- other configurations
  chat_autocomplete = false,
}
```
