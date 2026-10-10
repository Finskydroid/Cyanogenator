# Stage 1: setting up the base

By now LineageOS should be running with root. This stage prepares everything the customization in [Stage 2](Personalize_stage-2.md) depends on.

## 1. Setting up LineageOS and first impressions

Once LineageOS is up and running, you'll be greeted by its initial setup. At some point it may offer to install Lineage Recovery. Stick with TWRP if you already have a compatible version installed and working. Recovery compatibility depends on your device and partition layout, so don't replace a working recovery without checking first.

After the setup, enable Developer Options and turn on USB debugging. We'll need it for some of the tools and modifications later. Connect the phone to your computer and run `adb devices`. If the phone shows up as authorized, you are good. If it doesn't, accept the prompt on the phone, and on Linux check your udev rules.

## 2. Getting Magisk ready

If Magisk is already installed, open it and check whether it needs additional setup. Depending on how you rooted your device, you may see a prompt to complete the installation. Follow it and reboot if required.

Once Magisk works, open its settings and enable Zygisk if your setup supports it, then reboot. Grant superuser access only to apps and tools that actually need it. Root is powerful, so don't hand out permissions blindly.

## 3. Installing LSPosed

LSPosed is a framework for running modules that modify aspects of Android. It is optional unless a later step in this guide says otherwise.

Before installing anything, check that the LSPosed build you pick is compatible with your Android version, your Magisk installation and your device architecture. The project has had forks, so look at which one is currently maintained instead of grabbing the first result. Download the module from the project's own page, install it through Magisk's Modules section, and reboot if instructed.

When the device starts again, check that LSPosed is active before you move on. If it doesn't show up or fails to initialize, troubleshoot that first instead of stacking more modifications on top of a broken setup.

## 4. A quick look at the visual side

Now we can finally get to the fun part.

Before installing launchers, icon packs and other customization tools, look at the appearance options already in your system. If your build supports accent-color customization, try a shade of blue as a starting point.

Don't aim for minimalism just because it's the default look of many modern Android interfaces. We're going for the character of classic Android, not another generic home screen with a wallpaper and a row of rounded icons.

Need help picking a palette? Any palette generator is a useful place to experiment with complementary colors, shades and accents. Choose a main color first, then build the rest of the interface around it. The goal isn't to make every element cyan; it's to make the colors feel like they belong together.

## Checkpoint

Before you go to Stage 2, check that all of this is true:

- The phone boots normally to LineageOS, and keeps doing it after a reboot.
- `adb devices` lists the phone as authorized.
- The Magisk app shows Magisk installed and Zygisk enabled.
- An app that asks for root gets it, and one you didn't approve doesn't.
- LSPosed shows as active, if you installed it.

If one of these fails, fix it now. Everything in Stage 2 assumes they all pass.

Next: [Stage 2](Personalize_stage-2.md).
