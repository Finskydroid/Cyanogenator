<img width="597" height="404" alt="image" src="https://github.com/user-attachments/assets/4ec7ef24-4e1e-4b08-b324-56c1e2e507a8" />
# Super Cyanify

**Super Cyanify** is a command-line tool developed for the Cyanogenator project. It provides a simple interface for 
checking device information, inspecting partitions and performing basic device operations through ADB.

The tool is designed around a terminal menu, with a straightforward list of commands. 
Its interface keeps things simple and makes the available operations easy to access

## Features

- **Device Info:** retrieves information about the connected Android device.
- **Partitions:** lists block devices and partition-related entries exposed through ADB.
- **Root Check:** checks whether root access is available.
- **Enter Recovery:** reboots the device into recovery mode.
- **Enter Download:** attempts to reboot the device into Download Mode.
- **Reboot:** restarts the connected device.
- **Exit:** closes the tool.

## Requirements

- A Linux environment with Bash.
- Android Debug Bridge (ADB) installed and available in **PATH**.
- An Android device connected through USB
- USB debugging enabled and the computer authorized on the device.
- Root access for operations that require it.

Some operations depend on the device, its Android build and the recovery or bootloader implementation. For example, 
rebooting into Download Mode may not work on every device. *always check compatibility! ;)*

## Usage

Clone or download the repository, then make the script executable:

```bash
chmod +x cyanconsole.sh
```

Run it with:

```bash
./cyanconsole.sh
```

If a particular operation requires elevated privileges, run the tool accordingly.

## Project status

Super Cyanify is still a simple tool under development. Its current focus is device inspection and basic ADB operations, 
with room for additional diagnostic features as the project evolves.

Super Cyanify is part of **Cyanogenator**, a project focused on bringing back the look and 
feel of classic Android through customization and related tools.
