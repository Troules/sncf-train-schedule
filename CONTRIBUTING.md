# Contributing to SNCF Train Schedule Skill

Thank you for your interest in contributing to this Claude skill! This document provides guidelines for contributing.

## How to Contribute

### Reporting Issues

If you find a bug or have a suggestion:

1. Check if the issue already exists in the issue tracker
2. If not, create a new issue with:
   - Clear description of the problem or suggestion
   - Steps to reproduce (for bugs)
   - Expected vs actual behavior
   - Your environment (Claude version, OS, etc.)

### Submitting Changes

1. **Fork the repository**
   ```bash
   git fork <repository-url>
   ```

2. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make your changes**
   - Follow the existing code style
   - Update documentation as needed
   - Test your changes

4. **Commit your changes**
   ```bash
   git commit -m "Add: description of your changes"
   ```
   Use conventional commit messages:
   - `Add:` for new features
   - `Fix:` for bug fixes
   - `Update:` for updates to existing features
   - `Docs:` for documentation changes
   - `Refactor:` for code refactoring

5. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

6. **Create a Pull Request**
   - Describe what your changes do
   - Reference any related issues
   - Include examples if applicable

## Development Guidelines

### SKILL.md Structure

The `SKILL.md` file should follow this structure:

1. **YAML Frontmatter**: Name and description
2. **Overview**: What the skill does
3. **API Configuration**: Endpoints and authentication
4. **Instructions**: Step-by-step guide for Claude
5. **Examples**: Practical usage examples
6. **Guidelines**: Best practices and constraints

### Testing Your Changes

Before submitting:

1. Test the skill with Claude Code:
   ```bash
   # Copy to your skills directory
   cp -r . ~/.claude/skills/sncf-train-schedule/

   # Test various scenarios
   claude "Show me trains from Paris to Lyon"
   ```

2. Verify API calls work correctly:
   ```bash
   # Test with curl
   curl -u $NAVITIA_API_TOKEN: "https://api.navitia.io/v1/coverage"
   ```

3. Check that documentation is clear and accurate

### Documentation Standards

- Use clear, concise language
- Include code examples with expected output
- Document all API endpoints and parameters
- Keep examples up-to-date
- Use proper markdown formatting

### Code Style

- Use consistent indentation (2 spaces)
- Keep lines under 100 characters when possible
- Use meaningful variable names
- Add comments for complex logic
- Follow markdown best practices

## Areas for Contribution

We welcome contributions in these areas:

### Features
- [ ] Add support for more journey filters (wheelchair access, bike transport)
- [ ] Implement fare information retrieval
- [ ] Add multi-language support
- [ ] Create journey comparison tool
- [ ] Add disruption notifications
- [ ] Implement station facilities lookup

### Documentation
- [ ] Add more usage examples
- [ ] Create video tutorials
- [ ] Translate documentation to French
- [ ] Add troubleshooting guide
- [ ] Create API response reference

### Improvements
- [ ] Optimize API call efficiency
- [ ] Improve error handling
- [ ] Add response caching
- [ ] Better datetime parsing
- [ ] Enhance output formatting

### Testing
- [ ] Add integration tests
- [ ] Create test fixtures
- [ ] Add CI/CD pipeline
- [ ] Create mock API for testing

## API Guidelines

When working with the Navitia API:

- **Respect rate limits**: Don't make excessive requests
- **Use caching**: Cache responses when appropriate
- **Handle errors**: Always check for and handle API errors
- **Real-time data**: Prefer `data_freshness=realtime` for current info
- **Privacy**: Never log or expose API tokens

## Pull Request Review Process

1. **Automated checks**: PRs must pass any automated tests
2. **Code review**: At least one maintainer will review your code
3. **Testing**: Changes will be tested in a real environment
4. **Documentation**: Ensure all docs are updated
5. **Merge**: Once approved, your PR will be merged

## Community Guidelines

- Be respectful and constructive
- Help others learn and grow
- Give credit where credit is due
- Focus on what is best for the community
- Show empathy and kindness

## Questions?

If you have questions about contributing:

- Open an issue for discussion
- Check existing documentation
- Review the Navitia API docs
- Look at previous PRs for examples

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

## Recognition

Contributors will be:
- Listed in the CONTRIBUTORS file
- Mentioned in release notes
- Credited in the README

Thank you for making this skill better! 🚆
