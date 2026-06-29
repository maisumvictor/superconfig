# 📝 Neovim Setup

This playbook installs [Neovim](https://neovim.io/) and bootstraps the [NvChad](https://nvchad.com/) `v2.5` starter configuration. A few small customizations are applied on top:

- **Leader key:** `Space`
- **Theme:** `onedark`
- **Enabled LSP servers:** `gopls`, `html`, `cssls`
- **Formatter:** `stylua` for Lua (via `conform.nvim`)
- **Custom mappings:**
  - `;` → enter command-line mode (normal)
  - `jk` → exit insert mode

## First launch

1. Run `nvim`.
2. `lazy.nvim` will download the plugin stack automatically.
3. To add/upgrade language servers, run `:Mason`.
4. To manage plugins, run `:Lazy`.

> The `gopls` language server is installed by the playbook. `html` and `cssls` can be installed through Mason (`:MasonInstall vscode-html-language-server vscode-css-language-server`).

## Common keymaps

### General

| Key | Mode | Action |
| --- | --- | --- |
| `<Space>` | Normal | Leader key |
| `;` | Normal | Enter command-line mode (`:`) |
| `jk` | Insert | Exit insert mode |
| `<C-s>` | Normal | Save file |
| `<C-c>` | Normal | Copy whole file to system clipboard |
| `<Esc>` | Normal | Clear search highlights |
| `<leader>n` | Normal | Toggle line numbers |
| `<leader>rn` | Normal | Toggle relative line numbers |
| `<leader>fm` | Normal / Visual | Format file with `conform` |
| `<leader>ch` | Normal | Open NvChad cheatsheet |
| `<leader>th` | Normal | Open theme picker |

### Windows / navigation

| Key | Mode | Action |
| --- | --- | --- |
| `<C-h>` | Normal | Move to left window |
| `<C-l>` | Normal | Move to right window |
| `<C-j>` | Normal | Move to window below |
| `<C-k>` | Normal | Move to window above |

### File explorer (NvimTree)

| Key | Mode | Action |
| --- | --- | --- |
| `<C-n>` | Normal | Toggle file tree |
| `<leader>e` | Normal | Focus file tree |

### Fuzzy finder (Telescope)

| Key | Mode | Action |
| --- | --- | --- |
| `<leader>ff` | Normal | Find files |
| `<leader>fa` | Normal | Find all files (including hidden/ignored) |
| `<leader>fw` | Normal | Live grep in project |
| `<leader>fb` | Normal | Find open buffers |
| `<leader>fh` | Normal | Help tags |
| `<leader>fo` | Normal | Recent files |
| `<leader>fz` | Normal | Fuzzy find in current buffer |
| `<leader>cm` | Normal | Git commits |
| `<leader>gt` | Normal | Git status |

### Buffers (tabufline)

| Key | Mode | Action |
| --- | --- | --- |
| `<Tab>` | Normal | Next buffer |
| `<S-Tab>` | Normal | Previous buffer |
| `<leader>x` | Normal | Close current buffer |
| `<leader>b` | Normal | New empty buffer |

### Terminal

| Key | Mode | Action |
| --- | --- | --- |
| `<leader>h` | Normal | New horizontal terminal |
| `<leader>v` | Normal | New vertical terminal |
| `<A-h>` | Normal / Terminal | Toggle horizontal terminal |
| `<A-v>` | Normal / Terminal | Toggle vertical terminal |
| `<A-i>` | Normal / Terminal | Toggle floating terminal |
| `<C-x>` | Terminal | Exit terminal mode |

### LSP (when a language server is attached)

| Key | Mode | Action |
| --- | --- | --- |
| `gd` | Normal | Go to definition |
| `gD` | Normal | Go to declaration |
| `<leader>D` | Normal | Go to type definition |
| `<leader>ra` | Normal | Rename symbol |
| `<leader>wa` | Normal | Add workspace folder |
| `<leader>wr` | Normal | Remove workspace folder |
| `<leader>wl` | Normal | List workspace folders |
| `<leader>ds` | Normal | Show diagnostics in location list |

### Commenting

| Key | Mode | Action |
| --- | --- | --- |
| `<leader>/` | Normal | Toggle line comment |
| `<leader>/` | Visual | Toggle block comment |

## Discover more mappings

Press `<leader>ch` inside Neovim to open the **NvChad cheatsheet**, or run `:Telescope keymaps` to search all active keymaps.
