<h1 align="center">AltVerZ-Darwin</h1>

<p align="center"><b>PvZ2: AltVerZ 1.8.3f natively on iPhone, iPad and Mac.</b><br>No jailbreak, no JIT, no emulator.</p>

<p align="center">
The mod's Android code is converted ahead of time into ordinary, signed Apple code, so the game
runs the way any other app does: full screen, at your display's refresh rate, with sound, saves
and the mod's own content built in.
</p>

<p align="center">
  <a href="https://github.com/oenderg/AltverZ-Darwin/releases"><img alt="Latest release" src="https://img.shields.io/github/v/release/oenderg/AltverZ-Darwin?include_prereleases&label=latest&color=8a3ffc"></a>
  <a href="https://github.com/oenderg/AltverZ-Darwin/releases"><img alt="Downloads" src="https://img.shields.io/github/downloads/oenderg/AltverZ-Darwin/total?color=e0702c"></a>
  <img alt="Game version" src="https://img.shields.io/badge/PvZ2%20AltVerZ-1.8.3f-2ea44f">
  <img alt="iPhone and iPad" src="https://img.shields.io/badge/iOS%20%26%20iPadOS-15.5%2B-0a84ff?logo=apple&logoColor=white">
  <img alt="Mac" src="https://img.shields.io/badge/macOS-12%2B%20·%20Apple%20silicon-0a84ff?logo=apple&logoColor=white">
  <a href="https://github.com/oenderg/AltverZ-Darwin/stargazers"><img alt="Stars" src="https://img.shields.io/github/stars/oenderg/AltverZ-Darwin?style=social"></a>
</p>

<p align="center">
  <a href="https://github.com/oenderg/AltverZ-Darwin/releases"><b>Download</b></a> ·
  <a href="#features">Features</a> ·
  <a href="#install">Install guide</a> ·
  <a href="#build-it-yourself">Build it yourself</a> ·
  <a href="#how-it-works">How it works</a>
</p>

---

## This fork: cheats

This fork of [oenderg/AltverZ-Darwin](https://github.com/oenderg/AltverZ-Darwin) adds cheats to
PvZ2 AltVerZ 1.8.3f. The download and release links above are the original project's; this fork's own
builds come from its **Actions** tab (see below). Everything else works the same as upstream.

| Cheat | What it does |
|---|---|
| **Unlimited plant food** | Once the game has given you plant food in a level, a used one comes back a moment later. It never gives you plant food the game hasn't, so the first levels' tutorials still decide when you get it. |
| **Sun multiplier** (×2, ×3, ×4, ×5, ×10, ×20) | Every sun you collect is worth more: ×10 makes a 25 sun worth 250. The level's own sun limit still applies. |
| **Coin multiplier** (×2 to ×10) | Every silver, gold and diamond coin you collect on the lawn is worth more. Fake coins and level rewards are not changed. |
| **Gauntlet multiplier** (×2 to ×10) | The gauntlets (the zombie-hand currency) quests and Weekly Challenges give you are multiplied: ×10 turns a 3-gauntlet reward into 30. AltVerZ's gauntlets are the game's gems with a new picture, so gems you are given anywhere count too. |
| **Give gauntlets** (100, 1,000 or 10,000) | Adds that many gauntlets to your wallet once. On iPhone and iPad pick an amount in Settings and switch back to the game (it goes back to "Nothing" by itself); on the Mac press +100, +1,000 or +10,000. |

All of them are **off until you turn them on**, and a change applies while you play:

* **iPhone and iPad:** the iOS **Settings** app > **PvZ2 AltVerZ** (the page appears after the
  app's first launch). A change takes effect when you switch back to the game.
* **Mac:** Settings (`Cmd-,`) > General > Cheats.

**It is its own app.** This fork's builds use the app ID `io.github.pythagoras88.altverz-modded`, so they install
beside the original (`io.github.oenderg.altverz-darwin`) instead of replacing it, with their own saves on iPhone and
iPad. The downloads are named like `PvZ2-AltVerZ-modded-1.8.3f-Darwin-0.1.0.ipa`. What changed, and when, is in
[CHANGELOG.md](CHANGELOG.md).

They work through the game's own code: plant food is refilled with the game's own setter, and the
multipliers scale a collected item's value where the game reads it, so the counters, the sun cap
and the collection animation all agree. Nothing is written into your save directly. The details
and addresses are in [docs/GAME-NOTES.md](docs/GAME-NOTES.md#the-cheats).

### Building this fork

**Actions > Build > Run workflow**, on `main`:

* **APK link:** a direct, Google Drive or MEGA link to your own copy of the game's APK (the build
  checks that it is the exact supported version). Left empty, the workflow looks for an `.apk`
  attached to a *draft* release of this repository, which only you can see.
* **What to build / downloads:** e.g. iPhone/iPad and Slim.
* **Publish:** turn it **off** for a private test build. The `.ipa` is then kept on the run's page under **Artifacts** for 7 days (`PvZ2-AltVerZ-modded-<game>-Darwin-<version>.ipa`, not zipped).
* **Runner:** `macos-26` by default. If the job sits in the queue (GitHub sometimes has no Apple
  silicon Mac free), pick `macos-15-intel`, which builds the iPhone/iPad app.

Install the `.ipa` with AltStore or SideStore. The first launch of a Slim build downloads the game's
data.

> **Early build, expect bugs.**

## Features

* **A real app**
  * Full screen, with sound, saves and the mod's own content built in.
  * Leaving the app pauses the game; coming back shows its pause menu.
* **Unlocked frame rate**
  * The game runs at your display's refresh rate: 120 Hz on ProMotion displays.
  * Turn on **Target 60 FPS** in the game's own settings for that; with it off, the game runs at 60.
* **Touch, mouse and trackpad** work as on Android.
* **Keyboard** (Mac, and iPad with a keyboard)
  * `1`-`8` take a seed packet, `S` the shovel.
  * `Space` collects every sun, coin, gem, plant food and sprout drop on the lawn.
  * `F` toggles fast-forward, `Q` picks up plant food, and `Z`, `X`, `C` select the level's
    power-ups from left to right.
  * `Esc` pauses and resumes. The keys rest while the game is paused.
  * On the Mac, Settings (`Cmd-,`) lets you pick any keys.
* **Cheats** (off unless you turn them on)
  * **Unlimited plant food**: once the game has given you plant food, a used one comes back a moment later.
  * **Sun and coin multipliers**: every sun and coin (silver, gold and diamond) you collect on
    the lawn is worth more (sun ×10: 250 instead of 25), up to the game's own limits.
  * On the Mac they are in Settings (`Cmd-,`) > General; on iPhone and iPad in the Settings app,
    under the game's name.
* **Mac window**
  * Keeps the game's shape at any size, or, in Settings, adapts to any shape from 4:3 to 21:9.
  * Drawn at the sharpness of the display it is on; Settings can draw it sharper on a
    display that isn't Retina.
  * `Cmd-M` and `Cmd-H` pause the game.
* **Updates**
  * The Mac app updates itself: it checks once a day and asks before it installs
    (PvZ2 AltVerZ > Check for Updates…).
  * iPhone and iPad get updates through AltStore and SideStore with this repository's source.
  * Your saves stay, and a full app needs no second 1.1 GB download.

## Install

Every [release](https://github.com/oenderg/AltverZ-Darwin/releases) has two downloads for each
platform:

| File | What it is |
|---|---|
| `PvZ2-AltVerZ-modded-<game>-Darwin-<version>.ipa` | iPhone and iPad, slim (about 50 MB) |
| `PvZ2-AltVerZ-modded-<game>-Darwin-<version>-Full.ipa` | iPhone and iPad, with the game's data inside (about 1.1 GB) |
| `PvZ2-AltVerZ-modded-<game>-Darwin-<version>-Mac.dmg` | Mac, slim (about 55 MB) |
| `PvZ2-AltVerZ-modded-<game>-Darwin-<version>-Mac-Full.dmg` | Mac, with the game's data inside |

A slim app downloads the game's data (about 1.1 GB) the first time it opens and checks it, so keep
it open on Wi-Fi until the game starts.

**iPhone / iPad** (iOS 15.5 or later) - install the IPA with SideStore, AltStore, Sideloadly or
LiveContainer.

**AltStore / SideStore source** - add
`https://raw.githubusercontent.com/oenderg/AltverZ-Darwin/main/altstore/source.json`
(Sources → +) and install the game from it; new releases then show up as updates.

**Mac** (Apple silicon, macOS 12 or later) - open the DMG and drag the app onto Applications. The
app is not notarized, so the first time macOS refuses to open it: click **Done**, then in
**System Settings → Privacy & Security** click **Open Anyway**. After that the app updates itself.

Your saves live with the app (on the Mac, in `~/Library/Application Support/PvZ2 AltVerZ`).
AltVerZ has no Import/Export menu, so to bring a save over from Android, copy `pp.dat`,
`pp.dat.bak`, `local_profiles` and `global_save_data` from
`Android/data/com.ea.game.pvz2_auz/files/No_Backup/` on the phone into
`sdcard/Android/data/com.ea.game.pvz2_auz/files/No_Backup/` inside that folder (on iPhone and
iPad, inside **PvZ2 AltVerZ** → `data` in the Files app), with the app closed.

## Build it yourself

You need the **PvZ2 AltVerZ 1.8.3f** APK from the mod's official download. You don't need the
OBB: the build downloads it from the mod's own link by itself and checks it. To use your own
copy instead, pass it with `--obb` (or the workflow's OBB link).

### Option A - let GitHub build it (no Mac needed)

1. **Fork** this repository.
2. In your fork, open the **Actions** tab and enable workflows.
3. Pick **Build → Run workflow**, paste a link to the APK (a direct link, Google Drive or MEGA),
   and start it.
4. When it finishes (up to an hour), the apps are in your fork's **Releases**.

### Option B - build it on your Mac

Needs Xcode (with its iOS platform) and about 8 GB of free space.

```sh
git clone https://github.com/oenderg/AltverZ-Darwin
cd AltverZ-Darwin
./build.sh --profile altverz --apk "AltVerZ_1.8.3f.apk" --slim
```

The results land in `out/`. Add `--ios` or `--mac` to build just one of them; leave out `--slim`
for apps with the game's data inside (about 1.1 GB more).

## Known issues

* Early build: tested on the Mac, and only lightly on iPhone and iPad so far.

## How it works

The game's native libraries (`libPVZ2`, AltVerZ's `libSnowie` and their helpers) are translated
from Android's ELF format into Mach-O dylibs at build time, with the mod's 69 code hooks written
straight into the converted code. A small host - built on
[Husk](https://github.com/leviidev/husk) - provides what Android would have: the JNI calls the game
makes, its file system, OpenGL ES through ANGLE over Metal, audio, touch and keyboard input, and
the app's lifecycle.

| Folder | What is in it |
|---|---|
| `converter/` | ELF → Mach-O conversion and the hook bake |
| `runtime/` | the host: Android and JNI environment, graphics, audio, input, iOS and Mac apps |
| `data/` | the mod's recorded hook table, the game version it matches, and the mod profiles |
| `prebuilt/` | ANGLE for iOS and the iOS Simulator (rebuild with `REBUILD_ANGLE=1 ./build.sh …`) |
| `scripts/` | downloads, the disk image, the AltStore source, the Mac test runner |
| `docs/` | how it works, testing, the game's internals, releasing |

More in [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md).

## Contributing

Fixes and improvements are welcome. [CONTRIBUTING.md](CONTRIBUTING.md) has the build loop and what a
good pull request shows; [docs/TESTING.md](docs/TESTING.md) how to test on a Mac without touching your
own game; [docs/GAME-NOTES.md](docs/GAME-NOTES.md) what the game does that is not obvious. Coding
agents start at [AGENTS.md](AGENTS.md). Found a bug? Open an issue with the app's log.

## Thanks

The **AltVerZ** team for the mod, **Husk** for the translation layer this is built on, and
**ANGLE** (WebKit and Chromium) for OpenGL ES on Metal.
