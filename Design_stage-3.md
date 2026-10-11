# Stage 3: design direction

This is where the customization starts. I'm not going to give you click-by-click instructions here. Nova and Lawnchair are very granular, their menus change between versions, and a guide like that ends up as "tap here, here and here, and now you have 18 more steps." Instead, each tip says what to do and why. You know your launcher, so you adapt the tip to it.

## About the look

The look in this guide is a mix I chose by taste. The boot animation is the CyanogenMod 7 one, because it is far prettier than the generic animation from the Material era. The icons follow Lollipop. Everything else follows the same direction. It is not a faithful replica of any single version, and you can change any piece to match your own taste.

## How each tip is written

Every element has a goal (how it should look), a reason (what it borrows from the old Android), the values to copy, and where the setting usually lives, by section name and not by taps.

## Palette

Goal: white and light gray surfaces, dark text, and one accent color used sparingly.

Reason: old Material put color only where the action happens, so every screen is easy to scan.

Values:

- Accent: cyan, `#00BCD4`. This is my choice, inspired by the Cyanogen name. If you want something closer to the stock CyanogenMod apps, the ones I checked (the Eleven music player, for example) used a teal accent, `#009688`, on dark gray bars.
- Surfaces: white (`#FFFFFF`) for cards and the app drawer, light gray (`#F5F5F5`) behind them.
- Text: black at 87% opacity for main text and 54% for secondary text.
- Proportion: about 60% light surfaces, 30% text and icons, 10% accent.

Where: the accent or style setting of your LineageOS build (if it has one), and the highlight color in your launcher.

## Icons

Goal: icons exactly as drawn in the pack, with no circle or squircle mask on top.

Reason: packs from the Lollipop era were made before adaptive icons existed (Android 8.0). A modern launcher wraps every icon in a shape by default, which crops or reshapes the original artwork. Android 7.1 is the last version that didn't do this, so we copy its behavior.

Values:

- Icon pack: [AndroidLollipopIconPack.apk](https://sourceforge.net/projects/cyanogenmodder/files/AndroidLollipopIconPack.apk/download). Install it like any APK, then apply it from your launcher's icon settings.
- Nova Launcher: choose the Android 7.1 icon style. This turns off the automatic round shape.

<!-- TODO(snow): confirm the exact menu name of the 7.1 option in Nova, and the equivalent (or lack of one) in Lawnchair. -->

If the icons on your home screen don't match the pack's preview, a shape or normalization option is still on.

## Home screen, dock and app drawer

Goal: flat surfaces with square corners, and a white app drawer with white tabs.

Reason: old Material is built from flat sheets of paper with tiny corner radii (about 2dp for cards), not the big rounded shapes of modern Android. Square corners and white tabs are what make a drawer feel like Nougat.

Values:

- Corners: square, or as close to square as your launcher allows, on folders, the dock and the drawer.
- App drawer: white background, white tabs, and a grid that looks as close as you can get to the Nougat drawer on your screen.
- Home screen: keep the grid and the icon size consistent with the drawer, so the two don't look like different apps.

<!-- TODO(snow): add the exact grid (columns x rows) for home and drawer. -->

Where: in Nova, the Desktop, Dock, App & widget drawers and Folders sections hold all of this.

## Font

Goal: Roboto everywhere.

Reason: Roboto is the font of the Lollipop and Nougat era, and it matches the icon pack.

Where: LineageOS has a font option in its style settings, and the launcher has its own font setting for icon labels. Set both to Roboto so labels and system text agree.

## Live wallpaper

The live wallpaper I use with this setup is Wind: [Wind.apk](https://sourceforge.net/projects/cyanogenmodder/files/Wind.apk/download). Install it, then pick it from the wallpaper chooser.

A live wallpaper keeps drawing in the background, so it costs some battery. If that bothers you, keep a static wallpaper in the same accent color instead.

**Next: [Stage 4](System_stage-4.md).**
