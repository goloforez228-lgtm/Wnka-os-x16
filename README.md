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
