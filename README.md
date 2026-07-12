# dotfiles

Managed with [GNU Stow](https://www.gnu.org/software/stow/).

## Packages

| Package | Files | Target |
|---------|-------|--------|
| `bash` | `.bashrc`, `.bashrc-extra` | `~` |
| `tmux` | `.tmux.conf` | `~` |
| `vim` | `.vimrc` | `~` |
| `cosmic` | `.config/cosmic/` | `~` |

## Setup on a new machine

```bash
git clone <repo-url> ~/.dotfiles
cd ~/.dotfiles
stow bash tmux vim cosmic
```

That's it — stow creates symlinks from `~` back into `~/.dotfiles`.

## Common commands

```bash
# Add a new package
stow <package>

# Remove a package's symlinks
stow -D <package>

# Restow after moving files around
stow -R <package>
```

## Adding a new config

1. Create a package directory: `mkdir <package>`
2. Mirror the target path inside it — e.g. for `~/.config/foo`, use `<package>/.config/foo`
3. Move your config files in
4. Run `stow <package>`
