# Shadow Log: Obsidian 1.14.5 → 1.15.0

> What the update actually changed, read from the shipped code of two public releases. Every item cites the file and line (in the js-beautify output) where it was found. Automated heuristics: "possible", not "confirmed".

| | old | new |
|---|---|---|
| version | 1.14.5 | 1.15.0 |
| released | 2026-10-22 | 2026-11-02 |
| artifact | https://github.com/obsidianmd/obsidian-releases/releases/download/v1.14.5/obsidian-1.14.5.asar.gz | https://github.com/obsidianmd/obsidian-releases/releases/download/v1.15.0/obsidian-1.15.0.asar.gz |
| files in bundle | 369 | 368 |

Official notes: https://github.com/obsidianmd/obsidian-releases/releases/tag/v1.15.0 · https://obsidian.md/changelog/

**Release-notes cross-check:** 10 of the 10 top findings checked were not found in the official notes for 1.14.5→1.15.0. The check is a plain-text match and can miss reworded announcements.

Generated 2026-11-02T15:43:23.620Z by shadow-log 0.1.0.

## At a glance

| category | added | removed | changed |
|---|---:|---:|---:|
| Telemetry, analytics & tracking | 0 | 6 |  |
| API endpoints (paths) | 0 | 4 |  |
| Contacted / referenced domains | 0 | 11 |  |
| Electron IPC channels & protocols | 1 | 0 |  |
| Feature-flag / experiment-like identifiers | 0 | 5 |  |
| Settings, config & storage keys | 0 | 2 |  |
| Commands | 0 | 3 |  |
| UI strings (localization) | 32 | 27 | 4 |
| Dependencies & bundled libraries | 0 | 0 |  |
| Full URLs | 3 | 28 |  |
| Files in bundle | 9 | 10 | 15 |

## Top findings

### 1. New UI string group `interface.startScreen.mobile` (24 strings)

*Score 98 · 24 new UI strings under one prefix · 24 not referenced by code yet · keywords: sync, cloud, location*

Official notes: not found in the notes for 1.14.5→1.15.0 (searched for: "Set up Obsidian Sync", "up Obsidian Sync", "Obsidian does not have permission to access this location", "Delete vault")

- `interface.startScreen.mobile.buttonSetupObsidianSync` = "Set up Obsidian Sync" *(no code reference found)*
- `interface.startScreen.mobile.labelIcloudDisabled` = "You cannot access or create vaults in iCloud because it's disabled for Obsidian." *(no code reference found)*
- `interface.startScreen.mobile.msgNoLocationPermission` = "Obsidian does not have permission to access this location" *(no code reference found)*
- `interface.startScreen.mobile.buttonDeleteVault` = "Delete vault" *(no code reference found)*
- `interface.startScreen.mobile.buttonForget` = "Forget" *(no code reference found)*
- `interface.startScreen.mobile.buttonForgetVault` = "Forget vault" *(no code reference found)*
- `interface.startScreen.mobile.buttonMoveToDeviceStorage` = "Move to device storage" *(no code reference found)*
- `interface.startScreen.mobile.buttonOpenVault` = "Open vault" *(no code reference found)*
- `interface.startScreen.mobile.buttonOpenVaultRestricted` = "Open vault in restricted mode" *(no code reference found)*
- `interface.startScreen.mobile.buttonRenameVault` = "Rename vault" *(no code reference found)*
- …and 14 more (see UI strings section)

Evidence: `i18n.js` in the new build.

### 2. Removed telemetry/analytics signal `host:www.google-analytics.com`

*Score 75 · keywords: analytics*

Official notes: not found in the notes for 1.14.5→1.15.0 (searched for: "host:www.google-analytics.com")

Evidence (old build):
- `app.js:97643` → `…e.now(), (Q = O.createEl("script")).async = !0, Q.src = "https://www.google-analytics.com/analytics.js", N("create", B, "auto"), N("send", "pageview"))`

### 3. Removed telemetry/analytics signal `event:config`

*Score 60 · Telemetry, analytics & tracking*

Official notes: not found in the notes for 1.14.5→1.15.0 (searched for: "event:config")

Evidence (old build):
- `app.js:97641` → `}, window.gtag("js", new Date), window.gtag("config", B), (Q = O.createEl("script")).async = !0, Q.src = "https://www.googletagmanager.com/gtag/js?id=" + B) : (…`

### 4. Removed telemetry/analytics signal `event:event`

*Score 60 · Telemetry, analytics & tracking*

Official notes: not found in the notes for 1.14.5→1.15.0 (searched for: "event:event")

Evidence (old build):
- `app.js:97765` → `window.ga && window.ga("send", "pageview"), window.gtag && window.gtag("event", "page_view")`

### 5. Removed telemetry/analytics signal `event:js`

*Score 60 · Telemetry, analytics & tracking*

Official notes: not found in the notes for 1.14.5→1.15.0 (searched for: "event:js")

Evidence (old build):
- `app.js:97641` → `}, window.gtag("js", new Date), window.gtag("config", B), (Q = O.createEl("script")).async = !0, Q.src = "https://www.googletagmanager.com/gtag/js?id=" + B) : (…`

### 6. Removed telemetry/analytics signal `host:www.googletagmanager.com`

*Score 60 · Telemetry, analytics & tracking*

Official notes: not found in the notes for 1.14.5→1.15.0 (searched for: "host:www.googletagmanager.com")

Evidence (old build):
- `app.js:97641` → `…fig", B), (Q = O.createEl("script")).async = !0, Q.src = "https://www.googletagmanager.com/gtag/js?id=" + B) : (window.GoogleAnalyticsObject = "ga", N = window.…`

### 7. Removed telemetry/analytics signal `sdk:gtag`

*Score 60 · Telemetry, analytics & tracking*

Official notes: not found in the notes for 1.14.5→1.15.0 (searched for: "sdk:gtag")

Evidence (old build):
- `app.js:97765` → `window.ga && window.ga("send", "pageview"), window.gtag && window.gtag("event", "page_view")`
- `app.js:97641` → `}, window.gtag("js", new Date), window.gtag("config", B), (Q = O.createEl("script")).async = !0, Q.src = "https://www.googletagmanager.com/gtag/js?id=" + B) : (…`

### 8. New IPC channel `plugin-script-root` (renderer, sendSync)

*Score 45 · Electron IPC channels & protocols*

Official notes: not found in the notes for 1.14.5→1.15.0 (searched for: "plugin script root")

Evidence:
- `main.js:5548` → `}), r.ipcMain.on("plugin-script-root", i => {`
- `app.js:113388` → `` …f (eP === void 0 && S.isDesktopApp && (eP = Vt("electron").ipcRenderer.sendSync("plugin-script-root")), eP && (a = await $De(`${eP}${encodeURIComponent(this.app… ``

### 9. Removed domain referenced: `www.google-analytics.com`

*Score 42 · keywords: analytics*

Official notes: not found in the notes for 1.14.5→1.15.0 (searched for: "www.google-analytics.com")

Evidence (old build):
- `app.js:97643` → `…e.now(), (Q = O.createEl("script")).async = !0, Q.src = "https://www.google-analytics.com/analytics.js", N("create", B, "auto"), N("send", "pageview"))`

### 10. Removed API path `/user/forgetpass`

*Score 35 · API endpoints (paths)*

Official notes: not found in the notes for 1.14.5→1.15.0 (searched for: "/user/forgetpass")

Evidence (old build):
- `app.js:55516` → `return bD("/user/forgetpass", {`

## New UI string groups

Strings are grouped by key prefix. Groups whose strings no first-party code references yet are candidates for unreleased features.

| group | new strings | unreferenced | sample |
|---|---:|---:|---|
| `interface.startScreen.mobile` | 24 | 24 | "Set up Obsidian Sync" |
| `plugins.bases` | 2 | 0 | "Move to all views" |
| `setting.corePlugin` | 2 | 0 | "Required by your organization's policy." |
| `setting.thirdPartyPlugin` | 2 | 0 | "Plugin “{{name}}” is not permitted by your organization's policy." |
| `dialogue` | 1 | 0 | "Heading “{{heading}}” not found in file." |
| `interface` | 1 | 0 | "The “{{param}}” URI parameter requires “append” or “prepend.”" |

## Details by category

### Telemetry, analytics & tracking

<details><summary>Removed (6)</summary>

| score | removed | evidence |
|---:|---|---|
| 75 | `host:www.google-analytics.com` | `app.js:97643` → `…e.now(), (Q = O.createEl("script")).async = !0, Q.src = "https://www.google-analytics.com/analytics.js", N("create", B, "auto"), N("send", "pageview"))` |
| 60 | `event:config` | `app.js:97641` → `}, window.gtag("js", new Date), window.gtag("config", B), (Q = O.createEl("script")).async = !0, Q.src = "https://www.googletagmanager.com/gtag/js?id=" + B) : (…` |
| 60 | `event:event` | `app.js:97765` → `window.ga && window.ga("send", "pageview"), window.gtag && window.gtag("event", "page_view")` |
| 60 | `event:js` | `app.js:97641` → `}, window.gtag("js", new Date), window.gtag("config", B), (Q = O.createEl("script")).async = !0, Q.src = "https://www.googletagmanager.com/gtag/js?id=" + B) : (…` |
| 60 | `host:www.googletagmanager.com` | `app.js:97641` → `…fig", B), (Q = O.createEl("script")).async = !0, Q.src = "https://www.googletagmanager.com/gtag/js?id=" + B) : (window.GoogleAnalyticsObject = "ga", N = window.…` |
| 60 | `sdk:gtag` | `app.js:97765` → `window.ga && window.ga("send", "pageview"), window.gtag && window.gtag("event", "page_view")` |

</details>

### API endpoints (paths)

<details><summary>Removed (4)</summary>

| score | removed | evidence |
|---:|---|---|
| 35 | `/user/forgetpass` | `app.js:55516` → `return bD("/user/forgetpass", {` |
| 35 | `/user/pow-challenge` | `app.js:57875` → `return t.trys.push([0, 2, , 3]), [4, bD("/user/pow-challenge", {})];` |
| 35 | `/user/resendconfirmation` | `app.js:55523` → `return bD("/user/resendconfirmation", {` |
| 35 | `/user/signup` | `app.js:55506` → `return bD("/user/signup", {` |

</details>

### Contacted / referenced domains

<details><summary>Removed (11)</summary>

| score | removed | evidence |
|---:|---|---|
| 42 | `www.google-analytics.com` | `app.js:97643` → `…e.now(), (Q = O.createEl("script")).async = !0, Q.src = "https://www.google-analytics.com/analytics.js", N("create", B, "auto"), N("send", "pageview"))` |
| 31 | `www.googletagmanager.com` | `app.js:97641` → `…fig", B), (Q = O.createEl("script")).async = !0, Q.src = "https://www.googletagmanager.com/gtag/js?id=" + B) : (window.GoogleAnalyticsObject = "ga", N = window.…` |
| 8 | `chevrotain.io` _(vendor)_ | `lib/mermaid.min.js:1091` → `` See: https://chevrotain.io/docs/guide/resolving_lexer_errors.html#COMPLEMENT for details.`);else{let n="";e&&(n=` `` |
| 8 | `en.wikipedia.org` _(vendor)_ | `lib/mermaid.min.js:3021` → `…unction generator. Copyright Gaetan Renaudeau. MIT License: http://en.wikipedia.org/wiki/MIT_License *)` |
| 8 | `engelschall.com` _(vendor)_ | `lib/mermaid.min.js:3011` → `Copyright (c) 2013-2014 Ralf S. Engelschall (http://engelschall.com)` |
| 8 | `jquery.org` _(vendor)_ | `lib/mermaid.min.js:3017` → `https://jquery.org/license/` |
| 8 | `langium.org` _(vendor)_ | `lib/mermaid.min.js:1233` → `… detected. Please make "'+String(e)+'" lazy. Visit https://langium.org/docs/reference/configuration-services/#resolving-cyclic-dependencies');return t[e]}else i…` |
| 8 | `lodash.com` _(vendor)_ | `lib/mermaid.min.js:3000` → `* Lodash (Custom Build) <https://lodash.com/>` |
| 8 | `openjsf.org` _(vendor)_ | `lib/mermaid.min.js:3002` → `* Copyright OpenJS Foundation and other contributors <https://openjsf.org/>` |
| 8 | `tldrlegal.com` _(vendor)_ | `lib/mermaid.min.js:3018` → `https://tldrlegal.com/license/mit-license` |
| 8 | `underscorejs.org` _(vendor)_ | `lib/mermaid.min.js:3004` → `* Based on Underscore.js 1.8.3 <http://underscorejs.org/LICENSE>` |

</details>

### Electron IPC channels & protocols

<details open><summary>Added (1)</summary>

| score | added | evidence |
|---:|---|---|
| 45 | `plugin-script-root` | `main.js:5548` → `}), r.ipcMain.on("plugin-script-root", i => {` |

</details>

### Feature-flag / experiment-like identifiers

<details><summary>Removed (5)</summary>

| score | removed | evidence |
|---:|---|---|
| 35 | `beta` | `worker.js:6751` → `…Tau":"Τ","Upsilon":"Υ","Phi":"Φ","Chi":"Χ","Psi":"Ψ","Omega":"Ω","alpha":"α","beta":"β","gamma":"γ","delta":"δ","epsilon":"ε","zeta":"ζ","eta":"η","theta":"θ","…` |
| 35 | `Beta` | `worker.js:6751` → `…c":"û","uuml":"ü","yacute":"ý","thorn":"þ","yuml":"ÿ","fnof":"ƒ","Alpha":"Α","Beta":"Β","Gamma":"Γ","Delta":"Δ","Epsilon":"Ε","Zeta":"Ζ","Eta":"Η","Theta":"Θ","…` |
| 25 | `feature-cell` | `app.js:58294` → `e.createDiv("feature-cell", (function(e) {` |
| 25 | `feature-row` | `app.js:58293` → `e.createDiv("feature-row", (function(e) {` |
| 25 | `mobile-onboarding-feature-table` | `app.js:58282` → `return r.formEl.createDiv("mobile-onboarding-feature-table", (function(e) {` |

</details>

### Settings, config & storage keys

<details><summary>Removed (2)</summary>

| score | removed | evidence |
|---:|---|---|
| 21 | `obsidian` | `app.js:97471` → `window.localStorage.setItem("obsidian", "obsidian"), window.localStorage.removeItem("obsidian")` |
| 21 | `site-theme` | `app.js:97608` → `}, (A = localStorage.getItem("site-theme")) && this.setTheme(A), this.leftSiteThemeToggleEl.createSpan({` |

</details>

### Commands

<details><summary>Removed (3)</summary>

| score | removed | evidence |
|---:|---|---|
| 25 | `editor:set-heading-` | `app.js:79601` → `id: "editor:set-heading-".concat(e),` |
| 25 | `editor:toggle-highlight-` | `app.js:79646` → `id: "editor:toggle-highlight-".concat(e),` |
| 25 | `workspace:goto-tab-` | `app.js:113712` → `id: "workspace:goto-tab-".concat(e),` |

</details>

### UI strings (localization)

<details open><summary>Added (32)</summary>

| score | added | evidence |
|---:|---|---|
| 55 | `interface.startScreen.mobile.buttonSetupObsidianSync` | "Set up Obsidian Sync" **(unreferenced)** |
| 55 | `interface.startScreen.mobile.labelIcloudDisabled` | "You cannot access or create vaults in iCloud because it's disabled for Obsidian." **(unreferenced)** |
| 55 | `interface.startScreen.mobile.msgNoLocationPermission` | "Obsidian does not have permission to access this location" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.buttonDeleteVault` | "Delete vault" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.buttonForget` | "Forget" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.buttonForgetVault` | "Forget vault" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.buttonMoveToDeviceStorage` | "Move to device storage" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.buttonOpenVault` | "Open vault" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.buttonOpenVaultRestricted` | "Open vault in restricted mode" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.buttonRenameVault` | "Rename vault" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.labelDeleteVault` | "Delete vault “{{name}}”" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.labelDeleteVaultConfirm` | "This action is irreversible. Please confirm you want to delete it." **(unreferenced)** |
| 40 | `interface.startScreen.mobile.labelDeleteVaultWarning` | "Deleting this vault will delete all files in it." **(unreferenced)** |
| 40 | `interface.startScreen.mobile.labelForgetVault` | "Forget vault “{{name}}”" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.labelForgetVaultDesc` | "Forgetting this vault will remove it from the list of vaults without deleting any files." **(unreferenced)** |
| 40 | `interface.startScreen.mobile.labelOutdatedWebView` | "Update Android WebView" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.labelOutdatedWebViewDesc` | "Your Android device is not up to date, and must be updated for Obsidian to work. Please fi" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.labelRenameVault` | "Rename vault “{{name}}”" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.labelVaultInAppFolder` | "This vault is located in the Obsidian app folder." **(unreferenced)** |
| 40 | `interface.startScreen.mobile.labelVaultLocatedAt` | "This vault is located at {{path}}" **(unreferenced)** |
| 40 | `interface.startScreen.mobile.msgDeleteFailed` | "Failed to delete vault." **(unreferenced)** |
| 40 | `interface.startScreen.mobile.msgInvalidVaultNameCharacters` | "Vault name cannot contain any of these characters: " **(unreferenced)** |
| 40 | `interface.startScreen.mobile.msgMoveOldCopyNotDeleted` | "The vault was moved, but the old copy in the Obsidian app folder could not be deleted." **(unreferenced)** |
| 40 | `interface.startScreen.mobile.msgMovingVault` | "Moving from {{from}} to {{to}}" **(unreferenced)** |
| 15 | `dialogue.msgHeadingNotFound` | "Heading “{{heading}}” not found in file." |
| 15 | `interface.msgInsertParamRequiresMode` | "The “{{param}}” URI parameter requires “append” or “prepend.”" |
| 15 | `plugins.bases.actionMoveToAllViews` | "Move to all views" |
| 15 | `plugins.bases.actionMoveToThisView` | "Move to this view" |
| 15 | `setting.corePlugin.tooltipRequiredByPolicy` | "Required by your organization's policy." |
| 15 | `setting.corePlugin.tooltipTurnedOffByPolicy` | "Turned off by your organization's policy." |
| 15 | `setting.thirdPartyPlugin.msgPluginNotPermitted` | "Plugin “{{name}}” is not permitted by your organization's policy." |
| 15 | `setting.thirdPartyPlugin.tooltipNotPermittedByPolicy` | "Not permitted by your organization's policy." |

</details>

<details><summary>Removed (27)</summary>

| score | removed | evidence |
|---:|---|---|
| 11 | `dialogue.buttonAllow` | "Allow" |
| 11 | `editor.linkSuggestion.labelAccept` | "to accept" |
| 11 | `plugins.canvas.instructionJumpToGroup` | "to navigate to group" |
| 11 | `plugins.canvas.instructionNarrowBlock` | "to embed block" |
| 11 | `plugins.canvas.instructionNarrowHeading` | "to embed heading" |
| 11 | `plugins.commandPalette.instructionDismiss` | "to dismiss" |
| 11 | `plugins.commandPalette.instructionNavigate` | "to navigate" |
| 11 | `plugins.commandPalette.instructionUse` | "to use" |
| 11 | `plugins.fileExplorer.instructionDismiss` | "to dismiss" |
| 11 | `plugins.fileExplorer.instructionMove` | "to move" |
| 11 | `plugins.fileExplorer.instructionNavigate` | "to navigate" |
| 11 | `plugins.mermaid.labelGuardDesc` | "Only allow if you trust this vault's contents." |
| 11 | `plugins.mermaid.labelGuardTitle` | "Display Mermaid diagrams in this vault?" |
| 11 | `plugins.noteComposer.instructionAppend` | "to move to bottom" |
| 11 | `plugins.noteComposer.instructionDismiss` | "to dismiss" |
| 11 | `plugins.noteComposer.instructionMerge` | "to merge" |
| 11 | `plugins.noteComposer.instructionNavigate` | "to navigate" |
| 11 | `plugins.quickSwitcher.instructionDismiss` | "to dismiss" |
| 11 | `plugins.quickSwitcher.instructionNavigate` | "to navigate" |
| 11 | `plugins.quickSwitcher.instructionOpen` | "to open" |
| 11 | `plugins.quickSwitcher.instructionSelect` | "to select" |
| 11 | `plugins.templates.instructionDismiss` | "to dismiss" |
| 11 | `plugins.templates.instructionInsert` | "to insert template" |
| 11 | `plugins.templates.instructionNavigate` | "to navigate" |
| 11 | `properties.valueSuggestion.instructionDismiss` | "to dismiss" |
| 11 | `setting.editor.optionMermaidAllow` | "Show Mermaid diagrams in notes" |
| 11 | `setting.editor.optionMermaidAllowDescription` | "Render flowcharts, sequence diagrams, and other diagrams from “mermaid” code blocks." |

</details>

<details><summary>Changed (4)</summary>

| key | before | after |
|---|---|---|
| `editor.linkSuggestion.labelTypeBlock` | "Type ^" | "^" |
| `editor.linkSuggestion.labelTypeHash` | "Type #" | "#" |
| `editor.linkSuggestion.labelTypePipe` | "Type \|" | "\|" |
| `plugins.bases.labelSearchResults` | "Showing {{count}}" | "Showing {{shown}} of {{total}}" |

</details>

### Full URLs

<details open><summary>Added (3)</summary>

| score | added | evidence |
|---:|---|---|
| 20 | `https://obsidian.md/changelog/desktop/$` | `app.js:108701` → `` let t = `https://obsidian.md/changelog/desktop/${o}.md`; `` |
| 20 | `https://platform.twitter.com/embed/Tweet.html?dnt=true&theme=$` | `quicklook.js:15165` → `` … "?start=" + e[2])), r) : (e = r.match(Dy), e ? `https://platform.twitter.com/embed/Tweet.html?dnt=true&theme=${document.body.hasClass("theme-dark")?"dark":"lig… `` |
| 20 | `https://releases.obsidian.md/stats/theme/$` | `app.js:56088` → `` url: `https://releases.obsidian.md/stats/theme/${encodeURIComponent(r)}/download` `` |

</details>

<details><summary>Removed (28)</summary>

| score | removed | evidence |
|---:|---|---|
| 25 | `https://www.google-analytics.com/analytics.js` | `app.js:97643` → `…e.now(), (Q = O.createEl("script")).async = !0, Q.src = "https://www.google-analytics.com/analytics.js", N("create", B, "auto"), N("send", "pageview"))` |
| 14 | `https://obsidian.md/` | `help.js:333` → `M = "en" === t ? "https://obsidian.md/help" : "https://obsidian.md/".concat(t, "/help"),` |
| 14 | `https://obsidian.md/changelog/desktop/` | `app.js:110569` → `t = "https://obsidian.md/changelog/desktop/".concat(e, ".md"), i.label = 1;` |
| 14 | `https://platform.twitter.com/embed/Tweet.html?dnt=true&theme=` | `quicklook.js:27953` → `return "https://platform.twitter.com/embed/Tweet.html?dnt=true&theme=".concat(a ? "dark" : "light", "&id=").concat(t[1])` |
| 14 | `https://releases.obsidian.md/stats/theme/` | `app.js:55172` → `url: "https://releases.obsidian.md/stats/theme/".concat(encodeURIComponent(n), "/download")` |
| 14 | `https://www.googletagmanager.com/gtag/js?id=` | `app.js:97641` → `…fig", B), (Q = O.createEl("script")).async = !0, Q.src = "https://www.googletagmanager.com/gtag/js?id=" + B) : (window.GoogleAnalyticsObject = "ga", N = window.…` |
| 6 | `http://en.wikipedia.org/wiki/MIT_License` _(vendor)_ | `lib/mermaid.min.js:3021` → `…unction generator. Copyright Gaetan Renaudeau. MIT License: http://en.wikipedia.org/wiki/MIT_License *)` |
| 6 | `http://underscorejs.org/LICENSE` _(vendor)_ | `lib/mermaid.min.js:3004` → `* Based on Underscore.js 1.8.3 <http://underscorejs.org/LICENSE>` |
| 6 | `https://jquery.org/license/` _(vendor)_ | `lib/mermaid.min.js:3017` → `https://jquery.org/license/` |
| 6 | `https://lodash.com/license` _(vendor)_ | `lib/mermaid.min.js:3003` → `* Released under MIT license <https://lodash.com/license>` |
| 6 | `https://tldrlegal.com/license/mit-license` _(vendor)_ | `lib/mermaid.min.js:3018` → `https://tldrlegal.com/license/mit-license` |
| 4 | `http://engelschall.com` _(vendor)_ | `lib/mermaid.min.js:3011` → `Copyright (c) 2013-2014 Ralf S. Engelschall (http://engelschall.com)` |
| 4 | `https://chevrotain.io/docs/changes/BREAKING_CHANGES.html` _(vendor)_ | `lib/mermaid.min.js:1168` → `See: https://chevrotain.io/docs/changes/BREAKING_CHANGES.html#_6-0-0` |
| 4 | `https://chevrotain.io/docs/FAQ.html` _(vendor)_ | `lib/mermaid.min.js:1141` → `For further details see: https://chevrotain.io/docs/FAQ.html#NUMERICAL_SUFFIXES` |
| 4 | `https://chevrotain.io/docs/guide/internals.html` _(vendor)_ | `lib/mermaid.min.js:1176` → `` See: https://chevrotain.io/docs/guide/internals.html#grammar-recording for details`,-1,-1,-1,-1,-1,-1);Object.freeze(jye);Krt={name:`This CSTNode indicates the … `` |
| 4 | `https://chevrotain.io/docs/guide/resolving_grammar_errors.html` _(vendor)_ | `lib/mermaid.min.js:1150` → `See: https://chevrotain.io/docs/guide/resolving_grammar_errors.html#COMMON_PREFIX` |
| 4 | `https://chevrotain.io/docs/guide/resolving_lexer_errors.html` _(vendor)_ | `lib/mermaid.min.js:1091` → `` See: https://chevrotain.io/docs/guide/resolving_lexer_errors.html#COMPLEMENT for details.`);else{let n="";e&&(n=` `` |
| 4 | `https://github.com/chevrotain/chevrotain/issues` _(vendor)_ | `lib/mermaid.min.js:1096` → `` Please open an issue at: https://github.com/chevrotain/chevrotain/issues`+n)}}return[]}function OF(t,e,r){switch(t.type){case"Disjunction":for(let i=0;i<t.value… `` |
| 4 | `https://github.com/chevrotain/chevrotain/issues/564` _(vendor)_ | `lib/mermaid.min.js:1133` → `` See: https://github.com/chevrotain/chevrotain/issues/564#issuecomment-349062346 for details.`;return Gt(t,K1e)&&(r.CATEGORIES=t[K1e]),jh([r]),Gt(t,Q1e)&&(r.LABE… `` |
| 4 | `https://github.com/jquery/jquery/blob/master/src/event.js` _(vendor)_ | `lib/mermaid.min.js:3019` → `https://github.com/jquery/jquery/blob/master/src/event.js` |
| 4 | `https://github.com/markedjs/marked` _(vendor)_ | `lib/mermaid.min.js:447` → `` Please report this to https://github.com/markedjs/marked.`,t){let n="<p>An error occurred:</p><pre>"+du(r.message+"",!0)+"</pre>";return e?Promise.resolve(n):n}… `` |
| 4 | `https://github.com/mermaid-js/mermaid/issues` _(vendor)_ | `lib/mermaid.min.js:2619` → `…due to a bug within Mermaid, please report this issue at https://github.com/mermaid-js/mermaid/issues.");K.debug(e),xft(e,r)},"parse")}});var Tft,wft,KEe,QEe=O(…` |
| 4 | `https://github.com/nodeca/js-yaml` _(vendor)_ | `lib/mermaid.min.js:2995` → `(*! js-yaml 4.1.1 https://github.com/nodeca/js-yaml @license MIT *)` |
| 4 | `https://github.com/uuidjs/uuid` _(vendor)_ | `lib/mermaid.min.js:2460` → `…ues)throw new Error("crypto.getRandomValues() not supported. See https://github.com/uuidjs/uuid#getrandomvalues-not-supported");qU=crypto.getRandomValues.bind(c…` |
| 4 | `https://langium.org/docs/reference/configuration-services/` _(vendor)_ | `lib/mermaid.min.js:1233` → `… detected. Please make "'+String(e)+'" lazy. Visit https://langium.org/docs/reference/configuration-services/#resolving-cyclic-dependencies');return t[e]}else i…` |
| 4 | `https://lodash.com/` _(vendor)_ | `lib/mermaid.min.js:3000` → `* Lodash (Custom Build) <https://lodash.com/>` |
| 4 | `https://openjsf.org/` _(vendor)_ | `lib/mermaid.min.js:3002` → `* Copyright OpenJS Foundation and other contributors <https://openjsf.org/>` |
| 4 | `https://unpkg.com/mermaid@11.13.0/dist/mermaid.min.js` _(vendor)_ | `lib/mermaid.min.js:1` → `// Source: https://unpkg.com/mermaid@11.13.0/dist/mermaid.min.js` |

</details>

## File changes

**Added:** `public/InterVariable-Italic.woff2` (378.9 KB), `public/InterVariable.woff2` (344.0 KB), `public/SourceCodePro-Bold.ttf` (187.1 KB), `public/SourceCodePro-BoldItalic.ttf` (151.6 KB), `public/SourceCodePro-Italic.ttf` (157.6 KB), `public/SourceCodePro-Regular.ttf` (188.2 KB), `public/external-link-rtl.svg` (0.3 KB), `public/external-link.svg` (0.3 KB), `public/flow-circular.woff2` (7.7 KB)

**Removed:** `lib/mermaid.min.js` (2.8 MB), `public/fonts/01dcbad1bac635f9c9cd.woff2` (378.9 KB), `public/fonts/05b618077343fbbd92b7.ttf` (151.6 KB), `public/fonts/454577c22304619db035.ttf` (157.6 KB), `public/fonts/4bb6ac751d1c5478ff3a.woff2` (7.7 KB), `public/fonts/52ac8f3034507f1d9e53.ttf` (187.1 KB), `public/fonts/70cc7ff27245e82ad414.ttf` (188.2 KB), `public/fonts/c504db5c06caaf7cdfba.woff2` (344.0 KB), `public/images/2308ab1944a6bfa5c5b8.svg` (0.3 KB), `public/images/6155340132a851f6089e.svg` (0.3 KB)

<details><summary>Changed (15)</summary>

| file | before | after | Δ bytes |
|---|---:|---:|---:|
| `app.js` | 3.8 MB | 3.2 MB | -569856 |
| `app.css` | 652.6 KB | 584.2 KB | -69986 |
| `starter.js` | 450.6 KB | 428.6 KB | -22485 |
| `quicklook.css` | 114.3 KB | 103.3 KB | -11286 |
| `worker.js` | 234.2 KB | 244.6 KB | +10695 |
| `help.js` | 389.8 KB | 380.4 KB | -9578 |
| `main.js` | 198.9 KB | 207.1 KB | +8331 |
| `lib/codemirror/vim.js` | 243.1 KB | 249.9 KB | +6966 |
| `quicklook.js` | 663.2 KB | 659.4 KB | -3883 |
| `i18n.js` | 129.9 KB | 131.4 KB | +1580 |
| `enhance.js` | 12.9 KB | 12.5 KB | -458 |
| `lib/codemirror/markdown.js` | 44.0 KB | 44.3 KB | +303 |
| `sim.js` | 17.3 KB | 17.4 KB | +84 |
| `index.html` | 1.4 KB | 1.3 KB | -69 |
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
