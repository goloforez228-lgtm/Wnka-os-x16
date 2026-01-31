🖥️ Wnka-OSx16
Wnka-OSx16 is a lightweight x86 Real Mode operating system written entirely in assembly language (FASM). It is powered by the WNK Core (Wnka Netral Kernel) and focuses on low-level hardware interaction and retro-computing aesthetics.
🛠 Technical Specifications
Architecture: x16 Real Mode.
Kernel: Wnka Netral Kernel (WNK) v0.1.7g.
UI Engine: WSVU v0.3.0g (Wnka Simple Visual Unit).
Target: Floppy Disk Image (1.44MB).
Bootloader: Custom code starting at 0x7C00.


✨ Features
Security: Integrated login system (Default password: 123).
CLI Shell: Interactive command-line interface.
Hardware Probing:
Identifies CPU Vendor via CPUID.
Calculates Conventional RAM size.
Direct VGA palette manipulation for background colors.
System Control: Hardware-level reboot and ACPI-based shutdown (optimized for emulators).
Audio: PC-Speaker frequency modulation test.


⌨️ Command List
Command	Description
help	Lists all available system commands.
beep	Tests the PC-Speaker (sound check).
ver	Displays the system ASCII logo and version.
info	Shows detailed CPU, RAM, and Kernel info.
cls	Clears the terminal screen.
reboot	Performs a warm system reboot.
shut	Shuts down the machine (via QEMU/Bochs ports).


🚀 Build & Emulation
You will need FASM (Flat Assembler) to compile the project.
Compile:
bash
fasm boot.asm wnka_os.img

Run in QEMU:
bash
qemu-system-i386 -drive format=raw,file=wnka_os.img


📂 Project Structure
boot.asm — Main entry point, boot sector logic, and command router.
shell.asm — Data storage, ASCII art, and string definitions.
functions.asm — Core library (I/O, string comparison, hardware interrupts).


⚖️ License
(c) 2025 Wnka-soft. This project is provided "GNU-3.0 -- GPL-3.0".




🏗️ Regarding suffixes, the system has so-called suffixes that are associated with the version, for example: 0.1.1m
There are several of them - m, b, g, d.
The m suffix is ​​a minor update, but the version itself changes along with it. For example: 0.1.1m >> 0.1.2m
The b suffix is ​​a major update, but not very stable.
The version name also changes, for example: 0.1.1m >> 0.2.1b
The g suffix indicates a major but stable update, usually following b, but in rare cases it's released without a non-stable version (e.g., 0.2.1b >> 0.2.1g) or when the non-stable 0.2.1g update hasn't been released (there's no b release).
The final d suffix is ​​reserved for the developer and is released only after 15 days of the main release For m, b, and g versions, the version usually doesn't change during the early stages of development, and this version is only released at the last stage (without design) and the penultimate stage (without design, more bugs).
The version is named something like this: for example, 0.2.1d >> 0.2.2d or 0.2.1d (developer version without design and with bugs).
That's all for now.
