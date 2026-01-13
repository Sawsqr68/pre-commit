# Security Policy

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| 4.5.1   | :white_check_mark: |
| < 4.5.1 | :x:                |

## Reporting a Vulnerability

If you discover a security vulnerability in this project, please report it by emailing the maintainers at [asottile@umich.edu](mailto:asottile@umich.edu).

**Please do NOT create a public GitHub issue for security vulnerabilities.**

### What to Include in Your Report:
- Description of the vulnerability
- Steps to reproduce the issue
- Potential impact
- Suggested fix (if any)

### Response Timeline:
- **Initial Response**: Within 48 hours
- **Status Update**: Within 7 days
- **Fix Timeline**: Depends on severity (Critical: 7 days, High: 30 days, Medium: 60 days)

## Security Best Practices

When contributing to this project:
- Never commit secrets, API keys, or credentials
- Use signed commits (GPG)
- Keep dependencies up to date
- Follow secure coding practices
- Run security scans before submitting PRs

## Security Features

This project implements:
- Safe YAML parsing (no `yaml.load`)
- Parameterized queries for SQLite
- No use of `eval()`, `exec()`, or `os.system()`
- Subprocess execution without `shell=True`
- Input validation using `cfgv`

## Vulnerability Disclosure

We practice responsible disclosure and will:
1. Acknowledge your report within 48 hours
2. Provide regular updates on our progress
3. Credit researchers (unless they prefer to remain anonymous)
4. Publish security advisories for confirmed vulnerabilities
