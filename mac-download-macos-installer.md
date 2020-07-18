open "x-apple.systempreferences:com.apple.preferences.softwareupdate?installMajorOSVersion=10.15.6"

macOS catalina patcher - install catalina 10.15.x on unsupported mac
http://dosdude1.com/catalina/

[macos big surf 11 on unsupported Macs](https://parrotgeek.com/bigsur/)

- Open and install the 11.0b2 installer package normally onto your computer (this won't actually install the OS). You can delete it if you need the space back.
- Plug in the USB flash drive.
- Using Disk Utility, erase the flash drive and format it as "macOS Extended (Journaled)" with scheme "GUID Partition Map". If you can't see the scheme option,click View -> Show All Devices and select the whole disk (not the partition), then click Erase again.
- Open Terminal.
- Type sudo /Applications/Install\ macOS\ Big\ Sur\ Beta.app/Contents/Resources/createinstallmedia --volume, a space, and then drag in the flash drive from the desktop and press Enter.
- Type your administrator password (you won't see any dots) and press Enter.
- Follow the instructions, typing Y when asked.
- Extract "tool.zip" you downloaded earlier.
- Type xattr -c, a space, and then drag patch_installer.sh into terminal and press Enter.
- Type sudo, a space, and then drag patch_installer.sh into terminal again, then drag in the newly created installer partition, then press Enter.
- Eject your flash drive and boot it on the unsupported Mac (by holding the option key at boot and selecting it)
- Install macOS normally
- You're done!
