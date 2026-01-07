# Intellectual Property Compliance Guidelines

## Overview

This document provides guidelines for ensuring that all code, documentation, and other materials in EV MAX INC repositories are free from intellectual property (IP) issues and comply with copyright laws and licensing requirements.

## Core Principles

1. **Respect Third-Party IP**: Never copy code, documentation, or other materials from proprietary sources without proper licensing
2. **Open Source Compliance**: When using open-source components, strictly adhere to their license terms
3. **Attribution**: Always provide proper attribution for third-party work
4. **Original Work**: Prioritize creating original implementations over copying existing solutions

## Guidelines for Contributors

### Code Contributions

#### DO:
- Write original code based on your own knowledge and understanding
- Use open-source libraries with permissive licenses (MIT, Apache 2.0, BSD)
- Document the source and license of any third-party code
- Consult with legal team for commercial or GPL-licensed dependencies
- Use public APIs according to their terms of service

#### DON'T:
- Copy code from proprietary sources without authorization
- Use code from Stack Overflow, GitHub, or other sources without understanding licensing
- Include proprietary algorithms or methods from previous employers
- Violate terms of service of third-party APIs
- Use GPL or AGPL licensed code without approval (due to copyleft requirements)

### Documentation

#### DO:
- Write documentation in your own words
- Use generic industry terminology and concepts
- Reference public standards and specifications
- Link to official documentation of third-party tools
- Create original diagrams and illustrations

#### DON'T:
- Copy documentation from proprietary sources
- Reproduce copyrighted materials without permission
- Use trademarked terms incorrectly
- Include screenshots or assets from other products without permission

### Data and Assets

#### DO:
- Use royalty-free or properly licensed images, icons, and assets
- Create original data sets or use public domain data
- Document the source and licensing of all assets
- Use tools like Unsplash, Pexels, or Creative Commons resources

#### DON'T:
- Use proprietary images, logos, or branding without permission
- Include customer data or confidential information
- Use copyrighted fonts without proper licensing
- Include third-party trademarks without authorization

## Open Source License Compatibility

### Preferred Licenses (Most Permissive)
- **MIT License**: Very permissive, minimal restrictions
- **Apache License 2.0**: Includes patent grant, permissive
- **BSD Licenses**: Permissive with minimal requirements

### Use With Caution
- **GPL/LGPL**: Copyleft licenses require derivative works to be open-sourced
- **AGPL**: Network copyleft, very restrictive
- **MPL**: Copyleft at file level
- **EPL**: Eclipse Public License, requires review

### Avoid Without Legal Review
- **Custom licenses**: May have unexpected terms
- **Restrictive licenses**: Non-commercial, no-derivatives
- **Proprietary licenses**: Require commercial agreements

## Third-Party Tool References

When referencing commercial or third-party tools in documentation:

### Acceptable References:
- Generic tool categories (e.g., "monitoring tools", "CI/CD platforms")
- Multiple options with "such as" or "examples include"
- Open-source alternatives alongside commercial options
- Factual comparisons based on public information

### Example - GOOD:
```markdown
Implement monitoring tools such as:
- Open-source: Prometheus, Grafana, Nagios
- Commercial: Datadog, New Relic, AppDynamics
```

### Example - BAD:
```markdown
Use Datadog for all monitoring (creates vendor lock-in impression)
```

## API Integration Guidelines

### Before Integrating Any API:

1. **Review Terms of Service**
   - Ensure commercial use is permitted
   - Check rate limits and usage restrictions
   - Verify data handling requirements

2. **License Compatibility**
   - Verify API client libraries are compatible
   - Check for attribution requirements
   - Review any redistribution restrictions

3. **Data Privacy**
   - Ensure compliance with GDPR, CCPA, and other regulations
   - Don't send sensitive data to third-party services without encryption
   - Review data retention and deletion policies

4. **Attribution**
   - Include required attribution in documentation
   - Follow trademark usage guidelines
   - Don't imply endorsement unless authorized

## Specific Tool References in This Repository

### Google APIs
- **Current Use**: Google's Abusive Experience Report API
- **License**: Subject to Google Cloud Platform Terms of Service
- **Compliance**: API key authentication, no redistribution of API responses
- **Documentation**: Link to official Google documentation only

### Perplexity AI
- **Current Use**: Research automation SDK
- **License**: Subject to Perplexity API terms
- **Compliance**: Respect rate limits, don't redistribute API responses
- **Attribution**: Mention that results are powered by Perplexity

### Other Tool Mentions
- SonarQube (Open-source available)
- JUnit (EPL 2.0 - requires review for compliance)
- Mockito (MIT License - compatible)
- pytest (MIT License - compatible)

## Code Review Checklist for IP Compliance

Before submitting code, verify:

- [ ] All code is original or properly licensed
- [ ] Third-party dependencies are documented with licenses
- [ ] No proprietary algorithms or methods from previous employers
- [ ] API usage complies with terms of service
- [ ] No sensitive or confidential information included
- [ ] Attribution provided where required
- [ ] No GPL/AGPL code without approval
- [ ] Trademarks used correctly
- [ ] Documentation is original or properly attributed
- [ ] Assets and images are properly licensed

## License Compliance Automation

### Recommended Tools:
- **FOSSA**: Automated license compliance scanning
- **WhiteSource/Mend**: Open-source security and license compliance
- **Black Duck**: Comprehensive license management
- **Snyk**: Security and license scanning
- **License Finder**: Open-source license discovery tool

### GitHub Actions Integration:
```yaml
# Example: Add license scanning to CI/CD
- name: License Compliance Check
  uses: fossas/fossa-action@v1
  with:
    api-key: ${{ secrets.FOSSA_API_KEY }}
```

## Reporting IP Concerns

If you discover potential IP issues:

1. **Do Not Commit**: Stop and don't push the code
2. **Document**: Note the specific concern and location
3. **Report**: Contact legal team or repository maintainers immediately
4. **Isolate**: If already committed, don't merge to main branches
5. **Review**: Wait for legal review before proceeding

### Contact Information:
- **Legal Team**: legal@ev-max-inc.com
- **Repository Maintainers**: See CONTRIBUTING.md
- **Security Issues**: See SECURITY.md

## Educational Resources

### Recommended Reading:
- [Choose a License](https://choosealicense.com/)
- [Open Source Initiative - Licenses](https://opensource.org/licenses)
- [GitHub Licensing Guidance](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository)
- [SPDX License List](https://spdx.org/licenses/)
- [TLDRLegal](https://tldrlegal.com/) - Plain English license explanations

## Regular Audits

EV MAX INC conducts regular IP compliance audits:

- **Frequency**: Quarterly
- **Scope**: All dependencies, code, and documentation
- **Tools**: Automated scanning + manual review
- **Documentation**: Results documented in compliance reports

## Updates to This Document

This document is reviewed and updated:
- Quarterly or as needed
- When new dependencies are added
- After legal guidance changes
- Following compliance audits

**Last Updated**: 2025-10-05  
**Next Review**: 2026-01-05

---

**Questions?** Contact the legal team at legal@ev-max-inc.com or create an issue in the repository.
