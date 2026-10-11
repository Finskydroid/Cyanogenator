# Stage 2: personalizing

The base is ready, so now we start changing how the phone looks and feels.

## 1. Changing the launcher

LineageOS comes with its own home screen launcher, Trebuchet, based on Android's Launcher3. It handles your home screen, app drawer and shortcuts. We'll replace it with Nova Launcher, which gives you far more control over the layout and appearance of your setup.

Download Nova Launcher from an official or otherwise trusted source and transfer the APK to your phone if necessary. Nova has offered paid premium features, so use the version available to you and decide whether the extras are worth paying for. Keep in mind that Nova is closed source. If you prefer a fully open source launcher, Lawnchair offers similar control, and everything in this guide that concerns the layout works the same way.

One important detail: setting Nova as your default launcher doesn't mean you should remove Trebuchet right away. Some system components may depend on the stock launcher, so keep it installed until you've tested Nova thoroughly, including after a reboot.

## 2. A little CyanogenMod nostalgia

Before we start rearranging icons and widgets, let's change something you'll see every time you turn on your phone: the boot animation. A boot animation is the sequence of images Android displays while the system starts. With a compatible Magisk module, you can replace the default one with the classic CyanogenMod 7 boot animation without manually modifying the system partition.

The module is here: https://sourceforge.net/projects/cyanogenmodder/files/CM7BOOTANIM.zip/download

To install it, open Magisk, go to Modules, choose Install from storage, and select the zip. Reboot to see the result. Depending on your device and the animation, startup might appear to take a little longer. That's a small price to pay for bringing back a bit of that old-school Android character ;)

Two precautions, since this is a zip from a third party:

- Open it on your computer before installing. A boot animation module should contain a `module.prop` and a `bootanimation.zip` and not much else.
- Know how to undo it before you install it. If the phone ever loops on the boot logo after a module, [Troubleshooting](Troubleshooting.md) shows how to remove modules without wiping anything.

Next: [Stage 3](Design_stage-3.md).
