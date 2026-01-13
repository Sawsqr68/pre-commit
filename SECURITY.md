# Security Policy

## 🛡️ Supported Versions

Currently supported versions with security updates:

| Version | Supported          | Status |
| ------- | ------------------ | ------ |
| 4.5.x   | ✅ Yes | Active |
| 4.4.x   | ⚠️ Limited | Critical fixes only |
| < 4.4   | ❌ No | End of life |

## 🚨 Reporting a Vulnerability

**IMPORTANT: Please do NOT create public GitHub issues for security vulnerabilities.**

### How to Report

If you discover a security vulnerability, please report it by:

1. **Email**: Send details to the repository maintainer
2. **Private Security Advisory**: Use GitHub's private vulnerability reporting feature
3. **Direct Message**: Contact maintainers directly through secure channels

### What to Include in Your Report

Please provide:

- **Description**: Detailed explanation of the vulnerability
- **Impact**: What could an attacker do with this vulnerability?
- **Reproduction Steps**: Step-by-step instructions to reproduce
- **Affected Versions**: Which versions are impacted
- **Proof of Concept**: Code or screenshots (if applicable)
- **Suggested Fix**: If you have ideas for remediation
- **Your Contact Info**: For follow-up questions

### Response Timeline

We are committed to addressing security issues promptly:

| Severity | Initial Response | Status Update | Fix Timeline |
|----------|------------------|---------------|--------------|
| 🔴 Critical (9.0-10.0) | 24 hours | Daily | 7 days |
| 🟠 High (7.0-8.9) | 48 hours | Every 3 days | 30 days |
| 🟡 Medium (4.0-6.9) | 72 hours | Weekly | 60 days |
| 🟢 Low (0.1-3.9) | 1 week | Bi-weekly | 90 days |

## 🔐 Security Best Practices for Contributors

### Before Submitting Code

- [ ] Run security scanners locally: `bandit -r pre_commit/`
- [ ] Check for secrets: `detect-secrets scan`
- [ ] Update dependencies: `pip list --outdated`
- [ ] Sign commits with GPG
- [ ] Review OWASP Top 10 vulnerabilities

### Never Commit

- ❌ API keys, tokens, passwords
- ❌ Private keys or certificates
- ❌ Internal URLs or IP addresses
- ❌ Database credentials
- ❌ AWS/Cloud provider secrets
- ❌ Personal Identifiable Information (PII)

### Use Environment Variables

```python
# ❌ BAD
api_key = "sk-1234567890abcdef"

# ✅ GOOD
import os
api_key = os.environ.get('API_KEY')
```

## 🛠️ Security Features in This Project

### Code Security

- ✅ **Safe YAML parsing**: Using `yaml.safe_load()` instead of `yaml.load()`
- ✅ **Parameterized queries**: SQLite queries use parameterized statements
- ✅ **No dangerous functions**: No use of `eval()`, `exec()`, or `os.system()`
- ✅ **Subprocess safety**: All subprocess calls use `shell=False`
- ✅ **Input validation**: Comprehensive validation using `cfgv` library
- ✅ **Path sanitization**: File paths are validated and sanitized
- ✅ **Docker security**: Rootless mode support and security options

### Dependency Management

- ✅ **Automated updates**: Dependabot monitors for vulnerable dependencies
- ✅ **Version pinning**: Specific version requirements for security
- ✅ **Regular audits**: Weekly automated security scans
- ✅ **License compliance**: All dependencies use compatible licenses

### CI/CD Security

- ✅ **SHA pinning**: GitHub Actions pinned to specific commit SHAs
- ✅ **Code scanning**: Multiple SAST tools (Bandit, Semgrep, CodeQL)
- ✅ **Secret detection**: Automated scanning for leaked credentials
- ✅ **Dependency scanning**: Safety and pip-audit checks
- ✅ **Signed commits**: GPG signature verification

## 📋 Security Checklist for Pull Requests

When submitting a PR, ensure:

- [ ] No secrets or credentials in code/commits
- [ ] All dependencies are up to date
- [ ] Security tests pass locally
- [ ] Code reviewed for OWASP Top 10 issues
- [ ] Commit is signed with GPG
- [ ] Documentation updated if needed
- [ ] Breaking changes clearly documented

## 🔍 Known Security Considerations

### Docker Execution

This project executes Docker containers which may pose risks:

- **Risk**: Containers from untrusted sources
- **Mitigation**: Users should verify image sources
- **Best Practice**: Use official images and scan with Trivy/Snyk

### Git Hook Execution

Git hooks execute code automatically:

- **Risk**: Malicious hook configurations
- **Mitigation**: Review `.pre-commit-config.yaml` before installation
- **Best Practice**: Only use hooks from trusted repositories

### Subprocess Execution

The project executes external commands:

- **Risk**: Command injection if inputs not sanitized
- **Mitigation**: All inputs validated, no `shell=True`
- **Best Practice**: Users should audit hook commands

## 🏆 Security Hall of Fame

We appreciate security researchers who help us improve:

*No vulnerabilities reported yet. Be the first!*

## 📚 Resources

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [CWE/SANS Top 25](https://cwe.mitre.org/top25/)
- [GitHub Security Best Practices](https://docs.github.com/en/code-security)
- [Python Security Guide](https://python.readthedocs.io/en/stable/library/security_warnings.html)

## 📞 Contact

For security concerns, please contact the repository maintainer through GitHub.

## 🔄 Policy Updates

This security policy was last updated: 2026-01-13

We review and update this policy quarterly or after significant security incidents.

---

**Remember**: Security is everyone's responsibility. Thank you for helping keep this project secure! 🙏