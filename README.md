# Cyanogenator

<img width="754" height="421" alt="Cyanogenator interface preview" src="https://github.com/user-attachments/assets/8df053c7-f059-414a-a110-b58d73e7682b" />

Read the full guide before following any of the instructions. Some steps depend on earlier modifications, and skipping them without understanding the setup can cause problems.

Cyanogenator is a collection of instructions, tools and customizations for recreating the look and feel of classic Android, with CyanogenMod as its main reference. The guide documents the procedures I have tested, the tools involved and the configuration used during development.

It is a customization project, not a custom ROM. The instructions use an existing Android system as their base.

Contact?
Discord: https://discord.gg/39aUekNR6Z

## Design

The visual style combines elements from different Android generations. The boot animation comes from CyanogenMod 7, the icon style follows Lollipop, and the rest of the interface is customized around that direction.

The setup is not intended to reproduce a specific CyanogenMod release exactly. Individual elements can be replaced to suit your preferences.

## Reference setup

The procedures were tested primarily on the following configuration:

- **Device:** Samsung Galaxy A31 4G, Brazilian variant
- **Stock firmware:** Android 12
- **ROM:** LineageOS 19.1 GSI, arm64 bvN, from Andy Yan's SourceForge repository
- **Root:** Magisk 30.7 with Zygisk enabled
- **Recovery:** TWRP, where a compatible build is available

LineageOS 19.1 is based on Android 12. The reference GSI is available from [Andy Yan's SourceForge repository](https://sourceforge.net/projects/andyyan-gsi/).

Other devices, GSIs and custom ROMs may work, but compatibility depends on the device, Android version, partition layout and available modifications. The reference setup is the environment used to test the instructions, not a guarantee that every step will work elsewhere.

## Guide structure

The documentation is divided into stages. Follow them in order unless you already have the required setup.

- **Stage 0 — Setup:** prepare the device and flash the base system.
- **Stage 1 — Base configuration:** configure Magisk, Zygisk and LSPosed, and establish the initial customization setup.
- **Stage 2 — Personalization:** configure the launcher and boot animation.
- **Stage 3 — Design:** apply the color palette, icons, app drawer, font and live wallpaper.
- **Stage 4 — System interface:** configure Iconify and the navigation bar.
- **Troubleshooting:** consult this section before starting Stage 0 and whenever a procedure fails.

If your device already runs a compatible GSI with root access, some of Stage 0 may not be necessary. Check the prerequisites of each stage before skipping any steps.

## Files

The files used by the guide are hosted in the [Cyanogenator files directory on SourceForge](https://sourceforge.net/projects/cyanogenmodder/files/).

| File | Purpose |
|---|---|
| `CM7BOOTANIM.zip` | CyanogenMod 7 boot animation, installed as a Magisk module |
| `AndroidLollipopIconPack.apk` | Lollipop-style icon pack |
| `Wind.apk` | Live wallpaper |
| `Iconify.apk` | System interface customization |
| `Navbar.zip` | Customized navigation bar, installed as a Magisk module |

Some files originate from other projects and are hosted here for use with the guide. Check the original project's documentation and compatibility information before installing them. Refer to the relevant stage for the instructions associated with each file.

## Before you start

### Risks

Unlocking the bootloader usually erases user data. On Samsung devices, it can permanently trip Knox, affecting features such as Secure Folder and Samsung Pay. Warranty implications depend on the device and applicable terms.

Incorrect images, incompatible modules or interrupted flashing procedures can leave the device unable to boot. Some problems can be resolved by restoring stock firmware, but this is not guaranteed. Damage to or loss of important data, including modem-related data, can be difficult or impossible to recover.

Back up your data before making changes. Do not rely on this guide as your only recovery plan, especially if the device is your primary phone.

### Device compatibility

Android devices differ in hardware, screen resolution, system version, partition layout and bootloader behavior. Even devices from the same product family can require different procedures.

Check the exact model number and research the compatibility of each modification before applying it. A procedure tested on the reference device may behave differently on another device.

### Root and system modifications

Some steps require root access. The reference setup uses Magisk 30.7 with Zygisk enabled to support modules and modifications that require elevated privileges.

Module compatibility depends on the Android version, device and system configuration. Do not assume that a module working on the reference setup will work on every GSI or custom ROM.

If you encounter a problem, document the device model, Android version, ROM build, Magisk version and the steps that led to the issue.

## Tools

Cyanogenator includes documentation for related tools used during the customization process.

### DroidSky

DroidSky is a manager for the Cyanogenator customization project. It is still in an early stage and currently has a limited feature set. Its interface draws inspiration from TWRP, ClockworkMod Recovery (CWM) and the classic Holo UI.

DroidSky follows the old Android tradition of dessert-themed release codenames. Version `0.1` is named **Alfajor**.

### SUCy — Super Cyanify

SUCy is a Bash-based command-line tool for Android device inspection and basic operations through ADB. Its current menu includes device information, partition listing, root checking, rebooting into Recovery or Download Mode, and normal reboot.

The tool is still under development. Available operations depend on the connected device, its Android build and the permissions provided by the system. Consult the included manual before using the commands, especially those that restart the device.

## Contributing

The guide documents procedures and configurations I have worked with directly. Device-specific testing and corrections from other users can help extend compatibility beyond the reference setup.

When reporting an issue or submitting a pull request, include the device model, Android version, ROM build, Magisk version and the relevant steps. Include command output or logs when they help explain the problem.

Do not assume that a result on one device applies to another without testing.

## Status

Stages 0 through 4 are documented. The customization is still evolving, with further work planned for system sounds and additional system applications.

DroidSky and SUCy are also under development and may change as their features and documentation are expanded.

## License

This project is licensed under **GPL-3.0**. See the `LICENSE` file for details.
