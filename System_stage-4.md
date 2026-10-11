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

## 3. Replacing the Stock Apps

We've taken care of the launcher's appearance and brought back a piece of CyanogenMod history. Now it's time to work on the functional side of the system.

LineageOS includes a collection of default apps, but we're not obligated to keep using all of them. For this stage, we'll replace several of those apps with independent, open-source alternatives. The goal is to find tools that fit the Cyanogenator's overall look and feel while remaining practical for everyday use.

Here are the apps we'll be using:

| Default function | Replacement |
|---|---|
| Phone / Dialer | **Amadz** |
| File manager | **Amaze File Manager** |
| Gallery | **Aves Libre** |
| Calculator | **CalcYou** |
| Clock | **Clock You** |
| App store | **F-Droid Classic** or **Aurora Store** |
| Web browser | **Lightning Browser** |
| YouTube client | **NewPipe** |
| Camera | **Open Camera** |

### A Few Things Before We Begin

Install and test each replacement before disabling its original counterpart. Some Android apps provide functionality that goes beyond their visible interface, and replacing an app doesn't necessarily replace every system component associated with it.

This is particularly important for the phone app, camera, and file picker. Keep the original system components enabled until you've confirmed that calls, camera access, file selection, and other relevant functions still work correctly.

A few notes about our choices:

- **Amadz** will be our alternative dialer. Test incoming and outgoing calls, SIM selection, and call notifications before changing the default phone app.
- **Amaze File Manager** handles everyday file management. Keep Android's system document picker enabled, since other apps may rely on it.
- **Aves Libre** will handle browsing and organizing your photos and videos.
- **CalcYou** replaces the standard calculator with an open-source alternative.
- **Clock You** provides the clock and alarm interface.
- **F-Droid Classic** and **Aurora Store** serve different purposes. F-Droid provides access to its own catalog of free and open-source apps, while Aurora Store is an unofficial client for the Google Play catalog. Aurora still depends on Google's servers, so choose according to what you need.
- **Lightning Browser** gives us an alternative to the default browser.
- **NewPipe** provides an alternative YouTube experience without requiring the official YouTube app.
- **Open Camera** replaces the camera interface for everyday photography, although some device-specific camera features may not be available.

Once everything is installed and tested, you can decide which original apps to leave in place and which ones you no longer need. There's no need to remove every stock app just for the sake of it.

The important part is that your phone starts feeling like a coherent, customized Android setup rather than a collection of unrelated apps.
