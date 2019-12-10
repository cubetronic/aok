# AOK Linux for the XE303C12 Chromebook
Pronounced "A-okay"

![2019-12-08-143018_1366x768_scrot](https://user-images.githubusercontent.com/11820866/70398181-a080b100-19cd-11ea-82db-439739f46dbc.png)

## Instructions
0. Enable Developer Mode
1. Insert an SD Card or USB Drive
1. Download [The AOK Script](https://www.dropbox.com/s/ahhk0cvjjavfqi4/aok?dl=1 "Get it from Dropbox")
3. Press CTRL+ALT+T for a crosh window
4. Type `shell` and press enter
5. Type `sudo install -Dt /usr/local/bin ~/Downloads/aok` and press enter
6. Type `sudo aok` and press enter
7. Follow the instructions. (Reboot, Press CTRL-U, login, and type `setup` to set it all up!)

## What is this?
- A User-Friendly Linux Distro for certain ARMv7 laptops, based one Arch Linux ARM and Xfce.
- The **easiest** and **fastest** way to get a full Linux Distro on an old Chromebook.
- AOK Linux is a set of scripts with a few extra files. Packages are from archlinuxarm.org.

## Features
- Fully automated. Easy for a beginner.
- Mirror checking for improved 24/7 reliability.
- Pre-configured: 2D Graphics acceleration, Audio enabled, Caps Lock setup, WiFi hotspots compatible, etc.
- Clean Xfce environment with Firefox out of the box, ready to use.

## Supported Chromebooks
- Samsung XE303C12
- HP Chromebook 11 G1
- and more, see Wiki

## Requirements:
- A Chromebook: Sumsung XE303C12 or HP Chromebook 11 G1, or other
- Developer Mode enabled
- 4 GB or larger SD Card, or a Sandisk SDCZ430-032G USB Flash drive*. The final install size is 2.9 GB
- Internet (to download about 850 MB)

## How to Enable Developer Mode
1. Back up your files.
2. Turn off the Chromebook.
3. Hold down the **ESC** and **Refresh** keys and poke the **Power** button.
4. At the Recovery screen press **Ctrl-D** (there's no prompt - you have to know to do it).
5. Confirm switching to developer mode by pressing **Enter**, and the laptop will reboot and reset the system. This takes about 15-20 minutes.

Note: After enabling developer mode, you will need to press Ctrl-D each time you boot, or wait 30 seconds to continue booting.

Pro Tip: You can press Ctrl-D or Ctrl-U as soon as the backlight comes on. You don't have to wait for the white screen to appear.

## Post-Installation Tips
- To free up space (up to 500 MB), run Terminal Emulator and type `sudo pacman -Scc`
- To update the package list, run Terminal Emulator and type `sudo pacman -Sy`
- To install a program (package), run Terminal Emulator and type `sudo pacman -S thunderbird` for example
- For help using Arch Linux, visit https://wiki.archlinux.org/

## Notes

If you need to use a public Wi-Fi Hotspot with a Landing Page during setup, then see the WiFi Hotspot Help file in "extra".
Once the system is installed, Landing Pages will work automatically.

You may want to customize the scripts to use:
  - Your locale
  - Your own username
  - Your own hostname

You probably REALLY want to run the "pre-config" stuff!!!
The patch code get Arch Linux working nicely on the XE303C12.
Everything else is just normal Arch Linux install stuff.

If you want to copy files from ChromeOS, then after booting from SD/USB, only mount the eMMC read-only without loading the journaling system, for example:  
`sudo mount -o ro,noload /dev/mmcblk0p1 /mnt` Mounting the eMMC in any other way may cause Chrome OS to "repair itself" upon next boot, ERASING ALL USER DATA ON THE eMMC. If you want to copy files from AOK Linux to ChromeOS, then on ChromeOS do this:  
```
mkdir -p /usr/local/mount
sudo mount -o noload /dev/mmcblk1 /usr/local/mount
```
replace `mmcblk1` with `sda` for a USB or `sdb` for a second USB

It might be true that in rare cases, if the battery is discharged completely for a long period of time, the Chromebook boot system may not remember to allow you to boot from the SD Card. If Chrome OS is installed on the eMMC (internal memory), then it may "repair itself" and erase everything from the internal memory, and require logging in to Google's servers and starting as if from a new system, all before you can get back to developer mode and re-enable booting from the SD Card. This does not affect the integrity of the SD Card or your files on the SD Card.

## Thanks
The upstream source for this distribution comes to you from archlinuxarm.org.

https://archlinuxarm.org/platforms/armv7/samsung/samsung-chromebook
