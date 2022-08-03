<img src="assets/Qubes_OS_Logo.svg" alt="Qubes OS logo" style="width: 300px;" align="right">

# qubes-os-quickstarts
Qubes OS quickstarts

## Quicky
- `xfce4-appfinder --collapsed` - To quickly start application (run).
- `qvm-run -q -a --service -- sys-whonix qubes.StartApp+tor-control-panel` - For the tor control panel.

## Qubes Commands
- qvm-appmenus
- qvm-console-dispvm
- qvm-firewall
- qvm-move-to-vm
- qvm-remove
- qvm-start-gui
- qvm-template-postprocess
- qvm-backup
- qvm-copy
- qvm-get-image
- qvm-pause
- qvm-run
- qvm-sync-appmenus
- qvm-unpause
- qvm-backup-restore
- qvm-copy-to-vm - [How to copy from dom0](https://www.qubes-os.org/doc/how-to-copy-from-dom0/) - you can also copy from the dom0 without the gui: copy your data into `/var/run/qubes/qubes-clipboard.bin` then `echo -n dom0 > /var/run/qubes/qubes-clipboard.bin.source`.
- qvm-get-tinted-image
- qvm-pci
- qvm-service
- qvm-sync-clock
- qvm-usb - [How to use USB devices](https://www.qubes-os.org/doc/how-to-use-usb-devices/)
- qvm-block
- qvm-create
- qvm-kill
- qvm-pool
- qvm-shutdown
- qvm-tags
- qvm-volume
- qvm-check
- qvm-device
- qvm-ls
- qvm-pool-legacy
- qvm-start
- qvm-template
- qvm-xkill
- qvm-clone
- qvm-features
- qvm-move
- qvm-prefs
- qvm-start-daemon
- qvm-template-gui

## Commands for desktop application for managing Qubes OS
- Qubes Qube Manager: `/usr/bin/python3 /usr/bin/qubes-qube-manager`
- `qubes-backup`
- `qubes-backup-restore`
- `qubes-bug-report`
- `qubes-create`
- `qubesctl`
- `qubesd`
- `qubesdb-cmd`
- `qubesdb-list`
- `qubesdb-multiread`
- `qubesdb-read`
- `qubesdb-read-bool`
- `qubesdb-rm`
- `qubesdb-watch`
- `qubesdb-write`
- `qubes-dom0-update`
- `qubesd-query`
- `qubes-global-settings`
- `qubes-guid`
- `qubes-guivm-session`
- `qubes-hcl-report`
- `qubes-input-sender`
- `qubes-input-trigger`
- `qubes-log-viewer`
- `qubes-policy`
- `qubes-policy-admin`
- `qubes-prefs`
- `qubes-qube-manager`
- `qubes-template-manager`
- `qubes-template-manager`
- `qubes-update-gui`
- `qubes-vm-boot-from-device`
- `qubes-vm-clone`
- `qubes-vm-create`
- `qubes-vm-settings`

## qui
- `qui-clipboard`
- `qui-devices`
- `qui-diskspace`
- `qui-domains`
- `qui-updates`

> All the source code (Python 3) is found here: `/usr/lib/python3.8/site-packages/`
> On GitHub: https://github.com/QubesOS/qubes-desktop-linux-manager/

## Other to note
- `X -> /usr/bin/X-wrapper-qubes`
- `X-wrapper-qubes`

## XFCE4 Commands
- `xfce4-settings-manager` - "Control Panel"
- `startxfce4`
- `xfce4-about`
- `xfce4-accessibility-settings`
- `xfce4-appearance-settings`
- `xfce4-appfinder`
- `xfce4-color-settings`
- `xfce4-display-settings`
- `xfce4-find-cursor`
- `xfce4-keyboard-settings`
- `xfce4-mime-settings`
- `xfce4-mouse-settings`
- `xfce4-notifyd-config`
- `xfce4-panel`
- `xfce4-popup-applicationsmenu`
- `xfce4-popup-directorymenu`
- `xfce4-popup-places`
- `xfce4-popup-windowmenu`
- `xfce4-power-manager`
- `xfce4-power-manager-settings`
- `xfce4-screenshooter`
- `xfce4-sensors`
- `xfce4-session`
- `xfce4-session-logout`
- `xfce4-session-settings`
- `xfce4-settings-editor`
- `xfce4-settings-manager`
- `xfce4-taskmanager`
- `xfce4-terminal`
- `xfrun4 -> xfce4-appfinder`
### xfdesktop
- `xfdesktop`
- `xfdesktop-settings` - Managing the background image.
## xfwm4
- `xfwm4`
- `xfwm4-settings` - For managing the mdesktop menu (panel).
- `xfwm4-tweaks-settings`
- `xfwm4-workspace-settings` - Managing the workspace.

## Logs
- `/var/log/qubes` - The VMs logs are found here
- `/var/log/`
## Volumes in `/dev`
- `/dev/qubes_dom0` - Has all the volumes of the VMs
    - They seem to be all symlinks to `/dev/dm-*`
    - I am guessing that `root` and `swap` are the volumes for the dom0
    - When I use `file` command on the source of the symlink i get: `dm-55: block special (235/55)`
        - [Device file | Wikipedia](https://en.wikipedia.org/wiki/Device_file#Block_devices)
        - https://askubuntu.com/questions/166716/what-is-the-meaning-of-block-special
- [Mount LVM image](https://www.qubes-os.org/doc/mount-lvm-image/) - *You want to read your LVM image (e.g., there is a problem where you can’t start any VMs except dom0).*
- [Volume backup and revert](https://www.qubes-os.org/doc/volume-backup-revert/) - *With Qubes, it is possible to revert one of a VM’s storage volumes to a previous state using the automatic snapshot that is normally saved every time a VM is shutdown. (Note that this is a different, lower level activity than the [Backup, Restoration, and Migration](https://www.qubes-os.org/doc/backup-restore/) process.)*
- [Storage pools](https://www.qubes-os.org/doc/storage-pools/) - *Qubes OS R3.2 introduced the concept of storage drivers and pools. This feature was a first step towards a saner storage API, which is heavily rewritten in R4. See [here](https://dev.qubes-os.org/projects/core-admin/en/latest/qubes-storage.html) for documentation on storage pools in R4.*
- [qubes.storage – Qubes data storage](https://dev.qubes-os.org/projects/core-admin/en/latest/qubes-storage.html) - *Qubes provide extensible API for domains data storage. Each domain have multiple storage volumes, for different purposes. Each volume is provided by some storage pool. Qubes support different storage pool drivers, and it’s possible to register additional 3rd-party drivers.*

## Troubleshooting
### Restore VM
- Cause? No idea. It notice it removes many of the `qvm` commands in `/usr/bin`
- Solution: https://www.qubes-os.org/doc/volume-backup-revert/
    - `qvm-volume config vmname:private revisions_to_keep 4` - You might want to expand the *revisions_to_keep* because it will overwrite the previous version you had (that's why I put 4).
    - `:private` is for the data
    - `:root` is the system it self
- Step by step (change `private` to `root` for reverting the system files): 
    1. `qvm-volume info vmname:private`
    2. `qvm-volume config vmname:private revisions_to_keep 4`
    3. `qvm-volume revert vmname:private <revision>`
### Terminal access/exit
- To access the terminal (dom0): <kbd>Alt + Ctrl + F2</kbd>
- To exit the terminal (dom0): <kbd>Alt + Ctrl + F1</kbd>
### `qubes.xml` issues
This file contains details about each VMs.
- Located: `/var/lib/qubes/qubes.xml`
- Backups: `/var/lib/qubes/qubes.xml`
> If the `qubes.xml` file is empty you can copy one from the backups.
### Free some space on disk
- `sudo dnf clean all` - clears the cache of `yum`
- `/var/lib/qubes/appvms/` - You can delete the `.img` files (delete the `.img` of the less important VMs)
    - Clean up the rest: `qvm-remove <VMname>`
- Decrease the filesystem safety margin (5% by default): `sudo tune2fs -m 4 /dev/mapper/vg_dom0-lv_root`
- Another solution is to clear some of the logs: `/var/log` and/or `/var/log/qubes`
### Disk commands
- `pvs` - Display information about pgysical volumes
- `lvs` - Display information about logical volumes (you can see the volumes (backups too) of the different VMs)
- - [Secondary storage](https://www.qubes-os.org/doc/secondary-storage/) - *Suppose you have a fast but small primary SSD and a large but slow secondary HDD. You want to store a subset of your app qubes on the HDD.*
## TODO
- `/var/log/Xorg.0.log` - It seems there is an warning/error that keeps showing up
    - `[...] (EE) event7   - USB Optical Mouse: client bug: event processing lagging behind by 11ms, your system is too slow`
    - `[...] (EE) event4   - Wired USB Keyboard: client bug: event processing lagging behind by 11ms, your system is too slow`
