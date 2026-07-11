# Privacy Policy — Jira Everyday

**Effective date:** July 4, 2026
**Last updated:** July 11, 2026

Jira Everyday ("the Extension") is a Chrome browser extension that adds small
productivity enhancements to Jira Cloud boards. This policy explains what the
Extension does and does not do with your information.

**Short version: Jira Everyday does not collect, store, sell, or share any
personal data. It has no servers of its own, no accounts, no analytics, and no
tracking. It runs in your browser and — for one feature — talks only to your own
Jira instance using your existing session, never to any third-party server.**

The Extension is an independent project and is **not affiliated with, endorsed
by, or sponsored by Atlassian** or Jira.

## Information we collect

**None.** The Extension does not collect any personal data, usage data,
analytics, telemetry, or identifiers, and it has no backend server of its own. It
does not send your data to us or to any third party.

To power one feature it may request data from **your own Jira instance** — see
the "Jira API requests" section below. Those requests go only to your Jira site,
authenticated by your existing session; their responses are used on your device.

## How the Extension works with data on your device

To provide its features, the Extension reads content on the Jira page you are
viewing and stores your settings locally. None of this information is sent
anywhere.

### 1. Reading Jira page content (locally, in your browser)

On Jira Cloud pages (`https://*.atlassian.net/*`), the Extension reads issue
information already displayed on the page — such as an issue's key, title, URL,
and the "days in column" value Jira shows on board cards — in order to:

- offer copy actions (Copy Ticket ID, Title, URL), and
- highlight cards that have stayed in a status longer than your configured
  thresholds.

This reading happens entirely on your device, in real time, to render the
features. **This content is never collected, stored by the Extension, or
transmitted off your device.**

### 2. Clipboard

When you choose a copy action, the Extension writes the selected value (the
issue's ID, title, or URL) to your system clipboard. The Extension **only writes
to the clipboard in response to your click and never reads your clipboard.**

### 3. Your settings

The Extension saves your preferences — for example, which copy actions are
enabled, your Time in Status thresholds and colors, and your appearance
(light/dark/system) choice — using Chrome's extension storage APIs
(`chrome.storage`). These settings contain **only your configuration choices**
— never Jira issue content.

- Some settings are stored on your device (`chrome.storage.local`).
- Some settings use Chrome's built-in sync (`chrome.storage.sync`). If you have
  Chrome Sync enabled, Chrome may synchronize these preferences across your
  signed-in Chrome browsers. That synchronization is performed by Google/Chrome,
  is governed by Google's privacy policy, and is not accessible to the Extension
  developer.

You can clear these settings at any time by removing the Extension, or via your
browser's extension storage controls.

### 4. Jira API requests

The "Time in Status" feature highlights issues that have stayed in a status too
long. When your board already shows a "days in column" value, the Extension reads
it from the page (no network). When it does not, the Extension asks **your own
Jira instance** how long the issue has been in its current status by calling
Jira's REST API (e.g. `/rest/api/3/search`) from the Jira page you are viewing.

- These requests go **only to your Jira site** (the same `*.atlassian.net`
  domain you are on) and are authenticated by **your existing Jira session**
  (browser cookies). The Extension never uses, requests, or stores any password,
  API token, or other credential.
- Responses are used **on your device** to compute the number of days, and a
  minimal result (the date an issue entered its status) is cached locally
  (`chrome.storage.local`) to avoid repeat requests. **No issue data is sent to
  the Extension's developer or any third party** — there is no such server.
- If you are not signed in to Jira, or a request fails, the feature simply skips
  highlighting; nothing breaks.

## Permissions and why they are needed

- **`storage`** — to save your preferences (feature toggles, thresholds, colors,
  appearance) so they persist between sessions.
- **Host access to `https://*.atlassian.net/*`** — to run the on-page features
  (copy actions and status highlighting) on Jira Cloud boards. The Extension
  runs only on Atlassian/Jira Cloud domains and does not run on any other
  websites.

## Data sharing and selling

The Extension does not share, disclose, or sell any data to anyone. There are no
third-party services, SDKs, advertising, or analytics integrated into the
Extension.

## Data retention

The Extension retains only your settings, and only for as long as the Extension
is installed (or until you clear them). Because no personal data is collected or
transmitted, there is nothing else to retain or delete.

## Security

The Extension sends no data to us or to any third party, and requests the minimum
permissions necessary to function. The only network requests it makes are to your
own Jira instance, using your existing session (see "Jira API requests"). Your
settings and cache remain within your browser's storage under your control.

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
