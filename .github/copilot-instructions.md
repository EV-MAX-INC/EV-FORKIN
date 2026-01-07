# GitHub Copilot Instructions for EV MAX INC Repository

## Repository Overview

This repository contains software development projects for EV MAX INC, with a strong emphasis on:
- Intellectual Property (IP) compliance
- Process optimization and automation
- AI-powered tools and integrations
- Quality assurance and security best practices

## Core Principles for AI Coding Agents

### 1. Intellectual Property Compliance (CRITICAL)

**ALWAYS follow these IP guidelines:**

- **Never copy code** from proprietary sources without proper licensing
- **Use only permissive licenses**: MIT, Apache 2.0, BSD (preferred)
- **Require approval** for GPL/LGPL/AGPL licenses (copyleft concerns)
- **Provide attribution** for all third-party code and algorithms
- **Document sources**: Include license information for any dependencies
- **Original implementations**: Prioritize writing original code over copying

**Before suggesting any code:**
1. Ensure it's original or properly licensed
2. Check license compatibility with proprietary codebase
3. Add attribution comments if using third-party algorithms
4. Document dependencies in `DEPENDENCIES.md`

**Reference documents:**
- [IP_COMPLIANCE.md](../IP_COMPLIANCE.md) - Comprehensive IP guidelines
- [IP_QUICK_REFERENCE.md](../IP_QUICK_REFERENCE.md) - Quick decision guide
- [DEPENDENCIES.md](../DEPENDENCIES.md) - Dependency tracking template

### 2. Code Quality and Standards

**Java Projects:**
- Java 11+ compliance
- Maven for dependency management
- JUnit 5 for testing (EPL 2.0 - approved with review)
- Follow Google Java Style Guide conventions
- Minimum 80% test coverage
- Document all public APIs with Javadoc

**Python Projects:**
- Python 3.8+ compatibility
- Use pytest for testing (MIT license)
- Follow PEP 8 style guidelines
- Type hints for function signatures
- Docstrings for all public functions
- Virtual environments for dependency isolation

**General Standards:**
- Write self-documenting code with clear variable names
- Add comments only for complex logic or business rules
- Follow existing code patterns in the repository
- Keep functions small and focused (single responsibility)
- Handle errors gracefully with appropriate logging

### 3. API Integration Guidelines

**Before integrating any API:**
1. Review Terms of Service for commercial use permissions
2. Check rate limits and usage restrictions
3. Verify data handling and privacy requirements
4. Document API terms in `DEPENDENCIES.md`
5. Never commit API keys (use environment variables)

**Current APIs in use:**
- Google's Abusive Experience Report API (Google Cloud ToS)
- Perplexity AI API (requires attribution)

**Best practices:**
- Use API key authentication securely
- Implement retry logic with exponential backoff
- Cache responses when permitted by ToS
- Include required attribution in documentation
- Monitor usage to stay within quotas

### 4. Security and Privacy

**Never commit sensitive information:**
- API keys, tokens, passwords
- Customer data or personally identifiable information (PII)
- Proprietary algorithms from other sources
- Trade secrets or confidential information
- Database credentials or connection strings

**Security practices:**
- Use environment variables for configuration
- Validate all user inputs
- Sanitize data before database queries
- Use parameterized queries to prevent SQL injection
- Implement proper authentication and authorization
- Follow OWASP security guidelines

### 5. Documentation Requirements

**Always document:**
- Public APIs and interfaces
- Complex algorithms or business logic
- Configuration requirements
- Environment setup instructions
- Known limitations or edge cases

**Documentation style:**
- Write in clear, concise language
- Use markdown formatting consistently
- Include code examples for public APIs
- Keep documentation up-to-date with code changes
- Link to official third-party documentation (don't copy it)

### 6. Testing Requirements

**Test coverage expectations:**
- Minimum 80% code coverage
- Unit tests for all business logic
- Integration tests for API endpoints
- Edge cases and error conditions
- Performance tests for critical paths

**Testing practices:**
- Write tests before or alongside code (TDD/BDD)
- Use descriptive test names that explain what's being tested
- Keep tests independent and repeatable
- Mock external dependencies
- Test both success and failure scenarios

### 7. Version Control and Commits

**Commit message format:**
```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code formatting (no logic changes)
- `refactor`: Code restructuring (no behavior change)
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

**Example:**
```
feat(api): Add retry logic for Perplexity API calls

Implement exponential backoff retry mechanism for failed API calls.
Includes configurable max retries and timeout settings.

Closes #123
```

### 8. Pull Request Requirements

**Every PR must include:**
- [ ] Clear description of changes and motivation
- [ ] Test coverage for new code
- [ ] Updated documentation if APIs changed
- [ ] No sensitive information in code or commits
- [ ] IP compliance verification (see checklist below)
- [ ] Code follows style guidelines
- [ ] All tests pass

**IP Compliance Checklist:**
- [ ] Code is original or properly licensed
- [ ] Dependencies documented with licenses
- [ ] No proprietary content from other sources
- [ ] API usage complies with terms of service
- [ ] Attribution provided where required
- [ ] No sensitive information in code or comments

### 9. Project-Specific Context

**Current Projects:**

1. **java-abusive-experience-api**
   - Java 11+ with Maven
   - Google API integration
   - Thread-safe client implementation
   - Comprehensive unit tests with JUnit 5 and Mockito

2. **perplSDK (Python)**
   - Python 3.8+ SDK
   - Perplexity AI integration
   - Research automation and reporting
   - Requires API key authentication

**Key Directories:**
- `.github/` - GitHub templates and workflows
- Documentation files in root directory
- No source code directories yet (documentation repository)

### 10. Common Patterns and Anti-Patterns

**DO:**
✅ Use environment variables for configuration  
✅ Implement proper error handling with logging  
✅ Write clear, self-documenting code  
✅ Add tests for all business logic  
✅ Document public APIs thoroughly  
✅ Follow existing code style and patterns  
✅ Use dependency injection for testability  
✅ Implement retry logic for external API calls  

**DON'T:**
❌ Copy code from proprietary sources  
❌ Commit API keys or credentials  
❌ Use GPL/AGPL licenses without approval  
❌ Include customer data in tests or examples  
❌ Write large, monolithic functions  
❌ Skip error handling or validation  
❌ Ignore test failures  
❌ Make breaking changes without deprecation warnings  

### 11. Performance Considerations

**Optimization guidelines:**
- Profile before optimizing
- Focus on algorithmic improvements first
- Cache expensive computations when appropriate
- Use async/await for I/O-bound operations
- Implement connection pooling for databases
- Monitor memory usage and prevent leaks
- Set appropriate timeouts for external calls

### 12. Error Handling Best Practices

**Error handling strategy:**
- Use specific exception types (not generic Exception)
- Log errors with context and stack traces
- Return meaningful error messages to users
- Don't expose internal implementation details in errors
- Implement circuit breakers for external services
- Gracefully degrade functionality when possible
- Document expected exceptions in function signatures

### 13. Continuous Integration and Deployment

**CI/CD expectations:**
- All tests must pass before merge
- Code coverage must meet minimum thresholds
- Linting checks must pass
- Security scans must complete without high-severity issues
- Build must succeed on all target platforms
- Documentation must build without errors

### 14. Code Review Guidelines

**When reviewing code:**
- Check for IP compliance issues
- Verify test coverage and quality
- Look for security vulnerabilities
- Ensure documentation is updated
- Validate error handling
- Check for code style consistency
- Review performance implications
- Verify API compatibility

### 15. Resources and References

**Essential Reading:**
- [CONTRIBUTING.md](../CONTRIBUTING.md) - Contribution guidelines
- [IP_COMPLIANCE.md](../IP_COMPLIANCE.md) - IP guidelines (MUST READ)
- [SECURITY.md](../SECURITY.md) - Security policies
- [IMPROVEMENTS.md](../IMPROVEMENTS.md) - Process improvements and best practices
- [LICENSE](../LICENSE) - Copyright and license terms

**External Resources:**
- [Semantic Versioning](https://semver.org/)
- [Keep a Changelog](https://keepachangelog.com/)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [Choose a License](https://choosealicense.com/)
- [OWASP Security Guidelines](https://owasp.org/)

## Quick Decision Trees

### Should I add this dependency?

```
Is it necessary? 
├─ No → Don't add it
└─ Yes → What's the license?
    ├─ MIT/Apache 2.0/BSD → ✅ Add and document
    ├─ GPL/LGPL/AGPL → ⚠️ Get approval first
    └─ Custom/Proprietary → ⚠️ Legal review required
```

### Can I use this code snippet?

```
Where is it from?
├─ I wrote it myself → ✅ Yes
├─ Open source (MIT/Apache/BSD) → ✅ Yes, with attribution
├─ Stack Overflow/Blog → ⚠️ Check license, add attribution
├─ Proprietary software → ❌ No
└─ Previous employer → ❌ No (IP risk)
```

### Should I commit this file?

```
Does it contain:
├─ API keys/secrets? → ❌ Never commit
├─ Customer data? → ❌ Never commit
├─ Credentials? → ❌ Never commit
├─ Generated files? → ❌ Add to .gitignore
├─ Dependencies (node_modules)? → ❌ Add to .gitignore
└─ Source code/docs → ✅ Commit with good message
```

## Contact and Escalation

**For IP concerns:** legal@ev-max-inc.com  
**For security issues:** See [SECURITY.md](../SECURITY.md)  
**For general questions:** See [CONTRIBUTING.md](../CONTRIBUTING.md)

---

**Last Updated:** 2025-10-12  
**Version:** 1.0.0  
**Applies to:** All EV MAX INC repositories
