# Copilot-Chat Source for Blink.cmp

A simple [blink.cmp](https://github.com/saghen/blink.cmp) completion source for [CopilotChat.nvim](https://github.com/CopilotC-Nvim/CopilotChat.nvim).
Used for providing `@`, `#`, `$` and `/` completions for [CopilotChat.nvim](https://github.com/CopilotC-Nvim/CopilotChat.nvim).

![example](https://private-user-images.githubusercontent.com/149765160/456026739-1c179db4-1514-442a-ba89-44b4f1d66afc.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3Njk1OTE1ODAsIm5iZiI6MTc2OTU5MTI4MCwicGF0aCI6Ii8xNDk3NjUxNjAvNDU2MDI2NzM5LTFjMTc5ZGI0LTE1MTQtNDQyYS1iYTg5LTQ0YjRmMWQ2NmFmYy5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwMTI4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDEyOFQwOTA4MDBaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0yYjlmY2RlMDBkMThhZjViODMwM2EwZDdhZTM1ZWNkMDNlZmJiYzY0NGNjMDBlMjM2MmMwZWVmMjM1YjhlNmFkJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.dtbzeyxn7wj9txfM3CzGG6sTV4e0GFGUM3njPPHaaT8)

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
