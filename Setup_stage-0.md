# Stage 0: preparing the phone and flashing the base system

You will need to flash LineageOS onto your phone, preferably as a GSI (Generic System Image), even if it doesn't make a huge difference. Most phones are compatible with Project Treble, so check if yours is too. If you have already flashed a GSI and have root, skip to [Stage 1](Create_stage-1.md). This stage is for people who aren't very familiar with the open Android ecosystem, so read it slowly.

## 0. Before you touch anything

Do these first. Every one of them is annoying to discover afterwards.

- Write down your exact model number and region (Settings → About phone). Firmware, recovery and GSI choices all depend on it.
- Install an app like Treble Info and check three things: that Treble is supported, the architecture (usually arm64), and the partition layout (A-only or A/B, and whether the device uses dynamic partitions). These decide which GSI image you download. Dynamic partitions can also be checked over ADB with `adb shell getprop ro.boot.dynamic_partitions`.
- Back up your data. The next step wipes the phone.
- Back up your IMEI and modem data. On MediaTek devices, such as the A31, that usually means the nvram, nvdata and protect partitions. Research a backup method that works for your chipset and model, because losing the IMEI can leave you without a signal and it is hard to undo.
- Charge the battery above 50%, use a good cable, and download the stock firmware for your exact model and region now, in case you need it for recovery later.

## 1. Unlocking the bootloader

Start by enabling Developer Options. Open Settings, find Build number and tap it seven times. A new section appears in the menu.

Open Developer Options and look for OEM unlocking. If your device supports bootloader unlocking, enable it and follow the instructions for your model. On Samsung, unlocking means entering Download Mode and confirming the unlock there. This wipes your data.

Two things catch people out:

- On some Samsung devices the OEM unlocking toggle is missing or greyed out, usually for a while after the first setup. Connecting to Wi-Fi with an account signed in and waiting (it can take up to 7 days) is the usual way out. Check what applies to your model.
- Unlocking trips Knox permanently. It cannot be reverted, so decide before you confirm.

Keep in mind that some devices and regional variants restrict bootloader unlocking entirely. Research your exact model before continuing.

## 2. Getting root with Magisk

For this guide we use Magisk to patch the stock firmware and obtain root. The procedure below is for compatible Samsung devices. Other manufacturers may need a completely different approach. Magisk's own [installation page](https://topjohnwu.github.io/Magisk/install.html) has a Samsung section, so read it too.

First, download the stock firmware that matches your exact model and region. The package contains several files: BL, AP, CP and CSC. The one we need for Magisk is AP, typically named something like `AP_[firmware-version].tar.md5`.

Install the Magisk app and copy the AP file to your phone. Open Magisk and select Install → Select and Patch a File, then choose the AP package. Magisk generates a patched archive.

When the patching finishes, bring the result back to your computer. Magisk's documentation recommends ADB for this (`adb pull`), because MTP can corrupt large files.

Then flash with Odin. Put the patched archive in the AP slot and load the matching BL and CP files. For CSC, use the CSC file, not HOME_CSC, so the phone does a clean factory reset. Odin is Samsung-specific and runs on Windows. On Linux, Heimdall has poor support for newer Samsung devices, and people usually report better luck with alternatives such as Odin4 or Thor. Test whatever you pick before you rely on it.

Important: flashing the patched archive is not, by itself, a guarantee that root is ready to use. Some Samsung devices keep Magisk in the recovery partition instead of boot, and they need a specific recovery boot sequence to start with root. If the Magisk app offers a Recovery Mode option when patching, your device is probably one of those. Follow the instructions for your exact model, then open Magisk and check that the installation is complete.

## 3. Installing a custom recovery

A custom recovery such as TWRP gives you tools to install firmware, manage partitions and troubleshoot. Not every device has a compatible recovery, and the process varies between models.

Check the official TWRP device list at https://twrp.me/Devices/ and download files only for your exact device variant. Some devices need extra preparation before TWRP can boot correctly, so do not assume that flashing a `.tar` through Odin is all it takes.

On Samsung, Download Mode is usually reached by powering off, connecting the phone to a computer by USB while holding both volume buttons, and following the on-screen instructions. The exact procedure can vary by model.

If your device needs Odin, select the recovery package in the AP slot and follow the device-specific instructions. Some procedures require Auto Reboot to be disabled so that you can boot straight into recovery after flashing. Others differ, so check before you proceed.

One conflict to watch for: if Magisk lives in your recovery partition (see the previous step), flashing TWRP over it removes Magisk. In that case, install Magisk again after TWRP, and confirm root before you go on.

## 4. Choosing your Android build

Now we're getting somewhere.

Download the LineageOS image you intend to use. If your device supports Project Treble, a compatible GSI may be an option. If it doesn't, look for a custom ROM built specifically for your device.

For this project, the reference setup is LineageOS 19.1 GSI bvN, tested on the Brazilian Samsung Galaxy A31 4G. The letters at the end of a GSI's file name describe the build variant, so read the notes in the SourceForge folder to confirm that the one you pick matches your architecture and partition layout. Your mileage may vary depending on your device, firmware and hardware support.

If none of these options is compatible with your device, stock ROMs are outside the scope of this guide. That doesn't mean you're out of luck, though. Someone in the community might know a workaround ;)

## 5. Flashing the GSI

This is the step that replaces the stock system. Read all of it before you start.

1. Decompress the image. GSIs download as `.img.xz`. On Linux, `unxz name.img.xz` gives you `name.img`. On Windows, 7-Zip does the same.
2. Disable verified boot. Samsung's stock AP includes a `vbmeta` image, and a GSI will not boot with verification enabled. You need a vbmeta with verification disabled, flashed through Odin (packed as a `.tar`) or, on devices that support it, through fastboot with `fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img`.
3. Boot into TWRP and format data: Wipe → Format Data, then type `yes`. This erases everything and clears the old encryption.
4. Flash the system image. In TWRP, go to Install → Install Image, pick the `.img` and choose the System partition.
5. Reboot to system. The first boot takes longer than normal, so give it a few minutes.
6. Open the Magisk app again. The system changed, so the app from the stock install is gone. Reinstall it, then check that root still works. If it doesn't, patch and flash again before you continue.

If your device uses dynamic partitions, the system partition is not flashed like a normal partition, and TWRP may not handle it. In that case the usual route is fastbootd: reboot with `adb reboot fastboot`, then `fastboot flash system name.img`. Confirm that this works on your model before you wipe anything.

## 6. First boot

When the phone boots into LineageOS, Stage 0 is done. If it sits on the boot logo for more than about ten minutes, or restarts in a loop, go to [Troubleshooting](Troubleshooting.md).

Next: [Stage 1](Create_stage-1.md).
