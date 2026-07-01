# Changelog

## 0.2.0 - 2026-07-01

### Added

- PPT-style element dragging and eight-handle resizing
- Live size feedback and `Shift`-key proportional resizing
- Undo and redo history for text, color, move, and resize edits
- `Ctrl` / `Cmd` shortcuts for undo, redo, and save
- GitHub Pages live demo links in the English and Chinese documentation
- Clear upstream attribution to `cxq0517/htmltool2` and its original author

### Fixed

- Prevented edited elements from changing position when edit mode is turned off
- Limited `contenteditable` to the active text element to avoid changing page layout

## 0.1.0 - 2026-06-04

Initial open-source release.

### Added

- Local single-file HTML editor
- Text editing mode
- Background and text color editing
- Color swatches and HEX inputs
- Drag-and-drop HTML loading
- Save as `*-edited.html`
- Dirty-state indicator
- Safer iframe sandbox without script execution
- Chinese and English documentation
