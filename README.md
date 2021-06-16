# Tecno Spark 7 Pro Rooting Guide

### Device info
---------------

* Device name: `Tecno Spark 7 Pro`
* hw_code: `0x707`
* Build ID: `KF8-H696ABFAlAm-R-GL-210419V1082`
* Chipset: `mt6769`

---------------

# The easy way

> You can easily check your `Build ID` from `CPU-Z` app or using adb: `adb getprop ro.build.display.id`

If you have the same device and `Build ID` as me then you can safely flash `boot_magisk_patched.img` from fastboot mode.

I wouldn't recommend this if your `Build ID` is different.

If the requirements stated above are met then proceed.

Steps:

* [Get ADB and FASTBOOT](https://forum.hovatek.com/thread-588.html).
* [Unlocked bootloader.](#Unlock-bootloader)
* Grab `boot_magisk_patched.img` from this repository.
* Reboot into fastboot mode from adb: `adb reboot bootloader`
* Finally flash the image: `fastboot flash boot boot_magisk_patched.img`
* Enjoy!

# The hard way

First of all I would like to thank the hovatek community, specially the admins who are always there ready to help along their vast amount of informative guides unlike most of the scammers out there. Without their help I likely never would have gotten my device rooted.

So if `The easy way` isn't in your favor then you gotta move in the hard path... _phew!_

Below are the steps, I need to warn you that this isn't for noobs.

If you're one of them then _step back._

_Proceed with caution, I am not responsible for any sort of **permanent** damage made to your device._

### Unlock bootloader

> Warning: Unlocking the bootloader will cause your device userdata to be wiped up.

Unlock developer options in your phone and enable `OEM Unlocking` in `developer options` before proceeding.

Then you should just simply follow [this guide](https://forum.hovatek.com/thread-19578.html) until rebooting into fastboot mode.

Later in fastboot you run this command: `fastboot flashing unlock`

### Bypass secure boot and dump the whole rom

* Make sure your phone charge is below 2%, yes I ain't joking. You device could get stuck in the preloader mode on failed attempts and since this is a non-removable battery device we can't do anything other than just waiting for the battery to drain up totally. Just remember not to panic if you mess up and wait patiently.

* Follow [this guide](https://forum.hovatek.com/thread-37957.html) until step 14.

* Follow [this guide](https://forum.hovatek.com/thread-21970.html) to dump your whole rom.

> Important notes to remember:
> * Before running `WwR_MTK_x.y.z.exe`, open `Template.init` inside `WwR` folder and add `MT6768` under `[CPU]` section.
> * Before attempting to readBack in SP_FLASH_TOOL, double-click on `preloader` item under `Download` tab and select `preloader_kf8_h696.bin` (Download from this repository)


### Flash empty vbmeta.img to get rid of dm-verity

Follow `Method 3` in [this guide](https://forum.hovatek.com/thread-32719.html).

### Patch boot.img from magisk and flash it

Follow [this guide](https://forum.hovatek.com/thread-21427.html)

And that's it!

I Hope this guide was able to save you some time and headache.

