# 🧠 Neovim Config with lazy.nvim

This is my personal Neovim configuration using [lazy.nvim](https://github.com/folke/lazy.nvim) as a plugin manager. It supports modern plugin management, lazy-loading, and clean configuration via Lua.

---

## ✅ Prerequisites

- Neovim >= **v0.8.0**
- Git
- `curl` or `wget` (for downloading lazy.nvim)

---

## 🛠 Installation

### 1. Clone this repository

```
git clone git@github.com:fare98/neovim-conf.git ~/.config/nvim
```

Replace ~/.config/nvim if you want to keep another configuration — but this is the standard path Neovim expects.

⸻

2. Install Neovim

macOS (Homebrew)

`brew install neovim`

Ubuntu / Debian

`sudo apt update`
`sudo apt install neovim`

Arch Linux

`sudo pacman -S neovim`


⸻

3. Install lazy.nvim

You don’t need to manually install lazy.nvim. On first run, the code in lua/config/lazy.lua will automatically clone it to the required path:

`local lazypath = vim.fn.stdpath("data") .. "/lazy/lazy.nvim"`

If it’s not present, it runs:

`git clone --filter=blob:none --branch=stable https://github.com/folke/lazy.nvim.git ~/.local/share/nvim/lazy/lazy.nvim`


⸻

4. Launch Neovim

Simply open Neovim:

`nvim`

On first launch, lazy.nvim will install all plugins defined in lua/plugins/*.lua.

⸻

📦 Plugin Management

Plugins are declared in Lua files inside:

lua/plugins/

For example:

```
-- lua/plugins/ui.lua
return {
  {
    "nvim-lualine/lualine.nvim",
    config = function()
      require("lualine").setup()
    end
  }
}
```

To add plugins:
	1.	Create a new file in lua/plugins/ or edit an existing one.
	2.	Add plugin tables (using lazy.nvim spec format).
	3.	Save and restart Neovim.

Run this to install new plugins:

:Lazy sync


⸻

🔄 Plugin Commands

Command	Description
:Lazy	Open lazy.nvim UI
:Lazy sync	Install and update plugins
:Lazy clean	Remove unused plugins
:Lazy update	Update all plugins


⸻

🧹 Optional: Remove All Plugins

`rm -rf ~/.local/share/nvim/lazy`


⸻

🧪 Troubleshooting
	•	Run :checkhealth in Neovim to identify missing dependencies.
	•	Ensure your nvim is up-to-date (nvim --version).
	•	Check permissions on ~/.local/share/nvim/.

⸻
