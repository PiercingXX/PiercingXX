# PiercingXX

> I bend Linux to my will so you don’t have to. Workstations, laptops, tablets, servers, phones — press the button, watch the chaos organize itself.

I prefer a simple, clean UI on a reproducible Linux ecosystem, with customizations that make sense and eliminate friction. Most of what's below runs on hardware I own and talks to my local‑first AI for the whole house.

---

## Current Projects

One engine and one game, each built for the other.

### Ferrite — the engine
**Ferrite** (under construction) — an AI‑agent‑native, editor‑first 3D game engine written entirely in Rust, targeting Linux, Windows and Android.

- **Agent‑native.** Humans and AI agents get the same capabilities: edit, play, test, see, build. Every editor feature is also an agent tool over MCP, with undo, staged review, and an audit log. All authored data is plain text.
- **Editor‑first.** Dockable editor, play‑in‑editor, content browser, prefabs, physically based renderer, animation graphs, code hot reload.
- **Built for deterministic sims.** Games that run their own lockstep, rollback, or server‑authoritative simulation get a supported bridge, not a workaround.
- **Generators are first‑class assets**, with reproducibility checks — the same way Direct Order 27's art is made.
- **Rust all the way down.** Engine, editor, tools, and gameplay. No scripting VM. wgpu (Vulkan / DX12), Rapier physics, Kira audio, an ECS core.

  The finish line is shipping Direct Order 27 on it.

### Direct Order 27 — the game
**Direct Order 27** (under construction) — a photorealistic hard sci‑fi FPS/RTS. Multiplayer only.

> In 2041 an automated alien mining ship arrived at Saturn and began stripping the solar system for elements to make an alloy nothing in nature makes. Humanity shot one hull down. Its escape pod landed on Earth, damaged, sought refuge in earths infrastructure and helped us destroy the rest. By 2161 that alloy is the most valuable thing in the solar system. There's a fixed amount of it, and the machines' masters are coming back. Four factions fight over the wrecks under Direct Order 27: collect all of it, by any means necessary. Every match is training for the war that's coming.

- **Command and fight at the same time.** Pilot your own hover tank, build a base, and give orders from the cockpit.
- **Four factions**, each with its own roster, history, and doctrine. Pilots fight in printed clones over a live link — run out of clones and you're out.
- **Netcode first.** Bit‑identical across operating systems, so replays are exact. 16 players by design, 32 on a dedicated host.
- **Rust at the core.** Simulation, netcode, and presentation are all Rust.
- **Hard science that grows.** Every capability has a mechanism someone could explain.
- **Original** Every shipped file is original from the ground up, fully written in rust. Any similarities to other concepts or ideas are by coincidence only.
- **Alpha Release** v0.1 will be in a few weeks. Currently built as a direct P2P for initial game play mechanics and netcode testing. Once stability is ensured and enough assets are built out Alpha v1 will be available on Steam.

---

## What I've built ⚙️

To get my setup the way I want it, I had to build:

- Reproducible Linux installers that turn “fresh ISO” into “daily driver”.
- Dotfiles that keep that machine mine — keyboard, WM, editor, the lot.
- An Android phone suite that looks and works like the Linux I actually want. Same family, same verbs. Android now; native Linux next.
- A Wayland shell for Linux phones, so the suite has somewhere to go.
- A local‑first AI assistant and coder on hardware I own.
- A federated local cloud network that keeps mission‑critical apps online across multiple business locations through maintenance, internet outages, and power cuts.
- A game engine capable of running the game I always wanted.
- A keyboard layout for every platform I touch.

Yes, it’s opinionated, but that is why it’s good.

---

## Linux 🐧

This is the backbone. A fresh ISO becomes a daily driver here.

### Installers
- **[linux-mod](https://github.com/PiercingXX/linux-mod)** — one installer for Arch, Artix, Debian/Ubuntu, Fedora, Void, openSUSE, and Alpine. Full workstation or mini (tablets, lean boxes). Menu‑driven (gum → fzf → whiptail). Resumable. Dry‑run. Distro differences live inside the module, not in a pile of forks.
	- Hyprland, Sway, i3, bspwm, Awesome, Qtile, DWM, herbstluftwm, GNOME, Cosmic
	- NVIDIA + CUDA, Microsoft Surface kernel, printers, gaming extras, Docker, Tailscale
	- Variants for workstations, servers, tablets, and phones
- Per‑distro trees I still keep: [Arch](https://github.com/PiercingXX/arch-mod), [Debian](https://github.com/PiercingXX/debian-mod), [FreeBSD](https://github.com/PiercingXX/freebsd-mod), plus mini for tablets ([arch-mini-mod](https://github.com/PiercingXX/arch-mini-mod), [debian-mini-mod](https://github.com/PiercingXX/debian-mini-mod))

### Dotfiles
- **[Piercing-Dots](https://github.com/PiercingXX/piercing-dots)** — one repo to keep the machine updated and configured. Hyprland is the daily. XX-WM is the tablet. The other WM configs are still in the tree.
	- Waybar, kitty, Neovim, Yazi, Tmux, GIMP — customized into minimal yet fully functional powerhouses
	- `Super+/` opens the Cheat Sheet; `Super+S` opens a bash‑driven settings menu — don’t leave the keyboard
	- System updates, package manager, audio, Wi‑Fi, Bluetooth, wallpaper, backup, users, mirrors, clean — from that menu

### Device enabling
Drivers and scripts for hardware that isn’t in the kernel — shipped with the installer:
- Surface kernel support
- NVIDIA + CUDA, assembled for a script, not a weekend
- NuVision 8" tablet Wi‑Fi/Bluetooth/Audio — obscure old tech that could be perfect if it was made with modern hardware
- KooTigers touchscreen/driver utilities — neat little toy that needed some help

---

## Phone 📱

The mobile market is overrun by two equally non‑valid options... then there are Linux phones, also not valid but for different reasons: way underdeveloped, many issues, and not enough financial backing to make it a viable market — *yet*.

So while we wait, my daily is a Pixel 9 Pro running GrapheneOS, and I've replaced the stock experience one app at a time.

> **All the Android apps are my daily drivers.**

**The store**
- **XX-Apps** (private) — the suite store. One login, one catalog, updates from the house Gitea forge. Not Play. Not F-Droid. Not Obtainium.

**On the phone**
- **[XX-Launcher](https://github.com/PiercingXX/XX-Launcher)** — text‑first Android launcher (Kotlin). No icons, no wallpaper clutter. Search‑first drawer, 8 home slots, inline folders, gestures, widgets, theme presets, JSON backup. The design ancestor of everything below.
- **[TxxT](https://github.com/PiercingXX/TxxT)** — SMS in the same style as the launcher, with a few extras to cut out the noise.
- **[XX-Dialer](https://github.com/PiercingXX/xx-dialer)** — pretty much the same as TxxT but for calls, with a ring policy attached: spam never rings, starred contacts always ring, everyone else rings only inside their allowed time window.
- **[XX-Contacts](https://github.com/PiercingXX/xx-contacts)** — a UI over the system address book. Not a second contact store, not CardDAV, not a dialer. Ring policy stays in XX-Dialer. No INTERNET.
- **[Nope-Mode](https://github.com/PiercingXX/Nope-Mode)** — selected apps go silent and un‑openable, on a schedule or on demand. Focus Mode for GrapheneOS, where Digital Wellbeing doesn't exist. Runs as device owner; no accounts, no network, no analytics.
- **[XX-Calculator](https://github.com/PiercingXX/xx-calculator)** — it's a calculator that matches my theme. BigDecimal engine, no Android dependencies in the math.
- **[XX-Email](https://github.com/PiercingXX/xx-email)** — Gmail without the proprietary Google blob. Tabs, snooze, undo‑send, operator search. No Play Services, no analytics.
- **[XX-Clock](https://github.com/PiercingXX/xx-clock)** — clock, alarms, timers, offline. Per‑alarm ringtones.
- **[XX-Weather](https://github.com/PiercingXX/xx-weather)** — ZIP in, forecast out. NWS first, Open-Meteo if NOAA is down. No location permission, no Play Services.
- **[XX-Files](https://github.com/PiercingXX/xx-files)** — a real directory tree (`File.listFiles()`), not MediaStore “Recent / Images / Downloads”. Per‑volume trash, 30‑day restore. No INTERNET.
- **[XX-Keyboard](https://github.com/PiercingXX/xx-keyboard)** — swipe‑first English keyboard with Colemak and Piercing layouts. Glide typing, no INTERNET permission, no proprietary Google blob.
- **[XX-Auth](https://github.com/PiercingXX/xx-auth)** — offline TOTP/HOTP. Secrets stay in the Android Keystore. Scan a QR or paste a URI. No network, no cloud account, no telemetry.
- **[XX-Camera](https://github.com/PiercingXX/xx-camera)** — Pixel‑class camera: AUTO, MANUAL, panorama/360. Writes JPEG/DNG/video on the phone. No INTERNET. The library is XX-Photos, not this APK.
- **[XX-Auto](https://github.com/PiercingXX/xx-auto)** — a driving screen for a phone in a mount. Big targets, black ground, gets out of the way. Now playing, thumb‑sized play/skip, opens XX-Maps, dials a favourite. Can launch itself when the car's Bluetooth connects. No INTERNET.

**Phone + server** — these have Linux server counterparts in the same repo.
- **[XX-Photos](https://github.com/PiercingXX/xx-photos)** — private photo library on hardware I own. Phone client plus FastAPI server. Timeline, backup, albums; tagging stays on the server.
- **[XX-Audiobook](https://github.com/PiercingXX/xx-audiobook)** — FastAPI server + Kotlin/Compose client. Audiobooks, ebooks, podcasts, RSS from my NAS. Not a storefront account.
- **[XX-Vitals](https://github.com/PiercingXX/xx-vitals)** — a cleanroom Google Fit replacement: entered on the phone, Postgres on my own NAS, no cloud anywhere.
- **[XX-Note](https://github.com/PiercingXX/xx-note)** — Keep's front end over a folder of Markdown files on my own NAS. Every note is one plain file with frontmatter. Delete the app and lose nothing.
- **[XX-Calendar](https://github.com/PiercingXX/xx-calendar)** — CalDAV. Shows you your day. That is the whole pitch. CalDAV backend included. DAVx⁵ is leftover if you still need Google invites.
- **[XX-Drive](https://github.com/PiercingXX/xx-drive)** — private cloud like Synology Drive, minus Synology. One Go binary on the NAS; native Android and Linux apps that look and work the same. Files stay files on disk. Not there yet.
- **XX-Maps** (private) — offline‑first navigation. Vector map from one local file, on‑device search and routing, turn‑by‑turn, all with airplane mode on. Online adds live traffic, a community hazard‑report network, and ALPR‑aware routing.
- **skpp‑radio** (private) — a local radio station. FastAPI server + Kotlin phone client. Listen on the phone, drive house speakers by zone, air spots on a schedule.
- **xx-chat** (private) — Mattermost‑wire compatible staff/group chat with AI agent tie‑in, event‑log spine, membership walls, agents‑as‑staff. Offline‑first; agents post through the same door people do.

One family theme, set once. They work alone or as a suite. XX-Maps, the store, radio, and chat stay private for now; everything installs through XX-Apps.

Tested on GrapheneOS (Pixel 9 Pro). Other Android builds should work but are untested. Any app that talks to a server needs Tailscale (or Headscale) — install it, point the app at your server. Done.

### Where it's all headed
- **[XX-WM](https://github.com/PiercingXX/XX-WM)** (under construction) — a minimalist Wayland shell for Linux phones and tablets. Text‑first, gesture‑driven, AMOLED black, Space Mono. No icon grids, anywhere. Calls, SMS, lock screen, notification shade — all first‑class surfaces. phoc today; Hyprland when the gestures catch up. Fairphone 5, Librem 5, Furi Phone FLX1. Python + GTK4. The Android suite above is the rehearsal; this is the venue.

---

## Local AI & self‑hosting 🤖

- **[XX-Stack](https://github.com/PiercingXX/xx-stack)** — let your local AI use every computer you own. Agent contracts, routing policy, an MCP server, and a local inference control plane over Tailscale. Cloud APIs are off unless you switch them on.
- **[free-opencode-hermes](https://github.com/PiercingXX/free-opencode-hermes)** — a local proxy so OpenCode (and Hermes-Agent) can run from the terminal against providers you already have keys for, or models on machines you own. Keys stay in the proxy, not in the agent.

---

## Odds & ends 🗃️

- **[piercing-keyboard-layout](https://github.com/PiercingXX/piercing-keyboard-layout)** — my own layout that no one else will ever use. One layout, every platform: Linux (xkb), Windows, Android/GrapheneOS, and QMK/Vial ortho boards.
- **xx-platform** (private) — ops console for the businesses under XX: scheduling, bookkeeping, documents, reminders. Next.js + Prisma + PostgreSQL.
- **piercingxx-branding** (private) — the brand system behind all of the above: color, type, logomark, and voice.
- **book-list** (private) — my ongoing attempt to separate the worthwhile from the well‑marketed nonsense.

---

## How I work 🧪

- **Local first:** my AI, my inference, my data, my hardware. Cloud is opt‑in or absent. If it can run on my hardware, it will... if it can't, buy more hardware.
- **Repeatable results:** a fresh install should feel like home in minutes. Scripts > screenshots, always.
- **Text‑first, gesture‑driven, low‑friction UX** — on a desktop, a phone, or a lock screen.
- **Elegant complexity:** hide the sharp edges, keep the power. Minimal dependencies, sane defaults, readable code, zero drama.
- **Defaults with a spine:** opinions included at no extra charge.

**Stack:** Rust for the engine and game · Kotlin + Jetpack Compose on Android · Python + GTK4/libadwaita + layer‑shell on Linux · FastAPI for house servers, Go when the binary *is* the product · POSIX Bash, gum / fzf / whiptail · Hyprland (GNOME on tablets, phoc on phones) · Kitty, Yazi, Neovim, tmux · Docker/Compose, NVIDIA + CUDA, SGLang, Wyoming/Home Assistant, Tailscale

---

## Contact 📮

Email: Don’t.

Open an issue in the relevant repo. If it’s a rant, make it entertaining.
