# Stage 4: system interface

Up to now we only changed the launcher and a few settings. This stage changes the system interface itself (the quick settings panel, sliders and the navigation bar), and it uses root. That makes it the riskiest stage so far, so go slowly: change one thing, reboot, check, and only then change the next. Keep [Troubleshooting](Troubleshooting.md) open in another tab.

## Before you start

- Stage 3 is done and `Checkpoint` passes.
- Root works and Zygisk is enabled.
- If you have TWRP, make a backup before this stage.

## 1. Iconify, with a neumorphic look

Iconify is an app that restyles the system interface through root overlays. Download the build used in this guide: [Iconify.apk](https://sourceforge.net/projects/cyanogenmodder/files/Iconify.apk/download). Iconify is an upstream project, so check its page for the Android versions it supports. It is mostly built around AOSP-style interfaces, and a GSI can behave a little differently from what its screenshots show. That is another reason to change one thing at a time.

Install the APK, open it, and grant root when Magisk asks. On first launch it sets itself up and may ask for a reboot, so do it.

Goal: soft, low-contrast surfaces that look raised or pressed in, with cyan only on the active state.

Reason: neumorphism is built from surfaces that share one background color and are separated by soft shadows, so it needs a light, quiet palette. The one in Stage 3 fits it.

Values:

- Quick settings tiles and sliders: choose the styles that look closest to raised and pressed-in surfaces.
- Active state: the cyan accent from Stage 3 (`#00BCD4`).
- Apply one style, reboot, and look at it before you apply the next.

<!-- TODO(snow): name the exact Iconify options (tile style, slider style, etc.) that give the neumorphic result. -->

## 2. Customized navigation bar

The navigation bar comes as a Magisk module: [Navbar.zip](https://sourceforge.net/projects/cyanogenmodder/files/Navbar.zip/download). It restyles the buttons of the navigation bar.

Before installing, open the zip on your computer. A module should contain a `module.prop` and a few resource files, nothing else. Then open Magisk, go to Modules, choose Install from storage, select the zip and reboot.

<!-- TODO(snow): one line on what the module changes (icons, spacing, colors) and which navigation mode it needs (3-button?). -->

If you also use navigation options inside Iconify, install one at a time. Two tools changing the same bar are the most likely cause of a broken navigation bar.

## If the interface breaks

If the navigation bar disappears, the status bar glitches or System UI keeps crashing after a change, undo the last change first. [Troubleshooting](Troubleshooting.md) explains how to disable the overlays or remove the module over ADB.

## Checkpoint

- The phone boots normally after each change.
- Quick settings tiles and sliders have the style you picked.
- The navigation bar works and looks the way you expect.
- You know which change you made last, in case you need to undo it.
