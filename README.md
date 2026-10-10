# Cyanogenator
<img width="754" height="421" alt="image" src="https://github.com/user-attachments/assets/8df053c7-f059-414a-a110-b58d73e7682b" />

Transform your phone into the classic, nostalgic CyanogenMod experience; I’ve put together this "instruction manual" based on my own experience and knowledge regarding the topics and tools covered.

This guide is based on a specific version—though not one so obscure that you cannot easily replicate the setup. The most stable and tested version for this project is **LineageOS 19.1 GSI bvN (based on testing with the Samsung A31 4G, Brazilian variant, Android 12)**, which can be found in Andy Yan's SourceForge repository. While most people familiar with the Android world know this source, for those new to the scene, I will always provide the links at the end of the text.

Sourceforge repository mentioned: https://sourceforge.net/projects/andyyan-gsi/

See? That’s how it’s going to be from now on; always read to understand the exact destination of the link *;)*

Community contributions regarding compatibility and stability across specific versions and devices are important, as different architectures can be incompatible in various ways—such as screen resolution, software version, or partitioning. Always research your device to understand its specific characteristics; sometimes, a single digit can make all the difference, Another point concerns root access and system modification; certain steps in the tutorial require root access to work. One of these is essential for the modifications we need to make: Magisk with Zygisk enabled, and, of course, root access itself to add modules and gain precise control over this aspect of the device, **I am using Magisk version 30.7**, so I will be basing this on that version; any issues regarding the modules I list in the instructions can be resolved and examined by the community—as for me, I am providing technical explanations and a personal account.
