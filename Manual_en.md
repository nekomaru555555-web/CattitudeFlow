# CattitudeFlow User Manual

## Table of Contents

1. [Overview](#overview)
2. [Screen Layout](#screen-layout)
3. [Home Screen](#home-screen)
4. [Notes Screen](#notes-screen)
5. [Tickets Screen](#tickets-screen)
6. [Focus Screen](#focus-screen)
7. [Settings Screen](#settings-screen)
8. [Search Syntax Reference](#search-syntax-reference)
9. [Keyboard Shortcuts](#keyboard-shortcuts)
10. [FAQ](#faq)
11. [Troubleshooting](#troubleshooting)

---

## Overview

**CattitudeFlow** is a desktop application that combines Cornell-style note-taking with ticket (task) management.

Notes are written in Markdown format and structured in three panes — **Cue / Note / Summary** — following the Cornell method.  
Tickets support Cornell-style **Memos**, allowing you to attach multiple structured notes to any task.

---

## Screen Layout

### Header Navigation

The navigation buttons at the top of the app are as follows.

| Button | Description |
|--------|-------------|
| Home | Unified list and search for notes, tickets, and TODOs |
| Notes | Create and edit Cornell-style notes |
| Tickets | Manage tasks and tickets |
| Focus | View notes/tickets ranked by importance score |
| Settings | App configuration |

### InfoPill

Displayed on the right side of the header.

- **Days remaining**: Remaining days in the trial period (e.g., 7 days left)
- **Free space**: Disk space status (OK / Low)

### Window Controls

Displayed at the far right of the header when running as a native app.

| Button | Action |
|--------|--------|
| `_` | Minimize |
| `□` | Maximize / Restore |
| `×` | Close |

### Title Bar Quick Buttons

| Button | Action |
|--------|--------|
| `✂` | Open the Snippet Manager dialog (`Ctrl+I`) |
| `☀` | Toggle Spotlight Cursor on/off (`Alt+P`) |
| `☀ ▾` | Switch the active spotlight preset |

The snippet button shows a badge with the number of saved snippets. The spotlight icon color follows the currently selected preset.


---

## Home Screen

The Home screen has a 3-column layout: left menu, center list, and right Peek preview.

### Left Panel (Menu)

**Filter List**

| Item | Description |
|------|-------------|
| Notes | Show notes only |
| Tickets | Show tickets only |
| TODO | Show TODO items from all notes |
| Images | Show a list of attached images |
| All | Show notes + tickets + TODOs together |

Each item shows a count. When a tag is selected, the count is displayed as `tag count / total count`.

**Tag Filter**

Tags from notes and tickets are merged and displayed as chips.  
Click a tag to filter to items with that tag. Click **All** to clear the filter.

### Center Panel (List)

**Search Bar**

- Placeholder: `Full-text search (Ctrl+K) e.g. has:url code:powershell foo`
- `Ctrl+K` to focus
- `Clear` button to reset the search term
- Typing `::` quickly opens the pinned snippet modal

**Filter Chips**

Filter chips are shown below the search bar (All / Notes / Tickets / TODO).  
When TODO is selected, a **Scope** chip also appears (All / Today).  
When a date filter is active, a `date: YYYY-MM-DD ×` chip is shown and can be clicked to dismiss.

**List Operations**

| Action | Behavior |
|--------|----------|
| Single click | Show Peek preview in the right pane |
| Double click | Navigate to the corresponding Notes/Tickets screen |
| `Ctrl+Click` | Navigate to the corresponding screen |
| `Enter` | Navigate to the corresponding screen |

**Ticket Memo Rows**

When a ticket has memos attached, each memo is displayed as a child row beneath the ticket row.
Tickets that have memos show a `▼ / ▶` toggle so you can expand or collapse the memo tree.

| Action | Behavior |
|--------|----------|
| Single click | Open the ticket screen with the memo selected |
| `⛶` (fullscreen button) | Open the memo in fullscreen preview without the list panel |

**Image Tab**

- Shows thumbnail, path, creation date, size, and number of references for each image
- A dedicated search bar (search by uid / relPath) is shown
- Scroll to the bottom of the list to load more

### Right Panel (Peek Preview)

Single-clicking an item shows a preview in the right pane.

- Notes: Cornell-style preview (Cue / Note / Summary)
- Tickets: Ticket info preview
- Images: Image preview with a list of referencing notes/tickets
- Ticket Memos: Cornell-style memo preview (without list panel)
- **Fullscreen button** (⛶): Open the preview in fullscreen
- **Zoom toggle**: Switch Cornell preview size (compact / readable)
- Files changed in an external editor are detected automatically and refresh the list and preview

### Home Screen Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl+K` | Focus the search bar |
| `Ctrl+Shift+T` | Apply today's date filter and show the current month calendar |

---

## Notes Screen

### Layout

The Notes screen has a 2-column layout: **left list** and **right editor**.

### Left Panel (Note List)

**Creating a Note**

- Open the new note dialog from the `New` button or `+`
- Enter a title and date (default: today) to create
- If a note with the same title already exists, that note will be opened

**Creating a Child Note**

- Click the `+ Child Note` button while a note is selected to create a child of that note
- Child notes are displayed as indented rows in the list
- If the currently open note is already a child, a sibling note (same parent) is created instead (grandchildren are not allowed)

**Search**

- Press `/` to focus the search bar
- Full-text search of note content via the host

**Tag Filter**

Click a tag chip to filter notes by that tag.

**Pin**

- Click the ★ icon on a note row to toggle pinning
- Pinned notes appear at the top of the list
- The list is divided into `Pinned` and `All` sections
- Pin state is persisted to the Workspace (up to 100 entries)

### Right Panel (Editor)

**Metadata Fields**

| Field | Description |
|-------|-------------|
| Title | Note title (required) |
| Date | YYYY-MM-DD format (e.g., 2026-04-26) |
| Tags | Comma-separated (e.g., ops, daily) |

**Cornell Editor**

The note body is divided into three panes.

| Pane | Purpose |
|------|---------|
| **Cue** | Questions, keywords, hints |
| **Note** | Main content, detailed notes |
| **Summary** | Conclusion, takeaways |

**Pane Display Mode**

Use the pane mode toggle to switch how many panes are shown.

| Mode | Display |
|------|---------|
| `1` | Single pane (only the active pane) |
| `2` | Two panes |
| `3` | Three panes (all panes visible simultaneously) ※ Default |

The selected pane mode is applied immediately and restored when you reopen the note. In 3-pane mode, the Summary pane remains visible.

**Tabs**

| Tab | Description |
|-----|-------------|
| Edit | CodeMirror editor |
| Preview | Markdown preview (with table of contents) |

- Press `Ctrl+F` while the editor is focused to open the localized search panel
- Use the PDF button on the Preview tab to export with the current background styling

**Markdown Toolbar**

Use the toolbar above the edit area to insert formatting.

| Button | Format |
|--------|--------|
| Bold | `**text**` |
| Italic | `*text*` |
| Strikethrough | `~~text~~` |
| Underline | `<u>text</u>` |
| Text color | `<span style="color:#XXXXXX">text</span>` (20 colors) |
| Bullet list | `- text` |
| Numbered list | `1. text` |
| TODO list | `- [ ] text` |
| Table | Insert table template |
| Alert box | GFM alerts (NOTE / TIP / IMPORTANT / WARNING / CAUTION) |
| Heading | H1 / H2 / H3 |

**Color Palette (20 colors)**

Red / Crimson / Orange / Amber / Yellow / Lime / Green / Teal / Cyan / Sky /  
Blue / Indigo / Purple / Violet / Pink / Rose / Brown / Slate / Gray / Black

**Pasting Images**

Paste a clipboard image into the editor and it will be automatically saved to the Workspace and inserted as Markdown image syntax.  
An "Importing image…" overlay is shown while processing.

**Save Status**

Displayed in the top-right corner.

| State | Display |
|-------|---------|
| Saved | `Saved` |
| Unsaved | `Unsaved` |
| Saving | `Saving…` |

- Editor and preview content fonts can be changed at Settings → Editor
- Note files changed outside the app are detected and reloaded automatically

**Deletion**

Click the trash icon to delete a note. A warning is shown if the note is pinned or has unsaved changes.  
If child notes exist, a confirmation dialog asks whether to delete them as well.

### Notes Screen Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl+Enter` or `Ctrl+S` | Save |
| `Ctrl+1` | Jump to the Cue pane |
| `Ctrl+2` | Jump to the Note pane |
| `Ctrl+3` | Jump to the Summary pane |
| `Ctrl+E` | Switch to Edit tab |
| `Ctrl+P` | Switch to Preview tab |
| `/` | Focus the note search bar |

---

## Tickets Screen

Tickets are for managing tasks and to-dos. They support a Cornell-style body, status management, comments, and memos.

### Left Panel (Ticket List)

**Search and Filtering**

| Action | Description |
|--------|-------------|
| `/` key | Focus the search bar |
| Priority filter | All / P0 / P1 / P2 / P3 |
| Sort | By updated date / due date / priority |

**Creating a Ticket**

- Click the `New` button to show the title input form
- Type a title and press `Enter` to create

**Memo List**

When a ticket is selected, its associated memos are displayed as a list below the ticket.

| Action | Description |
|--------|-------------|
| Click a memo row | Open that memo in the right panel |
| `👁` icon | Hide / show the memo in the list (data is retained) |
| `🗑` icon | Delete the memo (confirmation dialog shown) |

### Right Panel (Ticket Editor)

Selecting a ticket opens the editor in the right panel.

**Metadata Fields**

| Field | Description |
|-------|-------------|
| Title | Ticket title (required) |
| Status | Custom column (configurable in Settings, e.g., backlog / doing / done) |
| Due date | YYYY-MM-DD format |
| Priority | P0 (highest) / P1 / P2 / P3 (lowest) |
| Labels | Comma-separated (e.g., urgent, ops) |

**Tabs**

| Tab | Description |
|-----|-------------|
| Edit | Cornell-style editor (Cue / Note / Summary) |
| Preview | Markdown preview (Cornell 3-pane layout) |
| Comments (n) | Add and view comments |
| Memo | View and edit memos for the selected ticket |

**Deletion**

Click the trash icon to delete a ticket (confirmation dialog shown).  
If the ticket has memos, the dialog includes a memo count in the confirmation message.

### Memo Feature

Tickets can have multiple Cornell-style **Memos** attached. The tab label is **Memo**, and child documents that were previously treated as “docs” are managed under the same name. This makes it easy to keep meeting notes, research notes, and supporting material separate from the main ticket body.

**Adding a Memo**

- Click the `+ Add Memo` button in the `Memo` tab or at the bottom of the left panel to create a memo immediately
- New memos use `Memo` as the default title

**Memo Editor**

The memo editor uses the same Cornell layout as notes, with 1 / 2 / 3 pane display modes. Save, delete, fullscreen, and layout behavior now match the note experience.

| Tab | Description |
|-----|-------------|
| Edit | Cornell-style editor (Cue / Note / Summary) |
| Preview | Markdown preview (Cornell 1 / 2 / 3-pane layout) |

- Auto-save begins as soon as the title is created
- Pane mode changes are applied immediately and restored the next time you open the memo
- The Preview tab includes PDF export
- Memo files changed in an external editor are reloaded automatically

**Memo Operations**

| Action | Description |
|--------|-------------|
| Click a memo row | Open the memo editor |
| `👁` icon | Hide / show the memo in the list (data is retained) |
| `🗑` icon | Delete the memo (confirmation dialog shown) |
| `⛶` (fullscreen) | Open the memo in a fullscreen Peek view without the list panel |

> Memos belong to their parent ticket. Deleting a ticket also deletes all its memos.

### Tickets Screen Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl+Enter` | Save |
| `/` | Focus the ticket search bar |

---

## Focus Screen

The Focus screen displays your most important notes and tickets ranked by score, for focused review and reading.

### Display Mode

| Mode | Description |
|------|-------------|
| Notes | Notes ranked by score |
| Tickets | Tickets ranked by score |

### Scoring

Note scores are calculated from the following factors.

- **Edit count** (last 30 days): Can be toggled on/off in Settings
- **Incoming links**: Number of times referenced from other notes

### Layout

| Area | Content |
|------|---------|
| Left list | Rank, title, reference count, updated date |
| Right preview | Cornell-style preview of the selected note |
| `Max` | Maximum number of items shown (5–200) |

### Operations

| Action | Behavior |
|--------|----------|
| Click | Select an item and show its preview |
| Double-click / `Enter` | Open in the Notes/Tickets screen |
| `Fullscreen` button | Open the fullscreen viewer |

### Fullscreen Viewer

- Switch items using the left list
- Search by title with the search bar
- Click `Open` to navigate to the corresponding screen
- Press `ESC` or click `Close` to exit

### Snippet Search and Pinned Modal

- When the search bar is empty, the page stays in Focus mode and shows notes and tickets ranked by edit activity
- When you enter a keyword, the page switches to Snippet mode and highlights matching Cornell panes
- Typing `::` quickly opens the pinned snippet modal so you can copy pinned blocks
- Use the title-bar `✂` button or `Ctrl+I` to open the Snippet Manager at any time

### Focus Screen Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Enter` | Open the selected item |
| `ESC` | Close the fullscreen viewer |

---

## Settings Screen

Access settings from the **Settings** button in the header. Select a category from the left sidebar.

### General

| Setting | Description |
|---------|-------------|
| Language | UI display language (system / ja / en / zh / ko / fr / de) |
| Locale | Locale for number and date formatting (leave blank to use OS setting, e.g., en-US) |
| Theme preset | Color theme |

- `Preview`: Preview the selected theme immediately
- `Save theme`: Save the theme to the host
- `Save language/locale`: Save language settings
- The saved language is also used for native and built-in UI such as file dialogs, startup errors, and the `Ctrl+F` search panel

### Workspace

| Setting | Description |
|---------|-------------|
| WorkspaceRoot | Path where notes and tickets are stored |

- `Reload`: Re-fetch current Workspace settings
- `Save`: Save the changed path

### Notes

| Setting | Description |
|---------|-------------|
| Auto-save | Whether to auto-save on input (ON/OFF) |
| Auto-save interval (ms) | Auto-save interval (200–10,000 ms, local UI setting) |

### Editor

| Setting | Description |
|---------|-------------|
| Font family | Font used for editor content and preview content |
| Font size (px) | Font size for body content |

- Changes are previewed immediately, even before saving
- `Reset to default` restores the default values

### Tickets

| Setting | Description |
|---------|-------------|
| Auto-save | Whether to auto-save on ticket edits (ON/OFF) |
| Auto-save interval (ms) | Auto-save interval (local UI setting) |
| Columns | Status options for tickets (comma-separated)<br>e.g., `backlog, doing, done, blocked, archived` |
| Show ticket ID | Display ticket IDs in lists/previews (local UI setting) |

### Focus

| Setting | Description |
|---------|-------------|
| Max items | Maximum number of items in the Focus list |
| Use edit count for ranking | Add note save count to the Focus score |
| Activity log | Enable edit count tracking (note content and search queries are not stored) |

> ※ Consecutive auto-saves are counted as once per minute to avoid inflating scores.

### Spotlight Cursor

| Setting | Description |
|---------|-------------|
| Presets 1–5 | Choose from five fixed spotlight presets |
| Name | Display name for each preset (up to 20 characters) |
| Size (px) | Spotlight circle diameter (20–200 px) |
| Color | Color used by the spotlight circle and header icon |
| Opacity | Transparency level of the spotlight |

- Use the title-bar `☀` button or `Alt+P` to toggle the spotlight on and off
- `Reset to default` restores the default color and size for the current preset

### Maintenance

| Action | Description |
|--------|-------------|
| **Export as Zip** | Back up the Workspace as a Zip file |
| **Restore from Zip** | Restore notes and tickets from a Zip (existing data will be replaced) |
| **Open log folder** | Open the app log folder in File Explorer |
| **Export log Zip** | Export logs as a Zip file |
| **Open license folder** | Open the folder containing bundled license files |

> ⚠️ **The restore operation completely replaces all existing notes and tickets.** Always back up your data before restoring.

---

## Search Syntax Reference

The Home screen search bar supports the following special syntax.

| Syntax | Description | Example |
|--------|-------------|---------|
| Plain keywords | AND search with spaces | `memo meeting` |
| `"phrase"` | Phrase search (multiple words as a single unit) | `"today's work"` |
| `has:url` | Find notes/tickets containing a URL | `has:url` |
| `code:any` | Find items containing a code block | `code:any` |
| `code:<language>` | Find items with a code block in the specified language | `code:powershell` |

**Example:**
```
has:url code:powershell memo
```
→ Items that contain a URL, a PowerShell code block, and the keyword "memo"

Note: typing `::` quickly opens the pinned snippet modal instead of running a normal search.

---

## Keyboard Shortcuts

### Global

| Shortcut | Action |
|----------|--------|
| `Ctrl+K` | Focus the Home search bar |
| `Ctrl+I` | Open the Snippet Manager dialog |
| `Alt+P` | Toggle Spotlight Cursor on/off |
| `::` | Open the pinned snippet modal |
| `Ctrl+Shift+T` | Apply today's date filter |
| `Ctrl+Mouse Wheel` | Zoom in / Zoom out |
| `Ctrl+0` | Reset zoom to 100% |

### Notes Screen

| Shortcut | Action |
|----------|--------|
| `Ctrl+Enter` / `Ctrl+S` | Save |
| `Ctrl+1` | Jump to the Cue pane |
| `Ctrl+2` | Jump to the Note pane |
| `Ctrl+3` | Jump to the Summary pane |
| `Ctrl+E` | Switch to Edit tab |
| `Ctrl+P` | Switch to Preview tab |
| `/` | Focus the note search bar |
| `Ctrl+F` | Open the in-editor search panel |

### Tickets Screen

| Shortcut | Action |
|----------|--------|
| `Ctrl+Enter` | Save |
| `/` | Focus the ticket search bar |
| `Ctrl+F` | Open the in-editor search panel |

### Focus Screen

| Shortcut | Action |
|----------|--------|
| `Enter` | Open the selected item |
| `ESC` | Close the fullscreen viewer |

### Home Screen

| Shortcut | Action |
|----------|--------|
| `Enter` | Navigate to the selected item |
| `Ctrl+Click` | Navigate to the selected item |

---

## FAQ

### Q. How is the Focus score calculated?
**A.** The score is calculated from the following factors:
- **Edit count (edit30d)**: Number of saves in the last 30 days (consecutive auto-saves count as once per minute)
- **Incoming links**: Number of times referenced from other notes

Toggle this on/off at Settings → Focus → **Use edit count for ranking**.

---

### Q. How many memos can I add to a ticket?
**A.** There is no limit. Click `+ Add Memo` to add as many as you need. Delete unwanted memos with the trash icon, or hide them temporarily with the 👁 icon.

---

### Q. How do I delete a TODO item?
**A.** TODOs are lines in the `- [ ] text` format inside a note. Delete the line while editing the note, or mark it as done with `- [x] text`. The TODO list on the Home screen updates automatically.

---

### Q. How do I add or change ticket statuses?
**A.** Go to Settings → Tickets → **Columns** and enter status names separated by commas, then save.  
Example: `backlog, doing, done, blocked, archived`

---

### Q. Can I sync across multiple devices?
**A.** You can point WorkspaceRoot to a shared folder (NAS or cloud-synced folder) to access your data, but **simultaneous editing is not recommended** as it may cause data conflicts.

---

### Q. Can a child note have its own child notes?
**A.** Nesting is limited to one level. If you click `+ Child Note` while a child note is selected, a sibling note (with the same parent) is created instead (grandchildren are not created).

---

### Q. Can I use auto-save and pinning at the same time?
**A.** Yes. Auto-save handles note content and metadata, while pinning state is managed separately.

---

## Troubleshooting

### The app won't start
1. Check that **WebView2 Runtime** is installed
2. Check that the host process (backend) started successfully
3. Go to Settings → Maintenance → **Open log folder** to review error logs

### Data won't load / An error is displayed

| Error | Solution |
|-------|---------|
| `E_WS_NOT_WRITABLE` | Check write permissions for the Workspace folder |
| `E_WS_INVALID_ROOT` | Check and correct the path in Settings → Workspace |
| `E_APP_NOT_READY` | Wait for the app to finish starting, then retry |
| `E_WEBVIEW2_UNAVAILABLE` | Install WebView2 Runtime |
| `E_SETTINGS_CORRUPT` | Settings will be reset automatically. Reconfigure your settings |

File read/write errors and native dialog messages are shown in the language selected in Settings.

### Auto-save is not working
1. Check that Settings → Notes/Tickets → **Auto-save** is enabled
2. Check that autoSaveMs is within `200–10,000`
3. Verify that the content has actually changed (no save occurs if nothing changed)

### Search returns no results
1. Check the spelling of your search term
2. Check whether a tag filter or date filter is active (click `×` on filter chips to clear)
3. Switch the filter to **All** and search again

### The Peek preview is not showing
- Click items with a **single click**, not a double click
- If the window is too narrow, widen it to reveal the right pane
