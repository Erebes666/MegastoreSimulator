# Changelog

All notable changes to this project will be documented in this file.

---

## [1.1.0] - 2026-04-19

### Added
- **Empty save slot detection** - when both `softCurrencyKey` and `currentLevelKey` are missing, the editor now shows a prominent error banner explaining that the user loaded an empty save slot, and hides the edit fields to prevent confusion.

### Improved
- Error messaging now distinguishes between a fully empty file and a file with partial data.

---

## [1.0.0] - 2026-04-19

### Initial release

- Load `Save_(0-4).data` files via click or drag-and-drop.
- Read and edit **money** (`softCurrencyKey`, `float32`).
- Read and edit **store level** (`currentLevelKey`, auto-detects `float32` / `int32`).
- Patch and download the modified save file directly in the browser.
- Displays original values alongside edit fields.
- 100% client-side - no data ever leaves the user's computer.
- Copy-to-clipboard button for the save file folder path.
- Warns users to keep a backup before replacing their save file.
