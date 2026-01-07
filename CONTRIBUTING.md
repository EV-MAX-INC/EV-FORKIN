# Contributing to EV MAX Software Projects

Thank you for your interest in contributing to EV MAX INC software projects! This document provides guidelines and best practices for contributing.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Process](#development-process)
- [Coding Standards](#coding-standards)
- [Testing Requirements](#testing-requirements)
- [Documentation](#documentation)
- [Intellectual Property Compliance](#intellectual-property-compliance)
- [Pull Request Process](#pull-request-process)
- [Commit Message Guidelines](#commit-message-guidelines)

## Code of Conduct

### Our Standards

- Be respectful and inclusive
- Focus on constructive feedback
- Prioritize collaboration over competition
- Maintain professional communication
- Support fellow contributors

## Getting Started

### Prerequisites

Before contributing, ensure you have:

1. **For Java Projects:**
   - Java 11 or higher
   - Maven 3.6 or higher
   - Your preferred IDE (IntelliJ IDEA, Eclipse, VS Code)

2. **For Python Projects:**
   - Python 3.8 or higher
   - pip and virtualenv
   - Your preferred IDE (PyCharm, VS Code)

### Setting Up Your Development Environment

1. **Fork and Clone the Repository**
   ```bash
   git clone https://github.com/ev-max2024/EVMAX-SOFT-9.28.2025.git
   cd EVMAX-SOFT-9.28.2025
   ```

2. **Create a Feature Branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Install Dependencies**
   
   For Java projects:
   ```bash
   mvn clean install
   ```
   
   For Python projects:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

## Development Process

### Workflow

1. **Check Existing Issues**
   - Review open issues and pull requests
   - Comment on issues you'd like to work on
   - Wait for assignment to avoid duplicate work

2. **Create or Update Issue**
   - If no issue exists, create one describing your proposed changes
   - Include problem statement, proposed solution, and expected benefits

3. **Develop Your Changes**
   - Follow coding standards (see below)
   - Write tests for new functionality
   - Update documentation as needed
   - Keep changes focused and minimal

4. **Test Thoroughly**
   - Run all existing tests
   - Add new tests for your changes
   - Verify code coverage meets requirements

5. **Submit Pull Request**
   - Follow PR template
   - Link related issues
   - Request review from maintainers

## Coding Standards

### General Principles

- **SOLID Principles**: Follow object-oriented design best practices
- **DRY (Don't Repeat Yourself)**: Avoid code duplication
- **KISS (Keep It Simple)**: Prefer simple, readable solutions
- **YAGNI (You Aren't Gonna Need It)**: Don't add functionality speculatively

### Java Code Style

- Follow [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)
- Use meaningful variable and method names
- Keep methods short and focused (max 50 lines)
- Use proper exception handling
- Add JavaDoc comments for public APIs

```java
/**
 * Retrieves abusive experience report for a given site.
 *
 * @param siteUrl the URL of the site to check
 * @return AbusiveExperienceReport containing violation details
 * @throws ApiException if the API call fails
 */
public AbusiveExperienceReport getReport(String siteUrl) throws ApiException {
    // Implementation
}
```

### Python Code Style

- Follow [PEP 8](https://www.python.org/dev/peps/pep-0008/) style guide
- Use type hints for function signatures
- Keep functions focused and small
- Use docstrings for all public functions

```python
def generate_report(query: str, max_results: int = 10) -> Dict[str, Any]:
    """
    Generates an AI-powered research report using Perplexity.
    
    Args:
        query: The research query to analyze
        max_results: Maximum number of results to include
        
    Returns:
        Dictionary containing the generated report
        
    Raises:
        ApiException: If the API call fails
    """
    # Implementation
```

### Code Formatting

- **Java**: Use Maven checkstyle plugin or IDE formatter
- **Python**: Use `black` for code formatting and `isort` for imports

```bash
# Python formatting
black .
isort .
```

## Testing Requirements

### Test Coverage

- Minimum 80% code coverage for new code
- All public APIs must have tests
- Include both positive and negative test cases
- Test edge cases and error conditions

### Testing Frameworks

- **Java**: JUnit 5 + Mockito
- **Python**: pytest + unittest.mock

### Test Structure

```java
// Java test example
@Test
public void testGetReport_ValidSite_ReturnsReport() {
    // Arrange
    String siteUrl = "https://example.com";
    
    // Act
    AbusiveExperienceReport report = client.getReport(siteUrl);
    
    // Assert
    assertNotNull(report);
    assertEquals(siteUrl, report.getSiteUrl());
}
```

```python
# Python test example
def test_generate_report_valid_query_returns_data():
    # Arrange
    query = "AI trends in 2025"
    
    # Act
    result = generate_report(query)
    
    # Assert
    assert result is not None
    assert "data" in result
```

### Running Tests

```bash
# Java
mvn test

# Python
pytest

# With coverage
pytest --cov=. --cov-report=html
```

## Documentation

### What to Document

- All public APIs and functions
- Configuration options and environment variables
- Architecture decisions (use ADRs)
- Setup and deployment procedures
- Troubleshooting guides

### Documentation Standards

- Use clear, concise language
- Include code examples
- Keep documentation up-to-date with code changes
- Add diagrams for complex workflows

### Updating Documentation

When making changes, update:
- README.md (if adding new features)
- CHANGELOG.md (following Keep a Changelog format)
- API documentation (JavaDoc/docstrings)
- Architecture diagrams (if structure changes)

## Intellectual Property Compliance

### Code Originality

All code contributions must be original work or properly licensed. Before contributing:

- Ensure you have the right to contribute the code
- Do not copy code from proprietary sources
- When using open-source code, verify license compatibility
- Provide proper attribution for any third-party code

### License Compliance

**Preferred Open-Source Licenses:**
- MIT License (most permissive)
- Apache License 2.0 (includes patent grant)
- BSD Licenses (simple and permissive)

**Licenses Requiring Approval:**
- GPL/LGPL (copyleft requirements)
- AGPL (network copyleft)
- EPL (Eclipse Public License)
- Custom or restrictive licenses

### Third-Party Dependencies

Before adding new dependencies:

1. **Check License**: Verify the license is compatible
2. **Document**: Add to dependency list with license information
3. **Review Terms**: Ensure compliance with terms of service
4. **Get Approval**: Consult with team lead for non-standard licenses

### Attribution Requirements

When using third-party code or resources:

```java
/*
 * This implementation is based on the algorithm described in:
 * Source: https://example.com/original-source
 * License: MIT License
 * Author: Original Author Name
 * Modifications: Description of changes made
 */
```

```python
"""
Based on implementation from:
Source: https://example.com/original-source
License: Apache 2.0
Author: Original Author Name
Modified to support additional features
"""
```

### API and Service Usage

When integrating external APIs:

- Review and comply with Terms of Service
- Respect rate limits and usage quotas
- Don't store or redistribute API responses if prohibited
- Include required attribution in documentation
- Use API keys securely (never commit to repository)

### Confidential Information

**Never commit:**
- API keys, passwords, or credentials
- Proprietary algorithms from previous employers
- Customer data or PII
- Trade secrets or confidential information
- Copyrighted materials without permission

### Code Review for IP Compliance

During code review, verify:

- [ ] Code is original or properly licensed
- [ ] Dependencies are documented with licenses
- [ ] No proprietary content from other sources
- [ ] API usage complies with terms of service
- [ ] Attribution provided where required
- [ ] No sensitive information in code or comments

For detailed guidelines, see [IP_COMPLIANCE.md](IP_COMPLIANCE.md).

## Pull Request Process

### PR Template

```markdown
## Description
Brief description of changes

## Related Issue
Fixes #(issue number)

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Performance improvement
- [ ] Code refactoring

## Testing
- [ ] All tests pass
- [ ] New tests added
- [ ] Code coverage maintained/improved

## Checklist
- [ ] Code follows style guidelines
- [ ] Documentation updated
- [ ] CHANGELOG.md updated
- [ ] No breaking changes (or documented)
```

### Review Process

1. **Automated Checks**
   - CI/CD pipeline must pass
   - Code coverage requirements met
   - No security vulnerabilities

2. **Peer Review**
   - At least one approval required
   - Address all review comments
   - Re-request review after changes

3. **Merge**
   - Squash commits for clean history
   - Use descriptive merge commit message

### Review Timeline

- Initial review: Within 2 business days
- Follow-up reviews: Within 1 business day
- Stale PRs (no activity for 14 days) may be closed

## Commit Message Guidelines

### Conventional Commits

We follow [Conventional Commits](https://www.conventionalcommits.org/) specification:

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types

- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, no logic change)
- `refactor`: Code refactoring
- `perf`: Performance improvements
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

### Examples

```
feat(api): add retry logic for API calls

Implement exponential backoff retry mechanism for failed API calls.
This improves reliability during temporary network issues.

Closes #123
```

```
fix(auth): correct token validation logic

The token validation was failing for tokens with special characters.
Updated regex pattern to properly handle all valid token formats.

Fixes #456
```

### Best Practices

- Use imperative mood ("add" not "added")
- Keep subject line under 50 characters
- Provide detailed body for complex changes
- Reference issues and PRs in footer

## Questions or Need Help?

- **Documentation**: Check existing docs in the repository
- **Issues**: Search for existing issues or create a new one
- **Discussion**: Use GitHub Discussions for general questions
- **Email**: Contact the maintainers directly for sensitive matters

## Recognition

Contributors who make significant contributions will be:
- Listed in release notes
- Mentioned in project documentation
- Considered for collaborator status

Thank you for contributing to EV MAX INC projects! Your efforts help us build better software and improve our processes.
