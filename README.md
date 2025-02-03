
This repo shows you how to recover the acer nitro 5 an515-45 bios even if the laptop only turns on but the screen stays black.

[ BIOS Unlock - SREP Method ]

To access all the hidden menus of the BIOS without actually having to reflash it, you use a tool called SmokelessRuntimeEFIPatcher:

https://git.ngni.us/mirrors/SmokelessRuntimeEFIPatcher/releases

Download the release, extract the EFI directory to your usb stick formatted with FAT32. 

Get the SREP config for your laptop and extract it to your usb stick:r

https://github.com/Maxinator500/SREP-Patches

https://github.com/Maxinator500/SREP-Patches/blob/master/Configs/AA715-42(715-43)&AN515-45_Insyde_BiosUnlock.cfg

(there is another config for our model, but this one exposed more settings for me)

Boot from it. Wait a while. It will boot into the unlocked BIOS, your on board BIOS will not be touched.

Be careful though, many of the possible settings will cause your laptop to brick or even worse. I am not responsible for any damages.

[ Quick Tuning ]

Things that worked for me were enabling PBO and setting it's scalar to 4x - everything above would actually decrease performance for me.

There is a PCIE related setting that you can set from "Balanced-Low" to "Performance" which also seems to help things a bit.

Mostly i recommend doing the v102a VBIOS update that acer provides and getting the 1.06 BIOS which updates QBoost settings for your discrete NVidia Card, so it is allowed to run at 100Watts. Later BIOSes might provide this advantage aswell, i just haven't tried.

I have bricked my BIOS before with the following settings:

- Memory timings, Memory Frequency
- Manually keying in a fan profile
- Setting some iGPU setting to "UMA_Game_Optimized"

Please be careful.


[ BIOS Recovery - Crisis Recovery Method ]

If your BIOS is bricked, as in laptop turning on but screen stays black, you can use this method, which is also called "Crisis Recovery" by acer, to reflash your BIOS (which also resets any changes made in the settings)

First you need to create an usb stick, possibly a small one, formatted with FAT32.

Next you download the BIOS file of your choosing. A good source is here:

https://github.com/ny4rlk0/BIOS-ACER-NITRO-5-AN515-45

Unpack the download, rename the abobios.bin file into GH51Zx64.fd and put it on the usb stick.

Turn off the laptop in question, put in the usb stick, press fn+esc while you power it on. Release the power button, and after that release fn+esc.

The laptop should have turned on with fans running at full speed.

Within about 5 minutes it should have read and reprogrammed the bios from the stick.

Afterwards it will turn off on its own. You are now free to turn it back on, it should be working again.

---

I have assembled these infos here as it took me hours to get all this together and working.
