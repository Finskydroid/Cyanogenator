# Troubleshooting

Read this before Stage 0. When something breaks, you want to already know where to look.

The general rule: undo the last thing you changed before you try anything new. Stacking fixes on top of a broken setup makes it harder to know what actually caused the problem.

## The phone loops on the boot logo after installing a Magisk module

Modules live in `/data/adb/modules/`. Removing the module's folder removes the module.

- If you can reach ADB while it loops, run `adb wait-for-device shell magisk --remove-modules`. This removes all modules and reboots on its own.
- If ADB doesn't come up, boot into TWRP, open the file manager, go to `/data/adb/modules/`, and delete the folder of the module you installed last. If the folder looks empty or won't open, the data partition may still be encrypted and TWRP can't read it. How to get around that depends on your device, so search for your model.

Then reboot. Remember which module caused it, and don't install it again.

## The phone loops or hangs right after flashing the GSI

- Give the first boot at least ten minutes.
- Check that the image matches your architecture and partition layout. A wrong variant is the most common cause.
- Check that verified boot is disabled (the vbmeta step in Stage 0).
- Boot TWRP and format data again (Wipe → Format Data), then reboot. Old encryption keys cause loops more often than you'd expect.

## Magisk says it isn't installed, or root is gone

After flashing a GSI, the Magisk app from the stock system is gone and may need to be installed again. Reinstall the app, then check what it reports. If it says no root, patch the stock AP again, or on devices that keep Magisk in recovery, boot with the recovery key sequence for your model. If you flashed TWRP over a recovery that held Magisk, that is the cause.

## ADB doesn't see the phone

- Check that USB debugging is on and that you accepted the authorization prompt on the phone.
- Try another cable and another port. Many cables only charge.
- On Linux, install your distribution's Android udev rules package and reconnect. On Windows, install the Samsung USB driver.

## The IMEI is gone or the signal is dead

Restore the nvram, nvdata and protect backups you made in Stage 0. If you didn't make them, flashing the full stock firmware sometimes brings the signal back. If it doesn't, you need a service tool for your chipset, and that is why the backup is in step 0.

## Going back to stock

Flash the full stock firmware for your exact model and region with Odin: BL, AP, CP and CSC. Use the CSC file, not HOME_CSC, for a clean start. This removes root, TWRP and the GSI. It does not relock the bootloader, and it does not restore the Knox warranty bit.
