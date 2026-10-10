You will need to flash LineageOS onto your phone—preferably a GSI, even if it doesn't make a huge difference. 
Most phones are compatible with Project Treble; check if yours is too. If you are uncomfortable with this sort of thing or have already flashed it, skip this step; 
it is intended solely for those who aren't very familiar with the open Android ecosystem.

1. Preparing Your Device

Before we can start customizing Android, we need to prepare the device to accept unofficial firmware and system modifications. This usually means unlocking the bootloader, 
obtaining root access, and installing a custom recovery when one is available and compatible with your device.

2. Unlocking the Bootloader

Start by enabling Developer Options. Open your phone's settings, find Build number, and tap it seven times. You'll unlock a new section in the settings menu.

Open Developer Options and look for OEM unlocking. If your device supports bootloader unlocking, enable it and follow the instructions specific to your model. On Samsung devices, unlocking the bootloader 
requires entering Download Mode and confirming the unlock. This process wipes your data, so back up anything you want to keep before proceeding.

Keep in mind that some devices and regional variants restrict bootloader unlocking entirely. Research your exact model before continuing.
Getting Root Access with Magisk

For this guide, we'll use Magisk to patch the stock firmware and obtain root access. The procedure described here 
is for compatible Samsung devices; other manufacturers may require a completely different approach.

First, download the stock firmware matching your exact device model and region. Firmware packages usually contain several files, including BL, AP, CP, and CSC. 
The one we'll need for Magisk is the AP file, typically named something like AP_[firmware-version].tar.md5.

Install the Magisk app, copy the AP file to your phone, and open Magisk. Select Install → Select and Patch a File, 
then choose the AP package. Magisk will generate a patched firmware archive.

Once the patching process finishes, transfer the resulting file back to your computer. Magisk's official documentation recommends 
using ADB to transfer the patched archive, as MTP can corrupt large files.

Next, use Odin to flash the patched firmware. Load the patched archive into the AP slot and follow the appropriate instructions for your device, 
including any required firmware components and reset procedures. Odin is Samsung-specific; Linux users may need a compatible alternative such as Heimdall, depending on device support.

Important: Flashing the patched archive is not, by itself, a universal guarantee that root access is ready to use. 
Some Samsung devices require additional setup or a particular recovery boot sequence. Follow the instructions for your exact model, then open Magisk and verify that the installation is complete.

3. Installing a Custom Recovery

A custom recovery such as TWRP can provide additional tools for installing firmware, managing partitions, and troubleshooting your device. However, 
not every device has a compatible recovery, and the installation process varies between models.

Check the official TWRP device list and download files only for your exact device variant. 
Some devices require additional preparation before TWRP can boot correctly, so don't assume that flashing a .tar file through Odin is all it takes.

For Samsung devices, Download Mode is commonly accessed by powering off the phone, connecting it to a computer with a USB cable while holding both volume buttons, and following the on-screen instructions. The exact procedure can vary by model.

If your device requires Odin, select the correct recovery package in the AP slot and follow the device-specific installation instructions. 
Some procedures require Auto Reboot to be disabled so that you can boot directly into recovery after flashing. Others differ, so check the instructions before proceeding.

4. Choosing Your Android Build

Now we're getting somewhere.

Download the LineageOS image you intend to use. If your device supports Project Treble, a compatible Generic System Image (GSI) may be an option. 
If it doesn't, look for a custom ROM built specifically for your device.

For this project, the main reference setup is LineageOS 19.1 GSI bvN, tested on the Brazilian Samsung Galaxy A31 4G variant. 
Your mileage may vary depending on your device, firmware, partition layout, and hardware support.

If none of these options are compatible with your device, stock ROMs are outside the scope of this guide. 
That doesn't mean you're out of luck, though — someone in the community might know a workaround. ;)
