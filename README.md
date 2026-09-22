<div align="center">

<img src="docs/icon.png" width="128" alt="Crisp icon">

# Crisp

**Every display control macOS hides, in one menu bar panel.**

Free, open-source external monitor control for macOS.<br>
Sharp HiDPI scaling, DDC brightness, presets and virtual displays.

[![Upstream release](https://img.shields.io/github/v/release/didriksg/Crisp?label=upstream%20release&color=2f81f7)](https://github.com/didriksg/Crisp/releases/latest)
[![macOS](https://img.shields.io/badge/macOS-14%2B-007AFF)](#requirements)
[![Swift](https://img.shields.io/badge/Swift-SwiftUI%20%2B%20AppKit-F05138?logo=swift&logoColor=white)](#building)
[![License: MIT](https://img.shields.io/badge/license-MIT-3fb950)](LICENSE)

**[Download for macOS](https://github.com/didriksg/Crisp/releases/latest/download/Crisp.dmg)** · **[Quick start](#quick-start)** · **[Documentation](#documentation)**

[Upstream releases](https://github.com/didriksg/Crisp/releases) · [Issues](https://github.com/didriksg/Crisp/issues) · [Website](https://crispmac.app/) · [中文](https://crispmac.app/zh.html)

</div>

---

Crisp is a free, open-source menu bar app for controlling displays on macOS. Adjust scaling, brightness, volume and color, save your desk setup as a preset, or automate display controls with `crispctl`. Built with Swift, SwiftUI and AppKit, with no Pro tier or license key.

This repository is the [Anywhere Music Player fork](https://github.com/Anywhere-Music-Player/Crisp) of [didriksg/Crisp](https://github.com/didriksg/Crisp). Downloads and Homebrew installation below use the upstream distribution; this fork does not currently publish its own releases. Source changes may differ from the latest packaged release.

Available in English and Simplified Chinese (简体中文).

<p align="center">
  <img src="docs/screenshot.png" width="360" alt="Crisp menu bar panel showing two displays, brightness sliders, system toggles and presets">
</p>

<details>
<summary>Watch the upstream demo</summary>

https://github.com/user-attachments/assets/90a62808-84d2-40d6-8563-0b282b9b4b6d

</details>

## Quick start

Requires **macOS 14 (Sonoma) or later**.

### Install

Using [Homebrew](https://formulae.brew.sh/cask/crisp):

```sh
brew install --cask crisp
```

Or download the upstream [`Crisp.dmg`](https://github.com/didriksg/Crisp/releases/latest/download/Crisp.dmg), open it and drag Crisp to Applications.

Installed from `didriksg/tap` earlier? `brew upgrade` moves you to the main cask by itself; `brew untap didriksg/tap` afterwards is optional cleanup.

### Use

1. Open Crisp from Applications and click its menu bar icon.
2. Adjust a display's brightness slider, or open its row to choose a resolution and other display settings.
3. Use **New Preset** to save a display configuration for later.

Hardware controls depend on the display and connection. See [Permissions](#permissions) for optional smooth scaling and brightness-key access, and [Automation](#automation) for command-line use.

## Features

| Control | What you can do |
| --- | --- |
| Scaling | Choose HiDPI resolutions and fine-tune the size of text and UI. |
| Brightness & volume | Adjust supported monitors over DDC, use software dimming, and route keyboard controls. |
| Display setup | Save presets, arrange screens, create virtual displays, and disconnect physical displays on Apple Silicon. |
| Color & HDR | Switch ICC profiles, adjust image settings, and use HDR or Extra Brightness on eligible displays. |
| Everyday tools | Toggle Dark Mode, Night Shift and True Tone; keep your Mac awake; automate with `crispctl`. |

<details>
<summary>Feature details and hardware limitations</summary>

- **Sharp, Retina-quality scaling on any display**: HiDPI scaled resolutions that make external monitors crisp instead of blurry or undersized, set up automatically for 1440p and larger displays, and always at the panel's full refresh rate (no more 1080p stuck at 50Hz on a 144Hz monitor)
- **Smooth scaling**: fine-tune how large everything looks in small steps, well beyond the handful of scaled sizes macOS offers; the flexible scaling people install BetterDisplay for
- **Brightness everywhere**: controls the real backlight of external monitors (DDC), dims via software on monitors that don't support that, and can keep dimming below the hardware minimum. Smooth fades, and brightness keys that follow the pointer, target all displays, or a chosen subset
- **Extra Brightness**: push XDR MacBook panels and HDR monitors past 100% by unlocking their HDR brightness reserve, up to the panel's full headroom (the feature BetterDisplay sells as brightness upscaling). One toggle per display, then the normal slider and brightness keys simply reach further. Sustained maximum brightness increases power draw, and real HDR video can look overblown while boosted
- **Volume**: control the built-in speaker volume of external monitors over DDC, with a slider per display and the keyboard volume/mute keys mapped to the monitor when it's your audio output. Shows only for monitors that support it, and can be hidden entirely from Settings
- **Presets**: save named display configurations (resolution, brightness, arrangement) with custom icons and colors, apply with one click, update in place. Image adjustment (gamma, color temperature, contrast) is per-display and not stored in presets
- **Display arrangement**: drag-to-arrange canvas, main display switching
- **Disconnect displays**: turn physical displays off and back on from the menu, remembered across sleep/wake (Apple Silicon)
- **System toggles**: Dark Mode, Night Shift, and True Tone, one click from the menu bar
- **Color**: ICC profile switching, XDR reference presets, HDR on/off per display, and image adjustment (gamma, contrast, gain, invert colors)
- **Virtual displays**: create HiDPI virtual screens
- **Extras**: combined brightness slider, auto brightness following the built-in display, a toggle for macOS's own ambient auto-brightness, keep awake, notch hiding, launch at login

</details>

## How does it compare?

BetterDisplay and Lunar are excellent, deeper tools. Crisp keeps the everyday essentials free: flexible HiDPI scaling, hardware brightness, presets, disconnecting displays, color adjustments, and auto-brightness sync. See the full side-by-side: [Crisp vs BetterDisplay, Lunar & MonitorControl](https://crispmac.app/crisp-vs-betterdisplay.html).

## Support upstream

The links below support the upstream maintainer and distribution.

Crisp is and will stay completely free. Its main running cost is the $99/year Apple Developer Program, Apple's fee for signing and notarizing the app so it installs cleanly. If you've found Crisp useful, or it saved you a BetterDisplay or Lunar license, and you'd like to chip in toward keeping Crisp signed and notarized, there's:

- [GitHub Sponsors](https://github.com/sponsors/didriksg)
- [Ko-fi](https://ko-fi.com/didriksg)
- [爱发电 (Afdian)](https://ifdian.net/a/didriksg)

Completely optional, but you'll have my heartfelt thanks.

### Sponsors

Thank you to the people chipping in toward keeping Crisp signed and notarized:

- **Arnor Ingthorsson** ([@arnor-ingthorsson](https://github.com/arnor-ingthorsson))
- **Barry** ([@BarryBarrywu](https://github.com/BarryBarrywu))
- **[@kuldipmaharjan](https://github.com/kuldipmaharjan)**
- **Volodymyr Dombrovskyi** ([@rebelvg](https://github.com/rebelvg))

## Requirements

- macOS 14 (Sonoma) or later; on macOS 26 the panel uses the native Liquid Glass backdrop

## Permissions

- **Administrator password** (one time, per monitor): needed only when you turn on smooth scaling, which installs a display override file into `/Library/Displays/Contents/Resources/Overrides` that macOS protects. Regular HiDPI scaling and everything else are password-free.
- **Accessibility** (System Settings > Privacy & Security > Accessibility): needed only if you turn on Brightness Keys, which routes the keyboard brightness keys to other displays (follow the pointer, all connected, or a chosen subset). Without it, everything else still works; the keys just control the built-in display as usual.

## Managed Macs

To keep Keep Awake off on company Macs, push a configuration profile for the `com.crisp.app` domain with `crisp.disableKeepAwake` set to `true`. Crisp reads it at launch and leaves the row out of Tools. A managed value outranks the user's own preferences, so it cannot be switched back on with `defaults write`.

## Automation

Crisp ships with `crispctl`, a command line tool for the same controls. It lives inside the app at `Crisp.app/Contents/MacOS/crispctl`; the Command Line Tool switch in Settings links it into `/usr/local/bin` after one admin prompt (off removes the link), and the Homebrew cask makes the same link on install. Source builds get it with:

```sh
xcodegen generate && xcodebuild -scheme crispctl -configuration Release
```

`crispctl help` prints the commands, and `crispctl display`, `crispctl brightness` or `crispctl hdr` one group with `--help` on any command for its details; point an agent at them before it does anything else.

```
Display commands:
  display list                              List displays as JSON
  display connect      <display>            Put a disconnected display back
  display disconnect   <display>            Take a display out of the layout
  display toggle       <display>            Disconnect if connected, connect if not

Brightness commands:
  brightness get       <display>            Read brightness and its live maximum
  brightness set       <display> <percent>  Set brightness
  brightness boost get <display>            Read Extra Brightness state
  brightness boost set <display> on|off     Switch Extra Brightness

HDR commands:
  hdr get              <display>            Read HDR state
  hdr set              <display> on|off     Switch HDR on an eligible external

Other commands:
  help                                      Show this help (also -h, --help)
  version                                   Show the Crisp version this tool ships with (also --version)
```

With Crisp running and the Command Line Tool enabled in Settings, try:

```sh
crispctl display list
display_uuid="PASTE-DISPLAY-UUID-HERE"
crispctl brightness get "$display_uuid"
crispctl brightness set "$display_uuid" 50
```

Replace `PASTE-DISPLAY-UUID-HERE` with a uuid returned by the first command.

`<display>` is a runtime id or a uuid from `display list`. Ids can change after an unplug or a wake; uuids do not, so scripts should prefer them.

`display list` reports each display's uuid, current resolution, logical `brightness`, logical `maxBrightness`, and brightness backend. The backend is Crisp's current route (`builtin`, `ddc`, `software`, or `unknown` while external DDC availability is undetermined); HDR software dimming reports `software`. Output is one JSON object per call.

Crisp must already be running; crispctl never launches it. `brightness set` accepts 0...100 normally. Values above 100 require Extra Brightness to be enabled and currently eligible for that display, and must not exceed its live `maxBrightness`; invalid boosted values are refused rather than clamped. A set is a manual change like using the slider and clears the active preset. The reply means Crisp accepted the request, not that the panel was read back; it is not retried automatically.

For example, `brightness boost get` returns `{"ok":true,"brightnessBoost":{"displayID":7,"eligible":true,"enabled":false}}`. `eligible` is the running Extra Brightness service's current eligibility result; `enabled` is its persisted per-display toggle state, so the two can differ while capability has collapsed and cleanup or auto-disable is pending. `brightness boost set` uses that existing service: `on` is refused when currently ineligible or when enabling fails, while `off` remains available for a connected display regardless of current eligibility. Enabling an external display may wait while the service settles HDR mode. Success means the service returned `true`, not that hardware, EDR headroom, or luminance was independently verified. A transport timeout does not prove the change was not applied; do not retry automatically—run `brightness boost get` first.

`display disconnect`, `connect` and `toggle` are the menu's Disconnect Display and Reconnect from a script, for a KVM desk or a button: Apple Silicon only, and a disconnect is refused when it would leave no active display. A display Crisp is holding disconnected is absent from every macOS display list, so `display list` still shows it with `connected:false` and its last-known id; use the uuid for it. Asking for the state a display is already in succeeds and changes nothing, and the reply comes after the window server has answered, which can take a few seconds.

`hdr get` and `hdr set` work on the external displays Crisp shows its HDR toggle for; the built-in panel and externals without HDR modes are refused. `get` reads the live state. `set` writes once through the same path as the toggle and reports success only when the read-back agrees; when it cannot tell (a timeout, or the display going away mid-way) it says so and does not retry, so run `hdr get` before retrying. Exit codes are unchanged.

## Documentation

- [Build and development guide](docs/BUILDING.md) — Command Line Tools builds and the edit–compile–run loop.
- [Design guide](docs/DESIGN.md) — panel architecture and UI conventions.
- [DDC notes](docs/ddc-notes.md) — monitor communication details.
- [Release guide](docs/RELEASING.md) — maintainer release workflow.
- [Fix a blurry external monitor](https://crispmac.app/fix-blurry-external-monitor-macos.html) — upstream setup guide.

## Building

For the Xcode workflow, use full Xcode with the macOS 26 SDK (the CI configuration uses macOS 26). The app's deployment target remains macOS 14.

```sh
git clone https://github.com/Anywhere-Music-Player/Crisp.git
cd Crisp
brew install xcodegen
make vendor        # fetches the pinned Sparkle framework
xcodegen generate   # generates Crisp.xcodeproj from project.yml
open Crisp.xcodeproj
```

For a distributable DMG (Command Line Tools only, no full Xcode) and the fast edit-compile-run dev loop, see [docs/BUILDING.md](docs/BUILDING.md).

## Contributing

For changes to this fork, [open a pull request](https://github.com/Anywhere-Music-Player/Crisp/pulls). For upstream bugs and feature requests, use the upstream links below. Include your macOS version, display model, connection type and reproduction steps when reporting a display issue.

Before submitting code changes, install `swiftlint` and `xcodegen`, then run `make check` with full Xcode. See the [development guide](docs/BUILDING.md#before-opening-a-pr) for details.

Issues and pull requests are welcome. Found a bug, want a feature, or have a display Crisp doesn't handle well? [Open an issue](https://github.com/didriksg/Crisp/issues) or start a [discussion](https://github.com/didriksg/Crisp/discussions). PRs are just as welcome, whether it's a fix, a feature, or a new translation.

## Origin

Crisp began as a fork of [FreeDisplay](https://github.com/huberdf/FreeDisplay) and has since been substantially rewritten: a custom panel architecture, native controls throughout, a reworked brightness pipeline, and a full redesign. Thanks to FreeDisplay for the foundation and the spirit: free display management for everyone.

## License

[MIT](LICENSE). Portions derived from FreeDisplay remain available under its MIT terms, reproduced in [ACKNOWLEDGMENTS.md](ACKNOWLEDGMENTS.md).
