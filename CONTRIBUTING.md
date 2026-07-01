# Contributing / 贡献指南

Thanks for your interest in improving this project.

感谢你愿意改进这个项目。

## Development

This project is intentionally simple. There is no build step.

```bash
python -m http.server 8765
```

Then open:

```text
http://127.0.0.1:8765/index.html
```

You can also open `index.html` directly in a browser.

## Pull Requests

Please keep pull requests focused and small.

Good changes include:

- Bug fixes for text editing or color editing
- Browser compatibility improvements
- UI polish that keeps the app lightweight
- Documentation improvements
- Test cases in `test.html`

Please avoid:

- Adding a build system unless it is clearly necessary
- Adding network services or analytics
- Broad refactors unrelated to the change
- Enabling script execution by default

## Manual Test Checklist

Before opening a pull request, please check:

- Open `index.html`
- Load `test.html`
- Enable edit mode
- Edit text
- Change background color
- Change text color
- Save the edited file
- Reopen the saved file
- Confirm the iframe sandbox still does not include `allow-scripts`

## Commit Style

Use short, descriptive commit messages, for example:

```text
fix text deletion guard
improve color panel layout
docs add English README
```
