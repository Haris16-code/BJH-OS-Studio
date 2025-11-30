# 📘 BJH OS Studio - The Ultimate Developer Guide

**Version:** 1.0  
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
10. [Uploading Apps/Games To BJH OS Official Apps Market](#%EF%B8%8F-how-to-upload-apps-to-bjh-os-apps-market)

---

## 1. Introduction
**BJH OS Studio** is the official Integrated Development Environment (IDE) built to empower developers to create robust HTML5-based Applications and Games for the **BJH OS** ecosystem. 

It provides a syntax highlighting, and integrated asset management, stripping away the complexity of manual configuration.

---

## 2. Installation & Requirements

### System Requirements
* **OS:** Windows 10/11, Linux, or macOS
* **Storage:** 500 MB free
### [Download BJH OS Studio Latest Version](https://github.com/Haris16-code/BJH-OS-Studio/releases/tag/bjh-os-studio-first-official-release)
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
---
# 🛠️ How To Upload Apps To BJH OS Apps Market

The **BJH OS Apps Market** allows developers to upload apps and games for BJH OS users. Developers can manage app updates, monitor downloads, view reviews, and interact with users through their dashboard. This guide explains how to upload apps safely, efficiently, and use the points system for promotions.

---

## 📑 Table of Contents

1. [Developer Account Setup](#1-developer-account-setup)
2. [Accessing the Developer Dashboard](#2-accessing-the-developer-dashboard)
3. [Uploading a New App/Game](#3-uploading-a-new-appgame)
4. [Updating an Existing App/Game](#4-updating-an-existing-appgame)
5. [App Statistics & Review Management](#5-app-statistics--review-management)
6. [Points System](#6-points-system)
    - [How You Earn Points](#how-you-earn-points)
    - [What You Can Use Points For](#what-you-can-use-points-for)
7. [How to Promote Your Apps](#7-how-to-promote-your-apps-in-the-bjh-os-apps-market)
    - [Method 1 — Promotion Panel](#method-1-promote-from-the-promotion-panel)
    - [Method 2 — My Apps Page](#method-2-promote-from-the-my-apps-page)
    - [After Approval](#what-happens-after-approval)
    - [Notifications](#notifications)
8. [Best Practices](#8-best-practices)
9. [Support](#9-support)

---

## 1. Developer Account Setup

Before uploading apps, you must have a **BJH OS Developer Account**.

1. Go to the [BJH OS Account Registration](https://bjh-os-apps-market.base44.app/profile) page.  
2. When your account is created and you log in, go to your **profile** at the top right and enable **Developer Mode** in **Developer Settings**.  
3. Fill in the required details:  
   - **Developer/Company Name**  
   - **Your Website** (Optional but recommended)  
   - **Bio** (Tell users about yourself)  
4. Click **Save Changes**.  
5. Press your **Profile Picture** at the top right; you will see a new option: **Developer Dashboard**.  

---

## 2. Accessing the Developer Dashboard

1. Click on **Developer Dashboard**.  
2. The dashboard displays:  
   - Your uploaded apps/games  
   - App statistics: downloads, ratings, reviews  
   - Upload/update options  
   - **Promotions** (use points to promote apps)  
   - Notifications from the system/admin  

---

## 3. Uploading a New App/Game

1. Click **“Upload New App/Game”** on your dashboard.  
2. Fill in the required details:  
   - **App/Game Icon** (recommended: 512x512px, PNG)  
   - **App/Game Name**  
   - **Description** (brief and full description)  
   - **Screenshots or Video** (optional; first media item shown in preview)  
   - **Category** (e.g., Games, Productivity, Tools)  
   - **Version Number** (e.g., 1.0.0)  
   - **Download File (ZIP)** containing the app/game  
   - **Support Email** (optional but recommended)  
   - **Support Website** (optional but recommended)  

3. Review your app/game details carefully.  
4. Click **Submit for Review**.  
   - Admin will review your app.  
   - Once approved, you will receive an email notification, and the app will appear in the BJH OS Apps Market.  
   - If rejected, you will receive a notification with the reason.

---

## 4. Updating an Existing App/Game

1. Go to **Your Apps** in the dashboard.  
2. Click **Update** next to the app.  
3. Update the fields as needed:  
   - Version number  
   - Description  
   - Screenshots or video  
   - ZIP file with updated app/game  

4. Submit the update for admin approval.  
5. After approval, the new version replaces the previous one.

---

## 5. App Statistics & Review Management

- Monitor **downloads**, **ratings**, and **reviews**.  
- Comment on user reviews to provide support or gather feedback.  
- Track which updates or features users appreciate most.

---

## 6. Points System

BJH OS Apps Market uses a **points system** to promote apps and reward developers.

### How You Earn Points

- Receive **50 points** when you log in as a developer for the first time.  
- Uploading each app/game grants **50 points**.  
- Completing your profile and providing support info may earn bonus points (if offered).  

### What You Can Use Points For

- Promote your apps in the BJH OS Apps Market.  
- Choose the promotion audience based on points:  
  - **High Audience** = more points required  
  - **Medium Audience** = moderate points  
  - **Low Audience** = fewer points  
- Points are deducted when a promotion is approved. If the promotion is rejected, points are refunded.  

**Notes:**  
- Plan promotions strategically to maximize visibility.  
- Points reset or earning opportunities may be updated periodically by BJH OS.

---

## 7. How to Promote Your Apps in the BJH OS Apps Market

The BJH OS Apps Market includes a **promotion system** powered by points that developers earn. These points can be used to boost visibility and reach more users.

### ⭐ Ways to Promote Your App

You can promote your app in **two different ways** inside the Developer Dashboard.  
**Both methods have the same effect — only the method to access the promotion differs.**

---

### Method 1 — Promote from the “Promotion” Panel

1. Open your **Developer Dashboard**.  
2. Click on the **Promotion** section.  
3. Select the app you want to promote.  
4. Enter the number of **points** you want to spend.  
5. Submit the promotion request.  
6. The request goes to the **admin for approval**.  

---

### Method 2 — Promote from the “My Apps” Page

1. Go to **My Apps** inside your Developer Dashboard.  
2. Each app shows a **Promote** button.  
3. Click **Promote**, enter the points, and submit the request.  
4. Admin reviews the promotion.

---

### What Happens After Approval

- Your app appears in **Search Suggestions**  
- May appear in **Trending / Popular Sections**  
- Listed as a **Sponsored App**  
- Appears in **Top Rated / Highlighted Areas** (depending on points)  
- Promotion duration depends on **points spent**  

**Higher points = longer visibility**  
**Lower points = shorter visibility**

---

### Notifications

You will be notified in your dashboard when:

- Promotion is **approved**  
- Promotion is **rejected** (points refunded automatically)  
- Any promotion-related system messages  

---

### Tip for Developers

Use promotions when:

- Releasing a new app  
- Uploading a major update  
- Wanting to boost downloads  
- Competing in a crowded category  

Strategic promotions can help your app reach **thousands of BJH OS users!**

---

## 8. Best Practices

- Use **high-quality icons, screenshots, and videos**.  
- Keep **descriptions clear and informative**.  
- Test your app/game thoroughly before upload.  
- Update apps regularly to fix bugs and add new features.  

---

## 9. Support

If you encounter issues during upload or updates, contact BJH OS support via:  
- Email: `muhammad.haris662007@gmail.com`  
- Developer dashboard support form  

---

This documentation ensures developers can **upload apps efficiently, track stats, use points to promote apps, and engage users** in BJH OS Apps Market.
