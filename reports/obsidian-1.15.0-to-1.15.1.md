# Shadow Log: Obsidian 1.15.0 → 1.15.1

> What the update actually changed, read from the shipped code of two public releases. Every item cites the file and line (in the js-beautify output) where it was found. Automated heuristics: "possible", not "confirmed".

| | old | new |
|---|---|---|
| version | 1.15.0 | 1.15.1 |
| released | 2026-11-02 | 2026-11-12 |
| artifact | https://github.com/obsidianmd/obsidian-releases/releases/download/v1.15.0/obsidian-1.15.0.asar.gz | https://github.com/obsidianmd/obsidian-releases/releases/download/v1.15.1/obsidian-1.15.1.asar.gz |
| files in bundle | 368 | 368 |

Official notes: https://github.com/obsidianmd/obsidian-releases/releases/tag/v1.15.1 · https://obsidian.md/changelog/

**Release-notes cross-check:** 7 of the 10 top findings checked were not found in the official notes for 1.15.0→1.15.1. The check is a plain-text match and can miss reworded announcements.

Generated 2026-11-12T23:35:30.889Z by shadow-log 0.1.0.

## At a glance

| category | added | removed | changed |
|---|---:|---:|---:|
| Telemetry, analytics & tracking | 0 | 0 |  |
| API endpoints (paths) | 0 | 0 |  |
| Contacted / referenced domains | 0 | 1 |  |
| Electron IPC channels & protocols | 6 | 0 |  |
| Feature-flag / experiment-like identifiers | 0 | 0 |  |
| Settings, config & storage keys | 2 | 3 |  |
| Commands | 0 | 0 |  |
| UI strings (localization) | 25 | 9 |  |
| Dependencies & bundled libraries | 0 | 1 | 1 |
| Full URLs | 0 | 1 |  |
| Files in bundle | 0 | 0 | 69 |

## Top findings

### 1. New UI string group `interface.startScreen.mobile` (13 strings)

*Score 98 · 13 new UI strings under one prefix · 13 not referenced by code yet · keywords: cloud*

Official notes: not found in the notes for 1.15.0→1.15.1 (searched for: "enabled", "Last opened", "This vault didn't finish opening last time", "On this device")

- `interface.startScreen.mobile.labelStoredInICloud` = "iCloud" *(no code reference found)*
- `interface.startScreen.mobile.labelEnabledPluginCount` = "{{count}} enabled" *(no code reference found)*
- `interface.startScreen.mobile.labelFiles` = "Files" *(no code reference found)*
- `interface.startScreen.mobile.labelLastOpened` = "Last opened" *(no code reference found)*
- `interface.startScreen.mobile.labelOpenIncomplete` = "This vault didn't finish opening last time." *(no code reference found)*
- `interface.startScreen.mobile.labelOpenIncompleteTryRestricted` = "This vault didn't finish opening last time. If it keeps happening, try restricted mode." *(no code reference found)*
- `interface.startScreen.mobile.labelPluginsDisabled` = "Disabled" *(no code reference found)*
- `interface.startScreen.mobile.labelSlowCommunityPlugins` = "Community plugins took {{seconds}} seconds to load last time. If this vault is slow to open, try restricted mode." *(no code reference found)*
- `interface.startScreen.mobile.labelStoredOnDevice` = "On this device" *(no code reference found)*
- `interface.startScreen.mobile.menuOptDeleteVault` = "Delete vault..." *(no code reference found)*
- …and 3 more (see UI strings section)

Evidence: `i18n.js` in the new build.

### 2. New IPC channel `popup-token` (renderer, sendSync)

*Score 60 · keywords: token*

Official notes: not found in the notes for 1.15.0→1.15.1 (searched for: "popup token")

Evidence:
- `main.js:5850` → `}), r.ipcMain.on("popup-token", i => {`
- `app.js:100709` → `return LN || (LN = electron.ipcRenderer.sendSync("popup-token")), window.open("about:blank", "_blank", ["token=" + LN, ...o].join(","))`

### 3. New UI string group `main` (6 strings)

*Score 49 · 6 new UI strings under one prefix*

Official notes: mentioned (matched "main" in the 1.15.1 (public) notes)

- `main.buttonManageVaults` = "Manage vaults"
- `main.unknownFileMessage` = "This file will open outside of Obsidian. Some file types can run code on your computer. Only proceed if you trust the so"
- `main.unknownFileTitle` = "Open file in another app?"
- `main.vaultInInstallFolderDetail` = "The installer erases this folder when Obsidian updates, and this vault with it. Choose "Manage vaults" to close the vaul"
- `main.vaultInInstallFolderMessage` = "Vaults can't be stored in Obsidian's installation folder because it's erased when Obsidian updates"
- `main.vaultInInstallFolderTitle` = "This vault is inside Obsidian's installation folder"

Evidence: `i18n.js` in the new build.

### 4. New IPC channel `open-with-default-app` (main, on)

*Score 45 · Electron IPC channels & protocols*

Official notes: not found in the notes for 1.15.0→1.15.1 (searched for: "open with default app")

Evidence:
- `main.js:6018` → `}), r.ipcMain.on("open-with-default-app", (i, s) => {`

### 5. New IPC channel `startup` (main, on)

*Score 45 · Electron IPC channels & protocols*

Official notes: mentioned (matched "startup" in the 1.15.1 (public) notes)

Evidence:
- `main.js:5881` → `}), r.ipcMain.on("startup", i => {`

### 6. New IPC channel `startup-appearance` (renderer, send)

*Score 45 · Electron IPC channels & protocols*

Official notes: not found in the notes for 1.15.0→1.15.1 (searched for: "startup appearance")

Evidence:
- `main.js:5509` → `return r.ipcMain.on("startup-appearance", Y), y.on("closed", () => r.ipcMain.off("startup-appearance", Y)), P.on("did-create-window", _ => {`
- `app.js:142026` → `window.electron.ipcRenderer.send("startup-appearance", {`

### 7. New IPC channel `startup-snapshot` (main, handle)

*Score 45 · Electron IPC channels & protocols*

Official notes: not found in the notes for 1.15.0→1.15.1 (searched for: "startup snapshot")

Evidence:
- `main.js:5890` → `r.ipcMain.handle("startup-snapshot", async (i, s, d) => {`

### 8. New IPC channel `startup-snapshot-save` (renderer, send)

*Score 45 · Electron IPC channels & protocols*

Official notes: not found in the notes for 1.15.0→1.15.1 (searched for: "startup snapshot save")

Evidence:
- `main.js:5898` → `}), r.ipcMain.on("startup-snapshot-save", (i, s, d) => {`
- `app.js:142098` → `delete n.active, window.electron.ipcRenderer.send("startup-snapshot-save", {`

### 9. Removed UI string group `interface.startScreen.mobile` (4 strings)

*Score 45 · 4 UI strings under one prefix were removed*

Official notes: not found in the notes for 1.15.0→1.15.1 (searched for: "Delete vault", "Forget vault", "Move to device storage", "Rename vault")

- `interface.startScreen.mobile.buttonDeleteVault` = "Delete vault"
- `interface.startScreen.mobile.buttonForgetVault` = "Forget vault"
- `interface.startScreen.mobile.buttonMoveToDeviceStorage` = "Move to device storage"
- `interface.startScreen.mobile.buttonRenameVault` = "Rename vault"

Evidence: `i18n.js` in the old build.

### 10. New UI string group `nouns` (3 strings)

*Score 37 · 3 new UI strings under one prefix*

Official notes: mentioned (matched "item" in the 1.15.1 (public) notes)

- `nouns.itemWithCount` = "{{count}} item"
- `nouns.itemWithCount_plural` = "{{count}} items"
- `nouns.quotes` = "“{{item}}”"

Evidence: `i18n.js` in the new build.

## New UI string groups

Strings are grouped by key prefix. Groups whose strings no first-party code references yet are candidates for unreleased features.

| group | new strings | unreferenced | sample |
|---|---:|---:|---|
| `interface.startScreen.mobile` | 13 | 13 | "iCloud" |
| `main` | 6 | 0 | "Manage vaults" |
| `nouns` | 3 | 0 | "{{count}} item" |
| `dialogue` | 1 | 0 | "Failed to move {{item}} to the system trash. To delete anyway, change the “Delet" |
| `interface.startUp` | 1 | 0 | "Unable to read “{{path}}”, so its files aren’t shown. Check its permissions, the" |
| `plugins.search` | 1 | 0 | "Relevance" |

## Details by category

### Contacted / referenced domains

<details><summary>Removed (1)</summary>

| score | removed | evidence |
|---:|---|---|
| 31 | `git.io` | `worker.js:2644` → `…ail(new Error("Incorrectly eaten value: please report this warning on https://git.io/vg5Ft"), k())` |

</details>

### Electron IPC channels & protocols

<details open><summary>Added (6)</summary>

| score | added | evidence |
|---:|---|---|
| 60 | `popup-token` | `main.js:5850` → `}), r.ipcMain.on("popup-token", i => {` |
| 45 | `open-with-default-app` | `main.js:6018` → `}), r.ipcMain.on("open-with-default-app", (i, s) => {` |
| 45 | `startup` | `main.js:5881` → `}), r.ipcMain.on("startup", i => {` |
| 45 | `startup-appearance` | `main.js:5509` → `return r.ipcMain.on("startup-appearance", Y), y.on("closed", () => r.ipcMain.off("startup-appearance", Y)), P.on("did-create-window", _ => {` |
| 45 | `startup-snapshot` | `main.js:5890` → `r.ipcMain.handle("startup-snapshot", async (i, s, d) => {` |
| 45 | `startup-snapshot-save` | `main.js:5898` → `}), r.ipcMain.on("startup-snapshot-save", (i, s, d) => {` |

</details>

### Settings, config & storage keys

<details open><summary>Added (2)</summary>

| score | added | evidence |
|---:|---|---|
| 30 | `disable-background-timer-throttling` | `main.js:4633` → `…tch("enable-features", A.join(",")), r.app.commandLine.appendSwitch("disable-background-timer-throttling"), process.removeAllListeners("uncaughtException"), pro…` |
| 30 | `language` | `index.html:148` → `…', localStorage.getItem(startup.id + '-config') \|\| '.obsidian', localStorage.getItem('language') \|\| navigator.language).then(showSnapshot, function (e) {` |

</details>

<details><summary>Removed (3)</summary>

| score | removed | evidence |
|---:|---|---|
| 21 | `enable-plugin-` | `app.js:113524` → `if (localStorage.setItem("enable-plugin-" + this.app.appId, e ? "true" : "false"), e)` |
| 21 | `slidingSidebar` | `app.js:63901` → `}), S.isPhone && this.app.vault.getConfig("slidingSidebar") ? (ae(r, new oe({` |
| 21 | `uriCallbacks` | `app.js:110796` → `if (!e.vault.getConfig("uriCallbacks")) return;` |

</details>

### UI strings (localization)

<details open><summary>Added (25)</summary>

| score | added | evidence |
|---:|---|---|
| 55 | `interface.startScreen.mobile.labelStoredInICloud` | "iCloud" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.labelEnabledPluginCount` | "{{count}} enabled" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.labelFiles` | "Files" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.labelLastOpened` | "Last opened" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.labelOpenIncomplete` | "This vault didn't finish opening last time." **(unreferenced)** |
| 40 | `interface.startScreen.mobile.labelOpenIncompleteTryRestricted` | "This vault didn't finish opening last time. If it keeps happening, try restricted mode." **(unreferenced)** |
| 40 | `interface.startScreen.mobile.labelPluginsDisabled` | "Disabled" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.labelSlowCommunityPlugins` | "Community plugins took {{seconds}} seconds to load last time. If this vault is slow to ope" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.labelStoredOnDevice` | "On this device" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.menuOptDeleteVault` | "Delete vault..." **(unreferenced)** |
| 40 | `interface.startScreen.mobile.menuOptForgetVault` | "Forget vault..." **(unreferenced)** |
| 40 | `interface.startScreen.mobile.menuOptMoveToDeviceStorage` | "Move to device storage..." **(unreferenced)** |
| 40 | `interface.startScreen.mobile.menuOptRenameVault` | "Rename vault..." **(unreferenced)** |
| 15 | `dialogue.msgFailedToMoveToSystemTrash` | "Failed to move {{item}} to the system trash. To delete anyway, change the “Deleted files” " |
| 15 | `interface.startUp.msgUnreadablePath` | "Unable to read “{{path}}”, so its files aren’t shown. Check its permissions, then restart " |
| 15 | `main.buttonManageVaults` | "Manage vaults" |
| 15 | `main.unknownFileMessage` | "This file will open outside of Obsidian. Some file types can run code on your computer. On" |
| 15 | `main.unknownFileTitle` | "Open file in another app?" |
| 15 | `main.vaultInInstallFolderDetail` | "The installer erases this folder when Obsidian updates, and this vault with it. Choose "Ma" |
| 15 | `main.vaultInInstallFolderMessage` | "Vaults can't be stored in Obsidian's installation folder because it's erased when Obsidian" |
| 15 | `main.vaultInInstallFolderTitle` | "This vault is inside Obsidian's installation folder" |
| 15 | `nouns.itemWithCount` | "{{count}} item" |
| 15 | `nouns.itemWithCount_plural` | "{{count}} items" |
| 15 | `nouns.quotes` | "“{{item}}”" |
| 15 | `plugins.search.labelSortRelevance` | "Relevance" |

</details>

<details><summary>Removed (9)</summary>

| score | removed | evidence |
|---:|---|---|
| 11 | `editor.linkSuggestion.labelTypeBlock` | "^" |
| 11 | `editor.linkSuggestion.labelTypeHash` | "#" |
| 11 | `editor.linkSuggestion.labelTypePipe` | "\|" |
| 11 | `interface.startScreen.mobile.buttonDeleteVault` | "Delete vault" |
| 11 | `interface.startScreen.mobile.buttonForgetVault` | "Forget vault" |
| 11 | `interface.startScreen.mobile.buttonMoveToDeviceStorage` | "Move to device storage" |
| 11 | `interface.startScreen.mobile.buttonRenameVault` | "Rename vault" |
| 11 | `setting.appearance.optionSlidingSidebar` | "Sliding sidebars" |
| 11 | `setting.appearance.optionSlidingSidebarDesc` | "Sidebars slide to the side of the content instead of floating above." |

</details>

### Dependencies & bundled libraries

<details><summary>Removed (1)</summary>

| score | removed | evidence |
|---:|---|---|
| 21 | `bundled:lib/reveal/reveal.js (reveal.js)` | `lib/reveal/reveal.js` → `bundled:lib/reveal/reveal.js (reveal.js) 4.3.1` |

</details>

<details><summary>Changed (1)</summary>

| score | changed | evidence |
|---:|---|---|
| 24 | `bundled:lib/pele.min.js (Pele)` 1.8.0 → 1.13.0 | `lib/pele.min.js` → `bundled:lib/pele.min.js (Pele) 1.13.0` |

</details>

### Full URLs

<details><summary>Removed (1)</summary>

| score | removed | evidence |
|---:|---|---|
| 14 | `https://git.io/vg5Ft` | `worker.js:2644` → `…ail(new Error("Incorrectly eaten value: please report this warning on https://git.io/vg5Ft"), k())` |

</details>

## File changes

<details><summary>Changed (69)</summary>

| file | before | after | Δ bytes |
|---|---:|---:|---:|
| `worker.js` | 244.6 KB | 193.2 KB | -52607 |
| `quicklook.js` | 659.4 KB | 620.1 KB | -40271 |
| `lib/pele.min.js` | 683.3 KB | 716.5 KB | +34000 |
| `lib/reveal/reveal.js` | 87.6 KB | 116.1 KB | +29222 |
| `starter.js` | 428.6 KB | 444.2 KB | +15984 |
| `help.js` | 380.4 KB | 392.0 KB | +11857 |
| `main.js` | 207.1 KB | 215.0 KB | +8142 |
| `lib/reveal/reveal.css` | 45.6 KB | 52.7 KB | +7238 |
| `app.js` | 3.2 MB | 3.2 MB | -6616 |
| `i18n/ta.txt` | 209.6 KB | 215.7 KB | +6159 |
| `index.html` | 1.3 KB | 7.2 KB | +6039 |
| `i18n/sa.txt` | 210.6 KB | 215.9 KB | +5343 |
| `i18n/ne.txt` | 204.3 KB | 209.3 KB | +5060 |
| `i18n/el.txt` | 156.1 KB | 161.0 KB | +4952 |
| `i18n/km.txt` | 199.6 KB | 204.4 KB | +4942 |
| `i18n/ka.txt` | 201.2 KB | 206.0 KB | +4923 |
| `i18n/th.txt` | 176.6 KB | 181.4 KB | +4886 |
| `i18n/bn.txt` | 188.0 KB | 192.5 KB | +4650 |
| `i18n/si.txt` | 195.6 KB | 200.0 KB | +4541 |
| `i18n/bg.txt` | 152.9 KB | 157.0 KB | +4181 |
| `i18n/uk.txt` | 140.4 KB | 144.0 KB | +3761 |
| `i18n/ru.txt` | 146.7 KB | 150.4 KB | +3722 |
| `i18n/be.txt` | 141.7 KB | 145.3 KB | +3694 |
| `i18n/sr.txt` | 137.3 KB | 140.6 KB | +3430 |
| `i18n/fa.txt` | 129.2 KB | 132.4 KB | +3327 |
| `i18n/am.txt` | 124.6 KB | 127.8 KB | +3269 |
| `i18n/ja.txt` | 110.4 KB | 113.3 KB | +2960 |
| `i18n/he.txt` | 102.6 KB | 105.4 KB | +2858 |
| `i18n/ar.txt` | 116.0 KB | 118.8 KB | +2796 |
| `i18n/de.txt` | 88.2 KB | 90.8 KB | +2693 |
| `i18n/ko.txt` | 93.8 KB | 96.3 KB | +2528 |
| `i18n/fr.txt` | 92.8 KB | 95.2 KB | +2495 |
| `i18n/ca.txt` | 87.8 KB | 90.2 KB | +2467 |
| `i18n/sk.txt` | 87.1 KB | 89.5 KB | +2450 |
| `i18n/hu.txt` | 94.0 KB | 96.4 KB | +2395 |
| `i18n/it.txt` | 82.9 KB | 85.2 KB | +2378 |
| `i18n/kab.txt` | 82.8 KB | 85.2 KB | +2378 |
| `i18n/vi.txt` | 101.1 KB | 103.4 KB | +2373 |
| `i18n/lv.txt` | 84.5 KB | 86.8 KB | +2368 |
| `i18n/nl.txt` | 81.7 KB | 84.0 KB | +2349 |
| `i18n/fi.txt` | 80.4 KB | 82.7 KB | +2338 |
| `i18n/pl.txt` | 83.9 KB | 86.1 KB | +2287 |
| `i18n/ga.txt` | 87.6 KB | 89.8 KB | +2270 |
| `i18n/ro.txt` | 90.9 KB | 93.1 KB | +2269 |
| `i18n/cs.txt` | 84.8 KB | 87.0 KB | +2254 |
| `i18n/es.txt` | 86.4 KB | 88.6 KB | +2252 |
| `i18n/pt.txt` | 84.0 KB | 86.2 KB | +2244 |
| `i18n/sq.txt` | 89.7 KB | 91.8 KB | +2243 |
| `i18n/uz.txt` | 86.4 KB | 88.6 KB | +2230 |
| `i18n/gl.txt` | 85.1 KB | 87.3 KB | +2206 |
| `i18n/pt-BR.txt` | 83.6 KB | 85.7 KB | +2184 |
| `i18n/ms.txt` | 78.5 KB | 80.6 KB | +2177 |
| `i18n/id.txt` | 76.8 KB | 78.9 KB | +2118 |
| `i18n/zh-TW.txt` | 68.2 KB | 70.2 KB | +2107 |
| `i18n/tr.txt` | 84.4 KB | 86.4 KB | +2090 |
| `i18n/no.txt` | 74.7 KB | 76.7 KB | +2086 |
| `i18n/sv.txt` | 78.3 KB | 80.3 KB | +2021 |
| `i18n/da.txt` | 74.8 KB | 76.7 KB | +1998 |
| `lib/reveal/white.css` | 6.8 KB | 4.9 KB | -1971 |
| `lib/reveal/black.css` | 6.8 KB | 4.9 KB | -1970 |
| `app.css` | 584.2 KB | 586.1 KB | +1941 |
| `i18n/zh.txt` | 69.3 KB | 71.1 KB | +1919 |
| `i18n.js` | 131.4 KB | 132.8 KB | +1422 |
| `i18n/mapping.txt` | 96.3 KB | 97.5 KB | +1223 |
| `sim.js` | 17.4 KB | 17.4 KB | +91 |
| `enhance.js` | 12.5 KB | 12.4 KB | -90 |
| `quicklook.css` | 103.3 KB | 103.3 KB | +34 |
| `i18n/en-GB.txt` | 7.4 KB | 7.4 KB | +21 |
| `package.json` | 0.3 KB | 0.3 KB | +0 |

</details>

## Method & caveats

- Inputs are the vendor's own public release artifacts, downloaded unmodified. No DRM, encryption, licensing or anti-tamper mechanism is touched.
- JavaScript is beautified with js-beautify; line numbers refer to that output so anyone can reproduce them (`shadow-log fetch` + open `.cache/<app>/<ver>/pretty/<file>`).
- Findings come from static string/pattern extraction. A new string proves the code shipped, not that the feature is turned on, reachable, or will launch.
- "Unreferenced" UI strings: no first-party code token matches the key name. Keys built dynamically can show up as false positives.
- Third-party library code is marked _(vendor)_ and down-weighted.
- "Official notes" lines compare each finding against the vendor's published release notes with a plain-text search. "Not found" means the search terms did not appear, not that the vendor hid anything.
- Snippets are short excerpts for verification (commentary/reporting), not redistributions of the code.
