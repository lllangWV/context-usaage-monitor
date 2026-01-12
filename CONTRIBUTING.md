# Contributing to Context Usage Monitor

Thank you for your interest in contributing!

## How to Contribute

### Reporting Bugs

1. Check if the issue already exists in the GitHub Issues
2. If not, create a new issue with:
   - A clear, descriptive title
   - Steps to reproduce the problem
   - Expected vs actual behavior
   - Your environment (OS, Claude Code version, bash version)

### Suggesting Features

1. Open a GitHub Issue with the "feature request" label
2. Describe the feature and its use case
3. Explain why it would be useful to other users

### Pull Requests

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/my-feature`)
3. Make your changes
4. Test your changes locally
5. Commit with clear, descriptive messages
6. Push to your fork
7. Open a Pull Request

### Code Guidelines

- Keep the bash script POSIX-compatible where possible
- Maintain backward compatibility with existing configuration
- Add comments for non-obvious logic
- Test with different Claude Code versions if possible

### Testing

Before submitting a PR:

1. Install the plugin locally
2. Verify the hook triggers correctly
3. Test configuration options
4. Check that state files are created in the correct location

## Questions?

Feel free to open an issue for any questions about contributing.
