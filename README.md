# Megastore Save Editor

A lightweight, browser-based save file editor for **Megastore Simulator** by Yolo Games Studio.

No installations, no servers, no data uploads - everything runs 100% locally in your browser.

---

## Features

- Edit your **money** (softCurrency) value
- Edit your **store level**
- Drag-and-drop or click-to-select your save file
- Detects and warns about empty save slots
- Downloads the patched file instantly, ready to drop back into your game folder

---

## How to Use

1. **Find your save file**
   ```
   C:\Users\YourUsername\AppData\LocalLow\Yolo Games Studio\Megastore Simulator\
   ```
   Save files are named `Save_0.data` through `Save_4.data`.

   > ⚠️ Make sure to pick a save slot that has an **active run** - empty slots or new slot with unfinished tutorial won't contain any data to edit.

2. **Back up your file** before making any changes (copy it somewhere safe).

3. **Open `megastore_save_editor.html`** in any modern browser.

4. **Load your save file** by dragging it onto the editor or clicking to browse.

5. **Edit the values** you want to change.

6. Click **Patch & Download** - the modified file will download automatically.

7. **Replace** the original file in the save folder with the downloaded one.

---
![App screenshot](https://github.com/Erebes666/MegastoreSimulator/blob/main/Assets/MegastoreSimulatorSaveEditor.gif)

![App screenshot](https://github.com/Erebes666/MegastoreSimulator/blob/main/Assets/Save_Editor.png)
---

## Compatibility

| Browser | Supported |
|---------|-----------|
| Chrome / Edge | ✅ |
| Firefox | ✅ |
| Safari | ✅ |

Tested on Windows 10/11. The editor is a single `.html` file with no dependencies.

---

## Technical Notes

Save files use Unity's `BinaryFormatter` serialization with UTF-16 LE encoded keys. The editor locates values by scanning for their key strings and patching the bytes at a fixed offset:

| Field | Key | Type | Offset from key end |
|-------|-----|------|---------------------|
| Money | `softCurrencyKey` | `float32` | 29 bytes |
| Level | `currentLevelKey` | `float32` / `int32` | 29 bytes |

---

## Disclaimer

This tool is provided for personal, single-player use only. Use at your own risk - always keep a backup of your original save file. This project is not affiliated with or endorsed by Yolo Games Studio.
