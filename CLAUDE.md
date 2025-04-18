# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview
This is a dotfiles repository managed with [chezmoi](https://www.chezmoi.io/). It contains shell configurations, git settings, and integrations with modern tools including:
- Starship prompt
- Atuin shell history
- Custom key bindings
- Templated configurations for security

## Commands
- **Apply Changes**: `chezmoi apply` to update dotfiles on the system
- **Preview Changes**: `chezmoi diff` to see pending changes
- **Edit Files**: `chezmoi edit --apply ~/.file` to edit and apply immediately

## Working with Templates
- Sensitive information is kept in `~/.config/chezmoi/chezmoi.toml` (not in repo)
- Template files (`.tmpl` extension) use Go templates for variable substitution
- When adding new templates, use `{{ .variable }}` syntax and document in `chezmoi.toml.example`

## Important Files
- `dot_zshrc`: Main shell configuration
- `dot_zsh_keybindings`: Terminal key binding configuration
- `dot_config/starship.toml`: Prompt styling configuration
- `dot_gitconfig.tmpl`: Git configuration template (requires user data)
- `ASSISTANT_MEMORY.md`: Detailed history of repository changes

## Code Style Guidelines
- **Shell Scripts**: Use Zsh syntax for compatibility, follow POSIX when possible
- **Indentation**: 2 spaces (not tabs)
- **Functions**: Include usage comments and error handling for all functions
- **Variable naming**: Use lowercase_with_underscores for variables and functions
- **Quoting**: Always quote variable references and command substitutions
- **Error handling**: Check return codes and provide useful error messages
- **Whitespace**: No trailing whitespace, use blank lines to separate logical sections
- **Git**: Follow conventional commits style, sign commits with GPG
- **Comments**: Organize files with section comments using `# ----------------------------------------` format
- **Section Headers**: Use descriptive headers with consistent formatting

## Security Considerations
- Never hardcode personal information in any file
- Use templating for sensitive data like emails, names, and keys
- Document security-sensitive configurations in `chezmoi.toml.example`
- Always verify file permissions for sensitive files (600 for private keys, etc.)

## Tools Integration
- **Starship**: Configuration in `dot_config/starship.toml`
- **Atuin**: Integrated in zshrc, respects key bindings
- **NVM**: Configured with lazy loading for better performance