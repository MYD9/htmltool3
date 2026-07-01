# Security Policy

## Supported Versions

This project is currently pre-1.0. Security fixes are applied to the latest version in the default branch.

## Reporting a Vulnerability

If you find a security issue, please open a GitHub issue with a minimal reproduction and mark it clearly as security-related.

Do not include private HTML files, credentials, tokens, or personal data in public reports.

## Security Model

The editor is designed to run locally in the browser.

Important defaults:

- User HTML is previewed in an iframe
- The iframe sandbox does not include `allow-scripts`
- Files are not uploaded by the app
- Saved output is generated locally through the browser

Known risks:

- Enabling scripts in previews would increase risk
- Browser DOM serialization may preserve unexpected runtime state if scripts are enabled in a fork
- Untrusted HTML can still contain sensitive content, links, forms, or external assets
