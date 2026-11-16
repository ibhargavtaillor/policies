# Privacy Policy — Jira Everyday

**Effective date:** July 4, 2026
**Last updated:** October 25, 2026

Jira Everyday ("the Extension") is a Chrome browser extension that adds small
productivity enhancements to Jira Cloud boards. This policy explains what the
Extension does and does not do with your information.

**Short version: Jira Everyday does not collect, sell, or share any personal
data. It has no servers of its own, no accounts, no analytics, and no tracking.
It runs in your browser, keeps your settings and any tickets you choose to pin in
your browser's own storage, and — for one feature — talks only to your own Jira
instance using your existing session, never to any third-party server.**

The Extension is an independent project and is **not affiliated with, endorsed
by, or sponsored by Atlassian** or Jira.

## Information we collect

**None.** The Extension does not collect any personal data, usage data,
analytics, telemetry, or identifiers, and it has no backend server of its own. It
does not send your data to us or to any third party.

Everything the Extension stores stays in your browser (see "Your settings and
pinned tickets" below). To power one feature it may request data from **your own
Jira instance** — see the "Jira API requests" section below. Those requests go
only to your Jira site, authenticated by your existing session; their responses
are used on your device.

## How the Extension works with data on your device

To provide its features, the Extension reads content on the Jira page you are
viewing and stores your settings locally. None of this information is sent to
the developer or to any third party.

### 1. Reading Jira page content (locally, in your browser)

On Jira Cloud pages (`https://*.atlassian.net/*`), the Extension reads issue
information already displayed on the page — such as an issue's key, title, URL,
the board column it is in, and the "days in column" value Jira shows on board
cards — in order to:

- offer copy actions (for example Ticket ID, Title, URL, branch name, commit
  title, or Markdown link),
- highlight cards that have stayed in a status longer than your configured
  thresholds, and
- let you pin a ticket (see "Pinned tickets" below).

This reading happens entirely on your device, in real time, to render the
features. Apart from tickets you explicitly pin and the small Time in Status
cache described below, **this content is not stored by the Extension, and it is
never transmitted off your device.**

### 2. Clipboard

When you choose a copy action, the Extension writes the selected text to your
system clipboard. Depending on the format you pick, this is built from the
issue's key, title, and/or URL — for example the ticket ID, title, URL, a git
branch name, a commit/PR title, a Markdown link, a "rich link" (a clickable
title, written as both HTML and plain text), or your own custom template.

The Extension **only writes to the clipboard in response to your action (a click
or a number key in the copy menu) and never reads your clipboard.**

### 3. Your settings

The Extension saves your preferences using Chrome's extension storage APIs
(`chrome.storage`). These include, for example: which copy formats are enabled;
your branch-name options (prefix, maximum length, lowercase) and custom copy
template; your Time in Status thresholds, colors, and the board column names you
choose to skip (such as "To Do" or "Done"); and your appearance
(light/dark/system) choice. These settings contain **only your configuration
choices** — not Jira issue content.

- Some settings are stored on your device (`chrome.storage.local`).
- Some settings (your copy-format options and Time in Status settings) use
  Chrome's built-in sync (`chrome.storage.sync`). If you have Chrome Sync
  enabled, Chrome may synchronize these preferences across your signed-in Chrome
  browsers. That synchronization is performed by Google/Chrome, is governed by
  Google's privacy policy, and is not accessible to the Extension developer.

### 4. Pinned tickets

If you use the Pin action, the Extension saves that ticket so you can reach it
from the Extension's popup and reorder it on the options page. For each pinned
ticket it stores **only** the issue key, the title, the ticket's URL, and the
time you pinned it. This information:

- is saved **only when you choose to pin a ticket**,
- is stored on your device only (`chrome.storage.local`) — it is **not** synced
  through Chrome Sync and is never sent to the developer or any third party, and
- is removed when you unpin the ticket or remove the Extension.

Clicking a pinned ticket in the popup simply opens its saved URL in a new
browser tab.

### 5. Jira API requests

The "Time in Status" feature highlights issues that have stayed in a status too
long. When your board already shows a "days in column" value, the Extension reads
it from the page (no network). When it does not, the Extension asks **your own
Jira instance** when the issue entered its current status, by calling Jira's
REST API (`/rest/api/3/issue/{issue key}`, requesting only the issue's status,
creation date, and change history) from the Jira page you are viewing.

- These requests go **only to your Jira site** (the same `*.atlassian.net`
  domain you are on) and are authenticated by **your existing Jira session**
  (browser cookies). The Extension never uses, requests, or stores any password,
  API token, or other credential.
- Requests are made only for issues visible on your board that are not already
  cached.
- Responses are used **on your device** to compute the number of days. Only a
  minimal result is cached locally (`chrome.storage.local`) to avoid repeat
  requests: for each issue key, the date the issue entered its current status,
  the board column it was in, and when the entry was cached. Cache entries expire
  after 12 hours, and the cache is capped at a small number of recent issues.
  **No issue data is sent to the Extension's developer or any third party** —
  there is no such server.
- If you are not signed in to Jira, or a request fails, the feature simply skips
  highlighting; nothing breaks.

## Permissions and why they are needed

- **`storage`** — to save your preferences (copy formats, branch and template
  options, Time in Status thresholds, colors and skipped columns, appearance),
  your pinned tickets, and the small Time in Status cache, so they persist
  between sessions.
- **Host access to `https://*.atlassian.net/*`** — to run the on-page features
  (copy actions, status highlighting, and pinning) on Jira Cloud boards, and to
  make the same-site Jira API requests described above. The Extension runs only
  on Atlassian/Jira Cloud domains and does not run on any other websites.

## Data sharing and selling

The Extension does not share, disclose, or sell any data to anyone. There are no
third-party services, SDKs, advertising, or analytics integrated into the
Extension.

## Data retention

The Extension retains only what it stores in your browser:

- **Settings** — for as long as the Extension is installed, or until you change
  or clear them.
- **Pinned tickets** — until you unpin them or remove the Extension.
- **Time in Status cache** — each entry expires after 12 hours, and the whole
  cache is removed with the Extension.

Because no personal data is collected or transmitted to us, there is nothing
else to retain or delete. You can clear all of this at any time by removing the
Extension, or via your browser's extension storage controls.

## Security

The Extension sends no data to us or to any third party, and requests the minimum
permissions necessary to function. The only network requests it makes are to your
own Jira instance, using your existing session (see "Jira API requests"). Your
settings, pinned tickets, and cache remain within your browser's storage under
your control.

## Children's privacy

The Extension is a developer productivity tool intended for general/professional
use. It does not knowingly collect any information from anyone, including
children.

## Changes to this policy

This policy may be updated as the Extension evolves. Material changes will be
reflected by updating the "Last updated" date above. Continued use of the
Extension after an update constitutes acceptance of the revised policy.

## Contact

Questions about this policy or the Extension's privacy practices can be sent to:

**<bhargavtailor6@gmail.com>**
