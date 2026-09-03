# Simple Ad Blocker (Chrome Extension)

A lightweight Manifest V3 Chrome extension that blocks common ad and tracker
domains using Chrome's built-in `declarativeNetRequest` API (no remote code,
no data collection).

## How to install it

1. Unzip this folder somewhere on your computer (e.g. `~/adblocker`).
2. Open Chrome and go to `chrome://extensions`.
3. Turn on **Developer mode** (toggle, top-right).
4. Click **Load unpacked** and select the `adblocker` folder.
5. The extension icon will appear in your toolbar — click it to see status
   and toggle blocking on/off.

## What it does

- Blocks network requests to ~30 well-known ad/tracker domains (Google ads
  and analytics, Facebook pixel, Criteo, Taboola, Outbrain, Amazon ads, etc.)
  defined in `rules.json`.
- Shows a live count of blocked requests on the extension badge.
- Lets you turn blocking fully on/off from the popup.

## Customizing the block list

Open `rules.json` and add more entries following the same pattern:

```json
{
  "id": 31,
  "priority": 1,
  "action": { "type": "block" },
  "condition": {
    "urlFilter": "||example-ad-domain.com^",
    "resourceTypes": ["script", "image", "sub_frame", "xmlhttprequest", "ping"]
  }
}
```

Each `id` must be unique. After editing, reload the extension from
`chrome://extensions` (click the refresh icon on the card).

## Limitations

- THERE IS NONE
