<h1 align="center">
Twitch - Keep Tab Active
</h1>

Userscript for browsers that prevents Twitch from auto-pausing/muting or throttling playback when the tab is inactive.  
It fakes **visibility/focus**, guards **programmatic pauses** (only user-initiated pauses are allowed), keeps the player **“in view”** for observers, and sends light **activity pings** so streams keep playing.

Particularly useful for those who like to **farm Twitch Drops** or keep streams running in the background without interruptions.

## ✨ Features

- Keeps Twitch streams **playing in background tabs**
- Prevents **auto-pause** and **auto-mute** when switching tabs
- Fakes **visibility and focus** so Twitch thinks the tab is active
- Sends light **activity signals** to avoid idle timeouts

## 🚀 Installation

1. Install [Tampermonkey](https://www.tampermonkey.net/) (or another userscript manager).
2. Install the script from one of the mirrors:
   - [GreasyFork](https://...)
   - [OpenUserJS](https://...)
   - Or [install directly from this repository](./Twitch_-_Keep_Tab_Active.js).

## ⚙ How it works (high-level)

- Pretends the tab never goes background by spoofing visibility/focus APIs.
- Blocks Twitch’s internal events that detect when you switch tabs.
- Allows only **real user gestures** to pause playback — everything else is auto-resumed.
- Keeps the player “visible” to page observers.
- Periodically sends harmless activity signals to prevent idle triggers.
- Tries to use `navigator.wakeLock('screen')` when supported.

## ⚠️ Notes & Limitations

- This script is still in **version 0.3**, and while it works reliably for most cases, it may not yet cover **all edge situations** or browser variations. If you encounter a specific case where it doesn’t behave as expected — feel free to report it and share the details.
- Focuses purely on **client-side** behavior — it doesn’t bypass server-side throttling or ad systems.
- May behave differently with extensions that modify Twitch’s player or tab activity.
- Twitch frequently updates their SPA — if something breaks, please report it.
- Use responsibly and respect Twitch’s content policies.
