# Privacy Policy — Jira Everyday

**Effective date:** July 4, 2026
**Last updated:** July 4, 2026

Jira Everyday ("the Extension") is a Chrome browser extension that adds small
productivity enhancements to Jira Cloud boards. This policy explains what the
Extension does and does not do with your information.

**Short version: Jira Everyday does not collect, store, transmit, sell, or share
any personal data. Everything it does happens locally in your browser. There are
no servers, no accounts, no analytics, and no tracking.**

The Extension is an independent project and is **not affiliated with, endorsed
by, or sponsored by Atlassian** or Jira.

## Information we collect

**None.** The Extension does not collect or transmit any personal data,
usage data, analytics, telemetry, or identifiers. It has no backend server and
makes no network requests of its own.

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

The Extension performs no network transmission of your data and requests the
minimum permissions necessary to function. Your settings remain within your
browser's storage under your control.

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
