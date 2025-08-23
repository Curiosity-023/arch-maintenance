# Arch Linux Standard Maintenance Checklist
Arch Linux Regular System Maintenance Checklist

Before you is an animatronic found in the back alley. We are unsure of it’s origins. It is your job to complete the maintenance checklist before claiming it as salvage. Or, if you choose to, you can throw it back into the alley where you found it, and forfeit payment.

Please make your choice now.

### ↺ | Backups and Sync
- **Check your home server automatic backup state and ensure no errors have occured and that all machines are up to date with each other.**
- This step is vital before progressing through with the maintenance checklist, as you do not want your system to break with important files going missing.

### ℹ | check for announcements from Arch
- Check the [arch linux homepage](https://archlinux.org/) for relevant announcements and important notifications, such as:
- updates that require human intervention and cannot be completed autonomously by pacman
- security related alerts (breaches etc)

### 🡅 | Upgrade system packages
```sudo pacman -Syu```
- reboot as soon as possible post to upgrading system packages
- If experiencing trouble after an update, double-check pacman's output by looking at `/var/log/pacman.log`

### 💁 | Check for orphans
```sudo pacman -Qtd```
- Remove appropriate packages

### 💾 | Check fs usage
- `dysk` to see a disk usage percentage. If disk is at an unexpected level (over 30% for laptops), proceed to:
- clear the package cache:
  ```paccache -r```
- use utilities such as Czkawka to scan and remove unneeded files
- uninstall any unused packages. check pacman's list of installed packages for this

### 🔧 | Old config files
- check for any unused or former config files as they may conflict with others in the future
- check the following directories:
- ~/.config/ -- where applications stores their configuration
- ~/.cache/ -- cache of some programs may grow in size
- ~/.local/share/ -- old files may be lying there
