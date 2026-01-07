# Third-Party Dependencies and Licenses

## Overview

This document tracks all third-party dependencies used in EV MAX INC projects, their licenses, and compliance status.

**Last Updated**: 2025-10-05  
**Next Review**: 2026-01-05

## License Compliance Status

| Status | Count | Notes |
|--------|-------|-------|
| ✅ Approved | 0 | MIT, Apache 2.0, BSD licenses |
| ⚠️ Review Required | 0 | Requires legal review |
| ❌ Blocked | 0 | Not compatible with our license |

## Java Dependencies

### Production Dependencies

| Dependency | Version | License | Status | Notes |
|------------|---------|---------|--------|-------|
| Google API Client | 2.2.0 | Apache 2.0 | ✅ Approved | Used for Google APIs integration |
| Google Cloud Core | Latest | Apache 2.0 | ✅ Approved | Google Cloud services |
| *Add as needed* | - | - | - | - |

### Test Dependencies

| Dependency | Version | License | Status | Notes |
|------------|---------|---------|--------|-------|
| JUnit 5 | 5.9.3 | EPL 2.0 | ⚠️ Review Required | Standard testing framework |
| Mockito | 5.3.1 | MIT | ✅ Approved | Mocking framework |
| *Add as needed* | - | - | - | - |

## Python Dependencies

### Production Dependencies

| Dependency | Version | License | Status | Notes |
|------------|---------|---------|--------|-------|
| requests | Latest | Apache 2.0 | ✅ Approved | HTTP library |
| *Add as needed* | - | - | - | - |

### Development Dependencies

| Dependency | Version | License | Status | Notes |
|------------|---------|---------|--------|-------|
| pytest | Latest | MIT | ✅ Approved | Testing framework |
| black | Latest | MIT | ✅ Approved | Code formatter |
| *Add as needed* | - | - | - | - |

## External APIs and Services

### Active Integrations

| Service | Purpose | License/ToS | Status | Data Handling |
|---------|---------|-------------|--------|---------------|
| Google Abusive Experience Report API | Compliance monitoring | Google Cloud ToS | ✅ Approved | API responses not stored |
| Perplexity AI | Research automation | Perplexity API ToS | ✅ Approved | Responses processed per ToS |
| *Add as needed* | - | - | - | - |

### API Compliance Notes

#### Google APIs
- **Terms**: [Google Cloud Platform Terms](https://cloud.google.com/terms)
- **Attribution**: Required in documentation
- **Data Usage**: API responses must not be cached beyond ToS limits
- **Rate Limits**: Monitored and respected

#### Perplexity AI
- **Terms**: [Perplexity API Terms](https://www.perplexity.ai/api)
- **Attribution**: "Powered by Perplexity" required
- **Data Usage**: Responses used for internal research only
- **Rate Limits**: Monitored and respected

## License Categories

### ✅ Approved Licenses (No Review Required)

These licenses are pre-approved for use:

- **MIT License**: Very permissive, minimal restrictions
- **Apache License 2.0**: Includes patent grant, permissive
- **BSD 2-Clause**: Simple and permissive
- **BSD 3-Clause**: Simple and permissive
- **ISC License**: Similar to MIT

### ⚠️ Review Required

These licenses require legal review before use:

- **EPL 2.0** (Eclipse Public License): Weak copyleft
- **LGPL** (Lesser GPL): Limited copyleft
- **MPL 2.0** (Mozilla Public License): File-level copyleft
- **CDDL** (Common Development and Distribution License)
- **Custom Licenses**: Any non-standard license

### ❌ Blocked (Do Not Use)

These licenses are not compatible without special approval:

- **GPL v2/v3** (GNU General Public License): Strong copyleft
- **AGPL** (Affero GPL): Network copyleft
- **SSPL** (Server Side Public License): Restrictive
- **Commons Clause**: Restricts commercial use
- **Proprietary/Commercial**: Requires separate agreement

## Compliance Process

### Adding New Dependencies

1. **Identify License**: Check the dependency's license
2. **Verify Compatibility**: Compare against approved licenses
3. **Document**: Add to this file with all required information
4. **Review**: If not pre-approved, request legal review
5. **Approve**: Get approval before merging PR

### Updating Dependencies

1. **Check License Changes**: Verify license hasn't changed
2. **Review Breaking Changes**: Check release notes
3. **Update Documentation**: Update version in this file
4. **Test**: Verify compatibility with our code

### Regular Audits

**Frequency**: Quarterly

**Process**:
1. Run automated license scanner (e.g., `license-finder`, FOSSA)
2. Review output for any changes
3. Update this document
4. Flag any issues for legal review

## Automated Tools

### Recommended License Scanners

- **license-finder** (Ruby-based, open-source)
- **licensee** (GitHub's own tool)
- **scancode-toolkit** (Comprehensive, open-source)
- **FOSSA** (Commercial, comprehensive)
- **WhiteSource/Mend** (Commercial, includes security)

### Maven Configuration

Add to `pom.xml`:

```xml
<plugin>
    <groupId>org.codehaus.mojo</groupId>
    <artifactId>license-maven-plugin</artifactId>
    <version>2.0.0</version>
    <executions>
        <execution>
            <goals>
                <goal>add-third-party</goal>
            </goals>
        </execution>
    </executions>
</plugin>
```

### Python Configuration

Install and run:

```bash
pip install pip-licenses
pip-licenses --format=markdown --output-file=licenses.md
```

## Attribution Requirements

### Where Attribution is Required

- Documentation (README, docs)
- About pages
- Help/Support pages
- License/Legal pages

### Standard Attribution Format

```
This software uses the following open-source packages:

- [Package Name] (https://link) - [License Name]
  Copyright (c) [Year] [Author/Organization]
```

## Contact and Questions

For questions about license compliance:
- **Legal Team**: legal@ev-max-inc.com
- **Repository Maintainer**: See CONTRIBUTING.md
- **Compliance Issues**: Report via SECURITY.md

## Change Log

| Date | Change | Updated By |
|------|--------|------------|
| 2025-10-05 | Initial creation | Copilot Agent |
| - | - | - |

## Resources

- [Choose a License](https://choosealicense.com/)
- [SPDX License List](https://spdx.org/licenses/)
- [TLDRLegal](https://tldrlegal.com/)
- [Open Source Initiative](https://opensource.org/licenses)
