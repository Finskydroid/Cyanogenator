# Cyanogenator
<img width="754" height="421" alt="image" src="https://github.com/user-attachments/assets/8df053c7-f059-414a-a110-b58d73e7682b" />

*Read this whole page before you follow any steps, so you know where this is going.*

Transform your phone into the classic, nostalgic CyanogenMod experience. I put this "instruction manual" together from my own experience with the tools and procedures it covers, and I explain how things work along the way, so you are not just copying commands blindly.

## About the look

The look is a mix I chose by taste, not a replica of any single CyanogenMod or Android version. The boot animation is CyanogenMod 7's, the icons follow Lollipop, and the rest follows the same direction. Change whatever you want to match your own taste.

## Reference setup

Everything here was tested on one specific combination. It is not so obscure that you cannot replicate it:

**Device: Samsung Galaxy A31 4G, Brazilian variant**

**Stock firmware: Android 12**

**ROM: LineageOS 19.1 GSI bvN (LineageOS 19.1 is based on Android 12L), from Andy Yan's SourceForge repository:** 
*https://sourceforge.net/projects/andyyan-gsi/*

**Root: Magisk 30.7 with Zygisk enabled**

**Recovery: TWRP, when a compatible build exists for your device**

This is the most stable and tested version for the project. Most people who know the Android scene already know that SourceForge page. For anyone new, I will always give the links, and you should always read where a link goes before you open it ;)

**How the guide is organized**

**Stage 0: preparing the phone and flashing the base system**

**Stage 1: setting up the base (Magisk, Zygisk, LSPosed, first visual direction)**

**Stage 2: personalizing (launcher and boot animation)**

**Stage 3: design direction (palette, icons, drawer, font, live wallpaper)**

**Stage 4: system interface (Iconify and the navigation bar)**

**Troubleshooting, for when something goes wrong. Read it before Stage 0, not after.**

If your phone already runs a GSI with root, you can skip Stage 0. If you have never flashed anything, read every stage in order.

Files used in this guide

Everything below is hosted in one SourceForge folder: https://sourceforge.net/projects/cyanogenmodder/files/

**CM7BOOTANIM.zip: CyanogenMod 7 boot animation, a Magisk module (Stage 2)**

**AndroidLollipopIconPack.apk: Lollipop-style icon pack (Stage 3)**

**Wind.apk: live wallpaper (Stage 3)**

**Iconify.apk: system interface customization (Stage 4)**

**Navbar.zip: customized navigation bar, a Magisk module (Stage 4)**

Some of these are APKs and modules from other projects, re-hosted here so the guide keeps working. Each stage links to its file, and you should always check the original project's page too.

Before you start
## Be honest with yourself about the risks:

Unlocking the bootloader wipes the phone. On Samsung it also trips Knox permanently. After that, Samsung Pay and Secure Folder stop working, and your warranty may be affected.
A wrong flash can leave the phone in a bootloop or bricked. Most of these cases are recoverable with stock firmware, but lost IMEI and modem data are not, unless you backed them up first.
Do not do this on your only phone.
Know your device

Community contributions are essential for improving compatibility and stability across devices and software versions. Android devices differ in screen resolution, Android version, hardware architecture and partition layout. Sometimes a single digit in a model number makes all the difference.

Research your device before following the instructions. Learn its specifics, check which modifications are compatible with it, and do not assume a procedure tested on one device works the same way on another.

## Root and system modification

Some steps require root. One of the key pieces of this setup is Magisk with Zygisk enabled, which lets us install modules and apply modifications that are otherwise unavailable. I am currently on Magisk 30.7, so the instructions and examples follow that version. Modules can behave differently depending on your device, Android version and configuration. If you hit a compatibility problem or find a better solution, tell me.

## Contributing

This project is my technical documentation of the tools, procedures and results I have personally worked with. I am sharing what I learned and leaving room for the community to test, troubleshoot, improve and expand it.

If you open an issue or a pull request, include your device model, Android version, ROM build and Magisk version. Without those, nobody can tell whether your result applies to anyone else.

Status

Stages 0 to 4 are written. The visual side keeps growing, and the next additions are sounds and the rest of the system apps.

License

GPL-3.0, see LICENSE.
