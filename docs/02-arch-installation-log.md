# Arch Linux Installation Log

This document records the manual installation of Arch Linux, used as the ArchMedica server.
The goal of this installation was educational: to understand on a deep level how the operating system works below the user layer.

## Environment

- Platform: Virtual Machine
- Architecture: x86_64
- Boot mode: BIOS (Legacy)
- Installation method: Manual 
- Role: Server

## Documentation used

- Arch Linux installation guide - https://wiki.archlinux.org/title/Installation_guide (accessed Feb 5, 2026)
- Arch boot process - https://wiki.archlinux.org/title/Arch_boot_process#Boot_loader (accessed Feb 5, 2026)
- GRUB - https://wiki.archlinux.org/title/GRUB (accessed Feb 5, 2026)

## Installation Approach

The installation of ArchMedica server was performed following the documentation listed.
Archinstall was not used because the objective of this project is to learn about the OS.

## Disk Layout

The server layout was designed following the recommended layout according to Arch Linux Installation Guide.

/dev/sda1 - /swap
/dev/sda2 - /

## Base System Installation

Using pacstrap, the following essential packages were installed:
- base
- linux
- linux-firmware
- grub
- nano
- sudo
- NetworkManager

## Bootloader Configuration

GRUB was installed in BIOS mode targeting the main disk (MBR).
Special attention was required to correctly target the installation disk.

Initial issues were encountered due to incorrect comand input, and misunderstanding regarding the documentation.
All of the issues were resolved by revisiting documentation and validating device names.
 
## Networking

NetworkManager was installed and enabled to provide basic connectivity.
Network access was successfully verified after reboot.

## Errors Encountered

	### Issue: Partition without base system was mounted
	- Symptom: ls on /mnt shows only lost+found
	- Cause: partition was formatted and no essential packages were installed
	- Solution: Partition was formatted again to avoid issues and installing packages using pacstrap
	
	### Issue: Unable to mount the partition
	- Symptom: error "can't lookup blockdev /dev/sda2"
	- Cause: I was using the placeholder partition name listed in the arch installation guide
	- Solution: use the correct partition name

	### Issue: Unable to install GRUB
	- Symptom: error while installing grub "safety check can't be performed" and "more than one install device"
	- Casue: comand line was entered incorrectly, Num Lock was off the keyboard was not entering the numbers and it went back to the comand history.
	- Solution: Active num lock and enter the correct comand line.

	### Issue: Unable to access the system
	- Symptom: user root did not recognize the password
	- Cause: No root password was defined, no users were added
	- Solution: Going back to the live USB, mount the partition, change password, add a sudo user, update sudoers to allow wheel group to execute sudo
