
# Tab Goblin — BSERC Week 2 Project 14

Chrome extension for organising tabs without closing them.

## Features
- Shows open-tab count, sleeping-tab count and Keep count.
- Goblin mood changes based on number of open tabs.
- Lists tabs oldest-last-accessed first.
- Puts inactive tabs to sleep using Chrome's built-in `chrome.tabs.discard`; the tab remains open and can be woken by clicking it.
- Keep list protects selected tabs from the Feed action.
- Saves named sessions locally and restores tabs after a Chrome restart.
- Saves data in `chrome.storage.local`; no server, account or network calls.

## Install
1. Extract the ZIP.
2. Open Chrome and visit `chrome://extensions` (Edge: `edge://extensions`).
3. Enable Developer mode.
4. Click Load unpacked.
5. Select the extracted `Tab_Goblin_Project14` folder containing `manifest.json`.
6. Click the extension icon.

## How to use
- Tabs are listed from least recently accessed to most recently accessed.
- Click ☆ to add a tab to Keep; ★ means protected.
- Click Zzz to discard an individual inactive tab.
- Feed the goblin to discard all safe inactive, unpinned, non-kept tabs in the current window.
- Save session to store the current window's tab URLs. Use Sessions → Restore after restarting Chrome to reopen them.

## Important limitations
- Chrome's discard API unloads a page but does not close its tab. Clicking the tab wakes it.
- The extension protects tabs explicitly added to Keep, pinned tabs and the active tab.
- Browsers do not expose a reliable universal way to detect every unsaved form field. If a tab contains a half-filled form or unsaved work, add it to Keep before feeding the goblin. The extension does not promise automatic form-state preservation.
- Session restoration reopens saved URLs; websites may require signing in again, and transient unsaved form contents are not saved.
- Chrome may refuse to discard some tabs, such as active or otherwise ineligible tabs.
