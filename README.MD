# RokieRemote Super-Simple-Roku-Remote-App-for-PC-Laptop-Window-Tablet
A Super Simple Roku Remote App for PC-Laptop-Window-Tablet.

A free Roku Remote Control app for PC, built as a replacement since the official Roku Remote app is no longer available in the Microsoft Store.

My goal is not to profit from it — simply to provide a free solution for people who need one. I've seen multiple posts from users asking for a Roku remote app for PC, which is what motivated me to build and share it in the first place.

---

## Features

### Device Discovery
- Auto-discovers Roku devices on your local network using SSDP on startup
- Falls back to mDNS (Zeroconf/AirPlay) if SSDP finds nothing
- When no live device is found, loads the last known device from a local cache so the UI remains useful while the TV is off

### Wake-on-LAN
- Sends a Magic Packet over UDP broadcast to wake a Roku TV from a powered-off state
- Automatically polls until the device comes online, then refreshes the device list and loads apps — no manual steps needed

### Remote Control
- Power on/off
- Home, Back
- D-pad navigation — Up, Down, Left, Right, Select
- Volume Up, Volume Down, Mute
- Play/Pause, Rewind, Fast Forward
- Instant Replay
- Options (Info)
- Channel Up / Channel Down

### Keyboard & Text Input
- Toggle an on-screen text box to type and send text to your Roku (great for search fields)
- Backspace is forwarded to the Roku as well

### Installed App Browser
- Fetches all installed apps and displays them as icon buttons in a scrollable panel
- Each icon uses the actual app artwork pulled from the Roku
- Hover over an icon to see the app name; click to launch it

### Device Caching
- Device info (name, IP, MAC address, network type) is saved locally after each discovery
- Cache is used to populate the device list and enable Wake-on-LAN even when the TV is offline

---

## Wake-on-LAN Setup

> **Note:** WoL requires the **"Fast TV Start"** setting to be turned **off**.

In my experience, Roku's SSDP-based device discovery on local networks can be unreliable. The "Fast TV Start" feature is intended to keep the device in a low-power standby mode so it can respond to SSDP multicast requests — however, over time the device may enter a deeper sleep state where it no longer responds to SSDP at all.

On the upside, disabling "Fast TV Start" can also help reduce power consumption and lower your electricity bill.

To turn off Fast TV Start: Home → Settings → System → Power

---

## Developer Mode

To enter Developer Mode on your Roku, press the following sequence on your physical remote:

🏠🏠🏠 &nbsp; ⬆️⬆️ &nbsp; ▶️◀️ &nbsp; ▶️◀️ &nbsp; ▶️


