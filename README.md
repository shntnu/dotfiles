# Dotfiles

Modern, minimal shell configuration managed with [chezmoi](https://www.chezmoi.io/).

## Key Files

- `dot_zshrc`: Main Zsh configuration
- `dot_zsh_keybindings`: Terminal key bindings
- `dot_gitconfig.tmpl`: Git aliases and settings (template)
- `dot_functions`: Helper shell functions
- `dot_config/starship.toml`: Prompt configuration

## Dependencies

```bash
# Core tools
brew install starship atuin nvm llvm@14

# Optional utilities
brew install tree zopfli pigz
```

- Prompt: [`starship`](https://starship.rs/)
- History: [`atuin`](https://atuin.sh/)

## Setup

For security, personal information is handled via templates:

1. `cp chezmoi.toml.example ~/.config/chezmoi/chezmoi.toml`
2. Edit with your information
3. `chezmoi apply`