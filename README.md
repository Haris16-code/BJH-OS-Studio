# 📘 BJH OS Studio - The Ultimate Developer Guide

**Version:** 1.0.0  
**Developer:** Muhammad Haris  

---

## 📖 Table of Contents
1. [Introduction](#1-introduction)
2. [Installation & Requirements](#2-installation--requirements)
3. [Interface Overview](#3-interface-overview)
4. [Project Management](#4-project-management)
5. [The Editor & Workflow](#5-the-editor--workflow)
6. [Asset Management](#6-asset-management)
7. [BJH OS Integration APIs](#7-bjh-os-integration-apis)
8. [Compilation & Exporting](#8-compilation--exporting)
9. [Troubleshooting](#9-troubleshooting)

---

## 1. Introduction
**BJH OS Studio** is the official Integrated Development Environment (IDE) built to empower developers to create robust HTML5-based Applications and Games for the **BJH OS** ecosystem. 

It provides a "What You See Is What You Get" (WYSIWYG) experience with live previewing, syntax highlighting, and integrated asset management, stripping away the complexity of manual configuration.

---

## 2. Installation & Requirements

### System Requirements
* **OS:** Windows 10/11, Linux, or macOS
* **Storage:** 500 MB free
[Download BJH OS Studio Latest Version](https://github.com/Haris16-code/BJH-OS-Studio/releases/tag/bjh-os-studio-first-official-release)
---

## 3. Interface Overview
The Studio is designed with a modern, dark-themed (default) layout inspired by VS Code.

### Top Toolbar
* **New Project:** Start a fresh App or Game.
* **Open Project:** Load an existing folder.
* **Run App:** Refreshes the Live Preview.
* **Compile:** Validates and exports to .zip.
* **Check Updates:** Fetches the latest IDE version from GitHub.
* **About:** Developer credits.

### Left Panel (File Explorer)
* Shows the directory tree of your project.
* Supports Context Menu (Right-Click) operations.

### Center Panel (Code Editor)
* Tabbed editing for multiple files.
* Syntax highlighting for HTML, CSS, JS, and JSON.
* **Auto-Save Enabled:** Saves work automatically 1 second after typing stops.

### Right Panel (Live Preview)
* A Chromium-based web engine that renders your app in real-time.

### Bottom Panel (Console Log)
* Displays system messages, errors, and validation statuses.

---

## 4. Project Management

### Creating a New Project
1. Click **New Project**.
2. **App Name:** The visible title (e.g., "Super Calculator").
3. **Type:** 
   * `app`: Standard windows/utilities.
   * `game`: Full-screen immersive experiences.
4. **Location:** Parent directory.
5. **Icon:** Select a `.ico` file (Mandatory for BJH OS Desktop).

### Project Structure
BJH OS Studio automatically generates this structure:



⚠️ **Critical Warning:** Never delete `project_config.js`. It contains the `PROJECT_TYPE` constant that tells BJH OS how to launch your software.

---

## 5. The Editor & Workflow

### Syntax Highlighting
The editor automatically detects file extensions and colors code accordingly:

* **HTML:** Tags (Blue), Attributes (Light Blue), Strings (Orange)
* **JS:** Keywords (Purple), Functions (Yellow), Comments (Green)
* **CSS:** Properties (Purple), Values (Orange)

### Auto-Save System
You do not need to press Ctrl+S. The IDE features a "Debounce Save" mechanism.

**How it works:** When you stop typing for 1 second, the file is automatically written to the disk.  
**Feedback:** Check the bottom log panel for `"Saved: filename.ext"`.

---

## 6. Asset Management
BJH OS Studio v1.0 introduces a robust Context Menu for managing files without leaving the IDE.

### Right-Click Actions (File Tree)
| Action | Description |
|--------|-------------|
| 📄 New File | Creates an empty file (e.g., `utils.js`). |
| 📂 New Folder | Creates a subdirectory. |
| ⬇ Import File(s) | Opens a file picker to copy external files (images, music) into the selected folder. |
| 📦 Import Folder | Copies an entire external directory structure into your project. |
| ✏ Rename | Renames the selected item. |
| 🗑 Delete | Safely removes the item (closes open tabs first to prevent crashes). |

---

## 7. BJH OS Integration APIs
To ensure your app feels "Native," use these integration patterns.

### A. Font Synchronization
BJH OS users can set a custom system font. Your app inherits this via the mandatory script injected into `index.html`:

```javascript
// This runs automatically on load
document.addEventListener('DOMContentLoaded', () => {
  const storedFont = localStorage.getItem('selectedFont');
  if (storedFont) {
    document.body.style.fontFamily = storedFont;
  }
});
```

8\. Compilation & Exporting
---------------------------

When your development is complete, you must package the app for distribution.

### The Compilation Process

1.  Click **Compile**.
    
2.  **Validator Runs:**
    
    *   Checks if index.html exists.
        
    *   Checks if project\_config.js is valid.
        
    *   Scans for the Font Sync script.
        
3.  **Output:** If successful, a dialog asks where to save the .zip file.
    
4.  The IDE compresses the folder, excluding temporary files.
    

**Distribution:** Send the resulting .zip file to BJH OS users. They can install it via the BJH OS App Store or by extracting it to their apps folder.

9\. Troubleshooting
-------------------

### Common Issues

*   **Live Preview not updating:** Ensure your browser is Chromium-based and Run App is clicked.
    
*   **Compile fails:** Check console log for missing files or invalid project\_config.js.
    
*   **Assets not appearing:** Confirm the files are inside the assets/ folder.
