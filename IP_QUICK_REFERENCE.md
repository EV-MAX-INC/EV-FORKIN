# IP Compliance Quick Reference Card

## 🚀 Quick Checklist - Before You Commit

- [ ] No API keys, passwords, or credentials in code
- [ ] All code is original work
- [ ] Third-party code properly attributed
- [ ] New dependencies documented with licenses
- [ ] No proprietary code from previous employers

## ✅ Safe to Use - Pre-Approved Licenses

| License | Use Freely | Notes |
|---------|-----------|-------|
| MIT | ✅ | Most permissive |
| Apache 2.0 | ✅ | Includes patent grant |
| BSD (2/3-Clause) | ✅ | Simple and permissive |
| ISC | ✅ | Similar to MIT |

## ⚠️ Need Review - Check Before Using

| License | Action Required | Why |
|---------|----------------|-----|
| GPL/LGPL | Legal review needed | Copyleft requirements |
| AGPL | Legal review needed | Network copyleft |
| EPL | Legal review needed | Weak copyleft |
| Custom licenses | Legal review needed | Unknown terms |

## ❌ Do Not Use - Blocked

| License | Don't Use | Reason |
|---------|----------|--------|
| GPL v2/v3 | ❌ | Strong copyleft |
| AGPL | ❌ | Network copyleft |
| SSPL | ❌ | Restrictive |
| No license | ❌ | Default copyright applies |

## 🔍 Before Adding a Dependency

1. **Find the license**: Check `LICENSE` file or package metadata
2. **Verify compatibility**: Use the tables above
3. **Document it**: Add to `DEPENDENCIES.md`
4. **If unsure**: Ask in PR or contact legal team

## 📝 How to Document Dependencies

### In DEPENDENCIES.md:

```markdown
| Dependency | Version | License | Status | Notes |
|------------|---------|---------|--------|-------|
| package-name | 1.2.3 | MIT | ✅ Approved | Brief purpose |
```

## 🔗 Using External APIs

**Before integrating an API, verify:**

- [ ] Terms of Service allow commercial use
- [ ] Data handling requirements understood
- [ ] Rate limits documented
- [ ] Attribution requirements noted
- [ ] Privacy compliance checked

**Document in DEPENDENCIES.md:**

```markdown
| Service | Purpose | License/ToS | Status | Data Handling |
|---------|---------|-------------|--------|---------------|
| API Name | What it does | Link to ToS | ✅ | Notes |
```

## 💡 Attribution Format

When using third-party code:

```java
/*
 * Based on: [Original Source URL]
 * License: [License Type]
 * Author: [Original Author]
 * Modifications: [What you changed]
 */
```

```python
"""
Based on: [Original Source URL]
License: [License Type]
Author: [Original Author]
Modifications: [What you changed]
"""
```

## 🚫 Never Commit

- `*.key`, `*.pem` - Private keys
- `.env`, `secrets.yml` - Environment configs
- `*password*`, `*credential*` - Credentials
- `*secret*` - Secret tokens
- Customer data or PII

**Already committed?** Contact security team immediately!

## 📚 Common Questions

### Q: Can I use code from Stack Overflow?
**A:** Only if it has a compatible license (CC BY-SA) and you attribute it. Better to understand and rewrite in your own words.

### Q: Can I use GPL libraries?
**A:** Not without legal approval - GPL requires your code to also be GPL.

### Q: What if I can't find a license?
**A:** Assume it's proprietary. Don't use it. Find an alternative.

### Q: Can I copy code from my previous employer?
**A:** No, unless you own the copyright or have explicit permission.

### Q: How do I handle AI-generated code?
**A:** Review it carefully. You're responsible for ensuring it doesn't violate IP. Don't blindly copy AI suggestions.

## 🆘 Need Help?

- **Legal Team**: legal@ev-max-inc.com
- **Full Guidelines**: [IP_COMPLIANCE.md](IP_COMPLIANCE.md)
- **Dependencies**: [DEPENDENCIES.md](DEPENDENCIES.md)
- **Security Issues**: [SECURITY.md](SECURITY.md)

## 🎯 Remember

1. **When in doubt, ask** - It's easier to get approval than fix issues later
2. **Document everything** - Track all dependencies and licenses
3. **Original is best** - Write your own code when possible
4. **Read the terms** - Don't assume, verify
5. **Protect secrets** - Never commit sensitive data

---

**This is a quick reference. Always consult the full [IP_COMPLIANCE.md](IP_COMPLIANCE.md) for details.**

**Last Updated**: 2025-10-05
