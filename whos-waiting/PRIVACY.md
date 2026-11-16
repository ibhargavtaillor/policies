# Privacy Policy — Who’s Waiting

**Effective date:** November 16, 2026
**Last updated:** November 16, 2026

Who’s Waiting ("the Extension") is a Chrome browser extension that shows, in a
side panel, the people who are waiting on your reply in the apps you connect
(currently Slack). This policy explains what the Extension does and does not do
with your information.

**Short version: Who’s Waiting does not collect, sell, or share any personal
data. It has no servers of its own, no accounts, no analytics, and no tracking.
It reads only the apps you choose to connect, directly from your browser, using
read-only access. Messages are scored on your device, and the little it keeps is
stored in your browser — never sent to the developer or any third party.**

The Extension is an independent project and is **not affiliated with, endorsed
by, or sponsored by Slack Technologies, Salesforce,** or any other service it
connects to.

## Information we collect

**None.** The Extension does not collect any personal data, usage data,
analytics, telemetry, or identifiers, and it has no backend server of its own. It
does not send your data to us or to any third party.

Everything the Extension stores stays in your browser (see "What is stored on
your device" below). To find who is waiting on you, it requests data from the
**apps you connect** — see "Connecting Slack" below. Those requests go directly
from your browser to that app's own API; their responses are processed on your
device.

## Connecting Slack

Slack is read through a small Slack app that **you create in your own
workspace**. You paste its User OAuth Token (`xoxp-…`) into the Extension. That
token is limited to two read-only scopes:

- **`search:read`** — to find direct messages sent to you, messages that
  @mention you, and your own replies (so the Extension knows when you have
  already answered).
- **`users:read`** — to show the names and profile photos of the people who
  wrote to you, and to tell whether a sender is a bot or app.

How the Extension uses this access:

- Requests go **only to Slack's API** (`https://slack.com/api/`), directly from
  your browser, authenticated with your token. The Extension uses only these
  Slack methods: `auth.test` (to check the token once when you connect),
  `search.messages`, and `users.info`.
- Each scan, about every 2 minutes, runs three searches limited to **the last 7
  days**: messages sent to you, messages that mention you, and messages from
  you. It does **not** read channel history, so it never sees channels where
  you are not mentioned.
- The Extension is **read-only**. It can never send, post, edit, react to,
  delete, archive, or label anything in Slack.
- Messages are scored **on your device** to decide whether they expect a reply
  from you. Message text is used in memory for this and is not stored, except
  as described in "What is stored on your device".
- An app you do not connect is never read.

## How your token is protected

Your Slack token is **encrypted at rest** with AES-GCM before it is saved in
your browser's extension storage. The encryption key is a non-extractable key
held by the browser, so the raw key cannot be read back out. The token is never
sent anywhere except to Slack's API as described above, and is never sent to the
developer.

When you disconnect Slack, the Extension deletes the token from your browser.
Because the token belongs to a Slack app you own, you can also revoke it at any
time from Slack (api.slack.com/apps → your app).

## What is stored on your device

The Extension saves data using Chrome's local extension storage
(`chrome.storage.local`) and the browser's IndexedDB (for the encryption key
only). **Nothing is synced through Chrome Sync and nothing is sent to the
developer or any third party.**

1. **Tracked items.** For each message that may need your reply, the Extension
   keeps: the sender's display name and profile photo link, the conversation
   name, when it was received, a link to open it in Slack, its score and the
   reasons for that score, and its state (for example waiting, snoozed, done).
   - **Message text:** if "Show message text" is on (the default), the start of
     the message (up to 500 characters) is kept so the list can show what the
     person is waiting for. Turning that setting off deletes this text right
     away and stops it from being stored.
   - **"Why is this here?" reasons** may include a short quote (about 40
     characters) of the sentence that matched a rule, for example
     *Asks you something “Can you review the PR…”*.
   - Nothing is stored for messages that are ignored (for example bots,
     `@channel` posts, or messages you have already answered).
2. **Your Slack account reference** — your Slack user ID, workspace ID,
   workspace name, and workspace URL, so the Extension can search for messages
   that mention you and build links to them.
3. **Your encrypted Slack token** (see above).
4. **Your settings** — which kinds of messages to track (DMs, group DMs,
   mentions), whether to show message text, notification options, and your
   appearance (light/dark/device) choice — plus setup progress and the time of
   the last scan.

## Notifications

If notifications are on, the Extension shows pop-ups through Chrome's
notification system when someone new is waiting on you (for example "Priya is
waiting on you") and an optional reminder after a set time. A pop-up may include
a short preview of the message. These are created
on your device and shown by Chrome and your operating system. You can turn them
off, or change the reminder time, in the Extension's settings.

## Profile photos

When a sender has set a Slack profile photo, the side panel displays it by
loading the image from Slack's servers, the same way Slack itself does. This
image request goes to Slack only; no other data is sent with it by the
Extension.

## Permissions and why they are needed

- **`storage`** — to save tracked items, your settings, your Slack account
  reference, and your encrypted token on your device.
- **`alarms`** — to check for new messages about every 2 minutes.
- **`sidePanel`** — to show the list of people waiting in Chrome's side panel.
- **`notifications`** — to show pop-ups when someone is waiting on your reply.
- **`offscreen`** — to play a short notification sound bundled with the
  Extension (Chrome's background service worker cannot play audio itself).
- **Host access to `https://slack.com/api/*`** — to call Slack's read-only API
  as described above. The Extension does not run on, read, or modify any
  websites you visit.

## Data sharing and selling

The Extension does not share, disclose, or sell any data to anyone. There are no
third-party services, SDKs, advertising, or analytics integrated into the
Extension. Data is not used for any purpose other than showing you who is
waiting on your reply, and is not used to determine creditworthiness or for
lending purposes.

## Data retention

The Extension retains only what it stores in your browser:

- **Tracked items** — while they are within the last 7 days. Items that fall
  out of that window, or no longer look like they need a reply, are removed on
  the next scan.
- **Message text** — only while "Show message text" is on; turning it off
  deletes it immediately.
- **Slack token and account reference** — until you disconnect Slack or remove
  the Extension.
- **Settings** — for as long as the Extension is installed.

Disconnecting Slack deletes its token and **everything tracked from it**.
Removing the Extension deletes all of its stored data. Because no personal data
is collected or transmitted to us, there is nothing else to retain or delete.

## Security

The Extension sends no data to us or to any third party, uses read-only access,
and requests the minimum permissions necessary to function. The only network
requests it makes are to the APIs of the apps you connect (currently Slack), and
your token is encrypted at rest on your device.

## Future features

Support for more apps (for example Gmail) and an on-device model for unclear
messages (using Chrome's built-in AI, which runs on your device) are planned.
Before any new app is read, you will be asked to connect it and shown what it
will read, and this policy will be updated to describe it.

## Children's privacy

The Extension is a productivity tool intended for general/professional use. It
does not knowingly collect any information from anyone, including children.

## Changes to this policy

This policy may be updated as the Extension evolves. Material changes will be
reflected by updating the "Last updated" date above. Continued use of the
Extension after an update constitutes acceptance of the revised policy.

## Contact

Questions about this policy or the Extension's privacy practices can be sent to:

**<bhargavtailor6@gmail.com>**
