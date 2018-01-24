## How to install Nvidia driver on linux laptops
1. Boot the laptop with Live USB on Legacy Mode (set acpi=off, touch pad stops working after this)
2. sudo apt-get install nvidia-361
3. Remove acpi=off from /etc/default/grub
4. Reboot

__NOTE:__ Legacy mode is the key. if your BIOS supports optimus technology, turn it off
