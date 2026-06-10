# CattitudeFlow User Manual

## Table of Contents

1. [Overview](#overview)
2. [Screen Layout](#screen-layout)
3. [Home Screen](#home-screen)
4. [Notes Screen](#notes-screen)
5. [Tickets Screen](#tickets-screen)
6. [Focus Screen](#focus-screen)
7. [OCR Memo Screen](#ocr-memo-screen)
8. [Settings Screen](#settings-screen)
9. [Search Syntax Reference](#search-syntax-reference)
10. [Keyboard Shortcuts](#keyboard-shortcuts)
11. [FAQ](#faq)
12. [Troubleshooting](#troubleshooting)

---

## Overview

**CattitudeFlow** is a desktop application that combines Cornell-style note-taking with ticket management.

Notes are written in Markdown format and support a Cornell-style format made up of three panes: **Cue / Note / Summary**.  
Tickets can have multiple Cornell-style **Memos**, allowing you to keep detailed records related to each task.  
In v1.0.5, in addition to the **OCR Capture** feature that imports on-screen text directly into the app, new features were added including free-floating **sticky notes** on the note body, a **Presentation view** for screen sharing, and **Markdown math (KaTeX)**.

---

## Screen Layout

### Header Navigation

The following navigation buttons are displayed in the header at the top of the app.

| Button | Description |
|--------|-------------|
| Home | List and search notes, tickets, and TODOs |
| Notes | Create and edit Cornell-style notes |
| Tickets | Manage tasks and tickets |
| Focus | List notes/tickets by importance score |
| OCR Memo | List and edit memos imported by OCR capture |
| Settings | App settings |

### InfoPill

The following information is shown on the right side of the header.

- **Days remaining**: Remaining days in the trial period (example: 7 days left)
- **Free space**: Disk free space status (OK / Low)

### Window Controls

These appear at the far right of the header when running as a native app.

| Button | Action |
|--------|--------|
| `_` | Minimize |
| `□` | Maximize / Restore |
| `×` | Close |

### Title Bar Quick Buttons

| Button | Action |
|--------|--------|
| `✂` | Open the Snippet Manager dialog (`Ctrl+I`) |
| `☀` | Toggle Spotlight on/off |
| `☀ ▾` | Switch the current spotlight preset |
| `🖥` Presentation view | Toggle **Presentation view** ON/OFF to improve the legibility of the live preview / preview (for screen sharing) |

The snippet button shows a badge with the number of registered items. The color of the spotlight button follows the currently selected preset color.

**Presentation view** emphasizes the font size, line spacing, and contrast of the live preview and preview so it stays readable during screen sharing. The ON/OFF state is remembered in the app and does not affect the theme colors or your saved data.

### System Tray Menu

Right-click the system tray icon to display the following menu.

| Item | Description |
|------|-------------|
| Show / Hide | Toggle the main window display |
| Spotlight | Toggle Spotlight on/off |
| Snippet | Open the Snippet Manager dialog |
| OCR | Start screen capture |
| Exit | Quit the app |

The currently configured global hotkey is shown on the right side of each item.  
You can customize hotkeys in Settings → Shortcut Keys.

---

## Home Screen

The Home screen has a three-column layout consisting of the left menu, center list, and right Peek preview.

### Left Panel (Menu)

**Filter List**

| Item | Description |
|------|-------------|
| Notes | Show notes only |
| Tickets | Show tickets only |
| TODO | Show TODO items from all notes |
| Images | Show a list of attached images |
| All | Show notes + tickets + TODOs together |

Each item shows a count. When a tag is selected, it is displayed in the format `tag count / total count`.

**Tag Filter**

Tags from notes and tickets are merged and shown as chips.  
Click a tag to display only items with that tag. Click `All` to clear the filter.

### Center Panel (List)

**Search Bar**

- Placeholder: `Full-text search (Ctrl+K) e.g. has:url code:powershell foo`
- Press `Ctrl+K` to focus
- Use the `Clear` button to reset the search term
- Typing `::` quickly opens the pinned snippet modal

**Filter Chips**

Filter chips are displayed below the search bar (All / Notes / Tickets / TODO).  
When TODO is selected, a **Scope** chip is also shown (All / Today).  
When a date filter is active, a `date: YYYY-MM-DD ×` chip appears and can be clicked to remove it.

**List Operations**

| Action | Behavior |
|------|------|
| Single click | Show Peek preview in the right pane |
| Double click | Go to the corresponding Notes/Tickets screen |
| `Ctrl+Click` | Go to the corresponding screen |
| `Enter` | Go to the corresponding screen |

**Ticket Memo Rows**

If memos are registered for a ticket, they are displayed as child rows below the ticket row.
Tickets with memos show a `▼ / ▶` toggle to collapse or expand the memo tree.

| Action | Behavior |
|------|------|
| Single click | Go to the Tickets screen and open the memo |
| `⛶` (fullscreen button) | Show the memo in fullscreen preview without the list |

**When the Images Tab Is Selected**

- Displays image thumbnails, paths, creation dates, sizes, and reference counts
- A dedicated search bar is shown (search by uid / relPath)
- You can load more items by scrolling to the bottom of the list

### Right Panel (Peek Preview)

Single-click an item to show its preview in the right pane.

- Notes: Cornell-style preview (Cue / Note / Summary)
- Tickets: Ticket information preview
- Images: Image preview and a list of referenced notes/tickets
- Ticket Memos: Cornell-style memo preview (without the list panel)
- **Fullscreen button** (⛶): Show the preview in fullscreen
- **Zoom toggle**: Switch the Cornell-style preview size (single-page / readable)
- Files changed in an external editor are also detected automatically and reflected in the list and preview

### Home Screen Keyboard Shortcuts

| Shortcut | Action |
|----------------|------|
| `Ctrl+K` | Focus the search bar |
| `Ctrl+Shift+T` | Apply today's date filter and show the current month calendar |

---

## Notes Screen

### Layout

The Notes screen has a two-column layout: a **left list** and a **right editor**.

### Left Panel (Note List)

**Creating a New Note**

- Open the new note dialog from the `New` button or `+`
- Enter a title and date (default: today) to create it
- If a note with the same title already exists, the existing note opens

**Creating a Child Note**

- Click the `+ Child Note` button while a note is selected to create a child note of the selected note
- Child notes are displayed as indented rows in the list
- If the currently open note is already a child note, a sibling note with the same parent is created instead (grandchild notes are not created)

**Search**

- Press `/` to focus the search bar
- You can full-text search note content using the host's full-text search

**Tag Filter**

Click a tag chip to narrow notes by tag.

**Pinning**

- Use the ★ icon on a note row to toggle pinning
- Pinned notes appear at the top of the list
- They are shown in separate `Pinned` and `All` sections
- Pinning is persisted in the Workspace (up to 100 items)

### Right Panel (Editor)

**Metadata Fields**

| Field | Description |
|------------|------|
| Title | Note title (required) |
| Date | YYYY-MM-DD format (example: 2026-04-26) |
| Tags | Comma-separated (example: ops, daily) |

**Cornell-style Editor**

The note body consists of the following three panes.

| Pane | Purpose |
|--------|------|
| **Cue** | Questions, keywords, hints |
| **Note** | Main content, detailed notes |
| **Summary** | Summary, conclusion |

**Pane Display Mode**

You can switch the display mode with the pane mode toggle.

| Mode | Display |
|--------|------|
| `1` | Single pane (only the active pane is shown) |
| `2` | Two panes |
| `3` | Three panes (all panes shown at the same time) ※ Default |

The selected mode is applied immediately, and the previous display mode is restored when you open the note again.

**Tab Switching**

| Tab | Description |
|------|------|
| Edit | CodeMirror editor |
| Preview | Markdown preview (with table of contents) |

- While editing, press `Ctrl+F` to open the search panel localized to the app display language
- On the Preview tab, PDF export is available with the current background color reflected

**Markdown Toolbar**

You can insert various formatting from the toolbar above the Edit tab.

| Button | Format |
|--------|------|
| Bold | `**text**` |
| Italic | `*text*` |
| Strikethrough | `~~text~~` |
| Underline | `<u>text</u>` |
| Text color | `<span style="color:#XXXXXX">text</span>` (20 colors) |
| Bullet list | `- text` |
| Numbered list | `1. text` |
| TODO list | `- [ ] text` |
| Table | Insert a table template |
| Alert box | GFM alerts (NOTE / TIP / IMPORTANT / WARNING / CAUTION) |
| Heading | H1 / H2 / H3 |

**Text Color Palette (20 colors)**

Red / Crimson / Orange / Amber / Yellow / Lime / Green / Teal / Cyan / Sky /  
Blue / Indigo / Purple / Violet / Pink / Rose / Brown / Slate / Gray / Black

**Pasting Images**

When you paste an image from the clipboard into the editor, it is automatically saved to the Workspace and inserted using Markdown image syntax.  
During import, an `Importing image…` overlay is shown.

**Sticky notes**

You can place free-floating sticky notes on top of the note body. Right-click inside the editor body and choose `Add sticky note` from the context menu.

- A newly added sticky note receives focus automatically so you can start typing right away (focus is not stolen while you type)
- Drag the top bar to move it. Each note is anchored to a position in the body, so it follows scrolling and edits
- Use the color button at the top-left to cycle the color (Yellow → Pink → Blue → Green)
- Drag the bottom-right corner of the text area to resize it; the new size is saved
- Click the `✕` button to delete it (with a confirmation dialog)
- Press `Ctrl+;` to insert the date and `Ctrl+Shift+;` to insert the time
- Sticky notes are saved inside the note body, so they are also included in Zip backups

**Math**

The Markdown preview and live preview support math rendering via KaTeX.

- Inline math: `$E = mc^2$`
- Block math: wrap it in `$$` on its own lines

```
$$
\int_0^1 x^2 dx = \frac{1}{3}
$$
```

**Save Status**

The save state is shown in the upper-right corner.

| State | Display |
|------|------|
| Saved | `Saved` |
| Unsaved | `Unsaved` |
| Saving | `Saving…` |

- Fonts for editor content and preview content can be changed in Settings → Editor
- If a note file is updated in an external editor, it is automatically reloaded as well

**Deletion**

You can delete a note from the trash icon. If it is pinned or has unsaved changes, a warning is shown.  
If child notes exist, a confirmation dialog asks whether to delete the child notes as well.

### Notes Screen Keyboard Shortcuts

| Shortcut | Action |
|----------------|------|
| `Ctrl+Enter` or `Ctrl+S` | Save |
| `Ctrl+1` | Jump to the Cue pane |
| `Ctrl+2` | Jump to the Note pane |
| `Ctrl+3` | Jump to the Summary pane |
| `Ctrl+E` | Switch to the Edit tab |
| `Ctrl+P` | Switch to the Preview tab |
| `/` | Focus the note search bar |

---

## Tickets Screen

Tickets are used to manage tasks and to-dos. They support a Cornell-style body, status management, comments, and memos.

### Left Panel (Ticket List)

**Search and Filtering**

| Action | Description |
|------|------|
| `/` key | Focus the search bar |
| Priority filter | All / P0 / P1 / P2 / P3 |
| Sort | Updated date / due date / priority |

**Creating a New Ticket**

- Click the `New` button to display the title input form
- Enter a title and press `Enter` to create it

**Memo List**

When you select a ticket, the memos registered for that ticket are listed in the lower area.

| Action | Description |
|------|------|
| Click a memo row | Open that memo in the right panel |
| `👁` icon | Hide / show the memo in the list |
| `🗑` icon | Delete the memo (confirmation dialog shown) |

### Right Panel (Ticket Editor)

When you select a ticket, the editor appears in the right panel.

**Metadata Fields**

| Field | Description |
|------------|------|
| Title | Ticket title (required) |
| Status | Custom column (changeable in Settings, example: backlog / doing / done) |
| Due date | YYYY-MM-DD format |
| Priority | P0 (highest) / P1 / P2 / P3 (lowest) |
| Labels | Comma-separated (example: urgent, ops) |

**Tab Switching**

| Tab | Description |
|------|------|
| Edit | Cornell-style editor (Cue / Note / Summary) |
| Preview | Markdown preview (Cornell-style 3-pane layout) |
| Comments (n) | Add and view comments |
| Memo | List and edit memos for the selected ticket |

**Deletion**

Delete a ticket with the trash icon (confirmation dialog shown).  
If memos are registered, the confirmation message includes the memo count.

### Memo Feature

You can add multiple Cornell-style **Memos** to a ticket. Meeting notes, research logs, and supplementary materials can be organized separately from the main ticket.

**Adding a Memo**

- You can create one immediately from the `+ Add Memo` button in the `Memo` tab or the button with the same name at the bottom of the left panel
- The default title of a new memo is `Memo`

**Memo Editor**

The memo editor uses the same Cornell layout as notes, and supports switching between 1 / 2 / 3 pane display modes.

| Tab | Description |
|------|------|
| Edit | Cornell-style editor (Cue / Note / Summary) |
| Preview | Markdown preview (Cornell-style 1 / 2 / 3 pane layout) |

- Auto-save starts as soon as you enter the title
- Pane mode changes are applied immediately and kept the next time as well
- PDF export is available on the Preview tab
- As with notes, right-click inside the Note pane body and choose `Add sticky note` to place sticky notes

**Memo Sorting**

Use the `▲` / `▼` buttons shown on each memo row in the memo list to change the memo order.

**Memo Operations**

| Action | Description |
|------|------|
| Click a memo row | Open the memo editor |
| `👁` icon | Hide / show the memo in the list (data is retained) |
| `🗑` icon | Delete the memo (confirmation dialog shown) |
| `⛶` (fullscreen) | Open the memo in fullscreen view without the list panel |
| `▲` / `▼` | Change the display order of the memo |

> Memos belong to a ticket, and deleting the ticket also deletes its memos.

### Tickets Screen Keyboard Shortcuts

| Shortcut | Action |
|----------------|------|
| `Ctrl+Enter` | Save |
| `/` | Focus the search bar |

---

## Focus Screen

This screen displays important notes and tickets in score order for concentrated review and viewing.

### Display Mode

| Mode | Description |
|--------|------|
| Notes | Display notes in score order |
| Tickets | Display tickets in score order |

### Scoring

Note scores are calculated from the following factors.

- **Edit count** (last 30 days): Can be turned on/off in Settings
- **Incoming links**: Number of times referenced from other notes

### Layout

| Area | Content |
|------|------|
| Left list | Rank, title, reference count, updated date |
| Right preview | Cornell-style preview of the selected note |
| `Max` | Maximum number of items shown in the list (5–200) |

### Operations

| Action | Behavior |
|------|------|
| Click | Select a note and show its preview |
| Double click / `Enter` | Open in the Notes/Tickets screen |
| `Fullscreen` button | Open the fullscreen viewer |

### Fullscreen Viewer

- You can switch items from the left list
- You can search titles with the search bar
- Click the `Open` button to go to the corresponding screen
- Press `ESC` or `Close` to exit

### Snippet Search and Pinning

- When the search bar is empty, the page stays in Focus mode and shows items ranked by edit-frequency score
- When you enter a keyword, it switches to Snippet mode and highlights only matching Cornell panes
- Typing `::` quickly opens the pinned snippet modal so you can copy snippets
- You can open the Snippet Manager dialog at any time with the `✂` button in the title bar or `Ctrl+I`

### Focus Screen Keyboard Shortcuts

| Shortcut | Action |
|----------------|------|
| `Enter` | Open the selected item |
| `ESC` | Close the fullscreen viewer |

---

## OCR Memo Screen

You can capture any area on the screen, recognize the text, and automatically save, browse, and edit it as an **OCR Memo**.  
Supported recognition languages are Japanese, English, Chinese, Korean, French, and German.

### Starting OCR Capture

Start capture in either of the following ways.

| Method | Action |
|------|------|
| Global hotkey | Press `Ctrl+Shift+F12` (default) |
| system tray | Right-click the tray icon → select **OCR** |

After capture starts, the screen becomes semi-transparent. Drag the mouse to select the rectangular area you want to recognize, and OCR processing will run.

### OCR Memo List

Click **OCR Memo** in the header to open the list screen.

| Column | Content |
|----|------|
| Capture date/time | Date and time when OCR was run |
| Recognized text | Leading portion of the OCR result |

### OCR Memo Editor

Select a memo from the list to open the editor.

**Image Area (when `Save image` is ON in Settings)**

The cropped screenshot is shown as a pinned card on a cork board background.

**Text Area**

The text recognized by OCR is displayed in a Markdown editor.  
You can freely edit and correct the content.

| Action | Description |
|------|------|
| Edit text | Modify directly in the editor |
| Copy | Copy the text to the clipboard |
| Delete | Delete the selected memo (confirmation dialog shown) |

### Delete All

Click the **Delete All** button at the top of the list to show a confirmation dialog.  
After confirmation, all OCR Memos are deleted.

> ⚠️ **This action cannot be undone.** Copy any required text beforehand.

---

## Settings Screen

You can change various settings from **Settings** in the header. Select a category from the left sidebar.

### General

| Setting | Description |
|------|------|
| Language | UI display language (system / ja / en / zh / ko / fr / de) |
| Locale | Locale for number/date formatting (leave blank to use OS settings, example: ja-JP) |
| Theme preset | Color theme |

- `Preview`: Immediately preview the selected theme
- `Save theme`: Save the theme to the host
- `Save language/locale`: Save language settings
- The saved language is also reflected in native/built-in UI such as file dialogs, startup errors, and the `Ctrl+F` search panel

### Workspace

| Setting | Description |
|------|------|
| WorkspaceRoot | Save path for notes and tickets |

- `Reload`: Re-fetch the current Workspace setting
- `Save`: Save the changed path

### Notes

| Setting | Description |
|------|------|
| Auto-save | Whether to auto-save while typing (ON/OFF) |
| Auto-save interval (ms) | Auto-save interval (200–10,000 ms, local UI setting) |

### Editor

| Setting | Description |
|------|------|
| Font family | Font used for editor content and preview content |
| Font size (px) | Body font size |
| Preview background rendering | When ON, card and code block backgrounds are rendered. When OFF, all backgrounds become transparent. This setting also applies to PDF export. (default: OFF) |
| Use theme color for headings & tables | When ON, headings and table headers reflect the theme accent (primary) color. When OFF (default), they use the body text color, matching the calm look of PDF export. |

- Values being typed are previewed immediately even before saving
- Use `Reset to default` to restore the defaults (font, background rendering OFF, theme color OFF)

### Tickets

| Setting | Description |
|------|------|
| Auto-save | Whether to auto-save when editing tickets (ON/OFF) |
| Auto-save interval (ms) | Auto-save interval (local UI setting) |
| Columns | Ticket status options (comma-separated)<br>Example: `backlog, doing, done, blocked, archived` |
| Show ticket ID | Show ticket IDs in lists/previews, etc. (local UI setting) |

### Focus

| Setting | Description |
|------|------|
| Max items | Maximum number of items on the Focus screen |
| Use edit count for ranking | Add note.save count to the Focus score |
| Activity log | Enable edit-count aggregation (note content and search queries are not stored) |

> ※ Consecutive saves caused by auto-save are rounded and counted as once per minute.

### Spotlight

| Setting | Description |
|------|------|
| Presets 1–5 | Choose the spotlight to use from five fixed presets |
| Name | Display name for each preset (up to 20 characters) |
| Size (px) | Spotlight circle diameter (20–200 px) |
| Color | Color of the spotlight circle and header icon |
| Opacity | Spotlight transparency |

- You can toggle it on/off with the `☀` button in the title bar
- `↩ Reset to default` restores the default color and size

### Shortcut Keys

You can change the global hotkeys (WPF level).

| Shortcut | Default | Description |
|----------------|-----------|------|
| Show / Hide | `Ctrl+Shift+F9` | Toggle the main window display |
| Spotlight | `Ctrl+Shift+F10` | Toggle Spotlight on/off |
| Snippet | `Ctrl+Shift+F11` | Open the Snippet Manager dialog |
| OCR Memo | `Ctrl+Shift+F12` | Start OCR capture |

**How to change them**

1. Click the input field for the shortcut you want to change (`Click to change` is displayed)
2. Press the new key combination (a modifier key is required)
3. Click the `Save` button to confirm
4. Click the `Reset` button to restore the default

After saving the setting, the hotkey display in the system tray menu is updated immediately as well.

### OCR

| Setting | Description |
|------|------|
| Save image | Attach the image to the memo during OCR capture (default: ON) |

- **ON**: Saves the captured image together with the OCR result text. The OCR Memo editor shows an image area with a cork board background.
- **OFF**: Saves text only.

### Maintenance

| Action | Description |
|------|------|
| **Export as Zip** | Back up the Workspace (notes, tickets, OCR memos, images) as a Zip file |
| **Restore from Zip** | Restore notes, tickets, and OCR memos from a Zip (existing data is replaced) |
| **Open log folder** | Open the app log folder in the file manager |
| **Export log Zip** | Export logs in Zip format |
| **Open license folder** | Open the folder containing bundled license files |

> ⚠️ **The restore operation completely replaces existing notes and tickets.** Always take a backup before running it.

---

## Search Syntax Reference

The full-text search bar on the Home screen supports the following special syntax.

| Syntax | Description | Example |
|------|------|----|
| Plain keyword | AND search separated by spaces | `memo meeting` |
| `"phrase"` | Phrase search (search multiple words as one unit) | `"today's work"` |
| `has:url` | Search notes/tickets containing a URL | `has:url` |
| `code:any` | Search items containing a code block | `code:any` |
| `code:<language>` | Search items containing a code block in the specified language | `code:powershell` |

**Example:**
```
has:url code:powershell memo
```
→ Items that contain a URL, include a PowerShell code block, and contain the keyword `memo`

Typing `::` quickly opens the pinned snippet modal instead of normal search results.

---

## Keyboard Shortcuts

### Global Hotkeys (WPF Level, Customizable)

You can change them in Settings → Shortcut Keys.

| Shortcut (Default) | Action |
|------------------------------|------|
| `Ctrl+Shift+F9` | Show / Hide the main window |
| `Ctrl+Shift+F10` | Toggle Spotlight on/off |
| `Ctrl+Shift+F11` | Open the Snippet Manager dialog |
| `Ctrl+Shift+F12` | Start OCR capture |

### In-App Global

| Shortcut | Action |
|----------------|------|
| `Ctrl+K` | Focus the Home search bar |
| `Ctrl+I` | Open the Snippet Manager dialog |
| `::` | Open the pinned snippet modal |
| `Ctrl+Shift+T` | Apply today's date filter |
| `Ctrl+Mouse Wheel` | Zoom in / Zoom out |
| `Ctrl+0` | Reset zoom to 100% |

### Notes Screen

| Shortcut | Action |
|----------------|------|
| `Ctrl+Enter` / `Ctrl+S` | Save |
| `Ctrl+1` | Jump to the Cue pane |
| `Ctrl+2` | Jump to the Note pane |
| `Ctrl+3` | Jump to the Summary pane |
| `Ctrl+E` | Switch to the Edit tab |
| `Ctrl+P` | Switch to the Preview tab |
| `/` | Focus the search bar |
| `Ctrl+F` | Open the in-editor search panel |

### Tickets Screen

| Shortcut | Action |
|----------------|------|
| `Ctrl+Enter` | Save |
| `/` | Focus the search bar |
| `Ctrl+F` | Open the in-editor search panel |

### Focus Screen

| Shortcut | Action |
|----------------|------|
| `Enter` | Open the selected item |
| `ESC` | Close the fullscreen viewer |

### Home Screen (List Operations)

| Shortcut | Action |
|----------------|------|
| `Enter` | Go to the selected item |
| `Ctrl+Click` | Go to the selected item |

---

## FAQ

### Q. How is the Focus score calculated?
**A.** It is calculated from the following factors.
- **Edit count (edit30d)**: Number of saves in the last 30 days (consecutive auto-saves are rounded and counted as once per minute)
- **Incoming links**: Number of times linked from other notes

You can turn it on/off in Settings → Focus → **Use edit count for ranking**.

---

### Q. Can I add any number of memos to a ticket?
**A.** There is no limit. You can add them with the `+ Add Memo` button. Delete memos you no longer need with the trash icon, or hide them with the 👁 icon if you only want to hide them temporarily.

---

### Q. How do I delete a TODO item?
**A.** A TODO is a line in a note in the `- [ ] text` format. Delete the target line while editing the note, or mark it complete like `- [x] text`. The TODO list on the Home screen updates automatically.

---

### Q. I want to add or change ticket statuses
**A.** Go to Settings → Tickets → **Columns**, enter the status names separated by commas, and save.  
Example: `backlog, doing, done, blocked, archived`

---

### Q. Can I sync across multiple devices?
**A.** You can access the data by setting WorkspaceRoot to a shared folder (NAS or a cloud-synced folder), but **simultaneous editing is not recommended because it may cause data conflicts**.

---

### Q. Can child notes have their own child notes?
**A.** Child note nesting is limited to one level. If you press `+ Child Note` while a child note is selected, it is created as a sibling note with the same parent instead (grandchild notes are not created).

---

### Q. Which languages can OCR recognize?
**A.** Japanese, English, Chinese, Korean, French, and German are supported. It can also recognize text when multiple languages are mixed on the screen, but accuracy varies depending on the language and character size.

---

### Q. I do not want to save OCR capture images
**A.** Turn OFF Settings → OCR → **Save image** to save text only. This does not affect images already attached to existing memos.

---

### Q. I want to change the global hotkeys
**A.** You can change each of the four hotkeys in Settings → Shortcut Keys. Click an input field, press the new key combination, and then click `Save`.

---

### Q. Can I use auto-save and pinning at the same time?
**A.** Yes. Auto-save periodically saves note content and metadata, while the pinned state is saved by a separate mechanism.

---

## Troubleshooting

### The app won't start
1. Check whether **WebView2 Runtime** is installed
2. Check whether the host side (backend process) starts normally
3. Go to Settings → Maintenance → **Open log folder** and review the error logs

### Data won't load / An error is displayed

| Error | Solution |
|--------|------|
| `E_WS_NOT_WRITABLE` | Check write permissions for the Workspace folder |
| `E_WS_INVALID_ROOT` | Check and correct the path in Settings → Workspace |
| `E_APP_NOT_READY` | Wait until startup completes and try again |
| `E_WEBVIEW2_UNAVAILABLE` | Install WebView2 Runtime |
| `E_SETTINGS_CORRUPT` | Settings are initialized automatically. Configure them again |

File read/write errors and native dialog messages are displayed in the configured display language.

### Auto-save is not working
1. Check whether Settings → Notes/Tickets → **Auto-save** is enabled
2. Check whether autoSaveMs is within the `200–10,000` range
3. Check whether note/ticket content has actually changed (nothing is saved if there is no change)

### Search returns no results
1. Check the spelling of the search term
2. Check whether a tag filter or date filter is applied (clear it with `×` on the filter chip)
3. Switch the filter to **All** and search again

### The Peek preview is not showing
- Click the item with a **single click**, not a double click
- If the window is narrow, widen it so the right pane can be shown

### OCR is not working
1. OCR engine initialization may take a few seconds. Wait a little and try again
2. Restart the app and try again
3. Go to Settings → Maintenance → **Open log folder** and check the error logs
