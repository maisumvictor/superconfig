# 🚀 VicConfig — macOS Development Environment (Ansible)

A personal Ansible playbook that bootstraps a macOS development machine with the Homebrew tools, terminal, shell, editor, and dotfile templates I use.

> **Security note:** this repo is intended to be public. No credentials, tokens, or private keys are committed. AWS and Kubernetes config files in the repo are intentionally empty `.example` templates. The `.gitignore` blocks the real files from ever being added.

## 📋 Prerequisites

Install these manually first (Apple restrictions or Ansible bootstrapping make them hard to automate):

1. **Homebrew**

   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. **Alacritty** (the terminal this playbook configures)

   ```bash
   brew install --cask alacritty
   ```

3. **Ansible**

   ```bash
   brew install ansible
   ```

## 🏃‍♂️ Usage

```bash
git clone git@github.com:maisumvictor/superconfig.git
cd superconfig
ansible-playbook setup.yaml
```

The playbook may ask for your macOS user password when packages or system settings require `sudo`.

## 🛠 What does it do?

- Updates Homebrew.
- Installs CLI tools (git, cloud CLIs, Kubernetes tooling, modern Unix replacements, etc.).
- Configures Zsh + Oh My Zsh + Powerlevel10k.
- Sets up Tmux + TPM + SessionX.
- Installs Neovim with NvChad starter and Go/Terraform language servers.
- Copies empty example templates for `~/.aws/config` and `~/.kube/config` (only if they don't already exist).

## 📚 Docs

- [`FORMULAS.md`](FORMULAS.md) — list of Homebrew formulas with descriptions.
- [`NEOVIM.md`](NEOVIM.md) — how to use the Neovim setup and its keymaps.

## ⚠️ Manual installs not covered

- **Docker Desktop** — requires system extension approval on first launch.
- **AWS VPN Client** — requires manual profile import.
- **Google Cloud SDK** — optionally install with `brew install --cask gcloud-cli`.

## 🚀 Publish to GitHub

If you haven't pushed yet:

```bash
git init
git add -A
git commit -m "Initial public version"
git branch -M main
git remote add origin git@github.com:maisumvictor/superconfig.git
git push -u origin main
```

## 🔐 Security

- No secrets are stored in this repository.
- Real AWS/Kubernetes configs are never overwritten by the playbook (`force: no`).
- If you add real credentials to the source tree, `.gitignore` should prevent them from being committed, but please review `git status` before pushing.
