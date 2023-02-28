# Linux on the CHUWI CoreBox 4th

> :grey_exclamation: This text reflects my personal experience with a single machine.  

## General remarks

- The case has a high-quality feel.
- All ports are located on the back of the case
- The fan produces a perceptible noise even on no / low load.
- The BIOS feels very quirky.
- There seems to be no official source for (windows) drivers or even BIOS updates. So if you have to reinstall Windows from scratch, you might have a problem.
- Its easy to open the case, its just four screws at the bottom of the housing. The only serviceable part seems to be the NVMe SSD.

## Installing Linux on the CHUWI CoreBox 4th

This was tested with Ubuntu 22.10. Main problem was the BIOS giving me a hard time to boot anything but the default Windows installation. The BIOS seems to have problems to properly power-up all peripherals in-time, especially bootable USB-devices.

| Problem  | Solution |
| ------------- | ------------- |
| Enter BIOS    | Press `F2` button during on powerup |
| BIOS does not recognize bootable USB sticks  | Use a self-powered USB hub in-between corebox and USB stick  |
| After successfully booting from USB stick and removing it again, corebox does not boot at all, anymore | Once the USB stick was recognized as bootable media, the corebox seems to reject to boot without it. Its even not possible to enter BIOS setup. So attach the USB stick again (remember self-powered USB hub), power up again, enter the BIOS, and **disable** boot from USB   |

After getting the box to boot from USB, further Linux installation was no problem at all. Just remember to disable boot from USB afterwards.

## Working with Linux on the CHUWI CoreBox 4th

As far as tested, Ubuntu 22.10 works perfectly on the CHUWI CoreBox 4th.
- System reliable enters and leaves standby.
- LAN and Wake-on LAN works.
- Bluetooth and Wifi works.
- I haven`t tested the USB-4 port but as a USB port, so I cannot comment on Thunderbolt functionality. But there is a [support forum entry](https://forum.chuwi.com/t/egpu-thunderbolt-problem-on-corebox-4th-does-not-work/37378), indicating that Thunderbolt does not fully work (even) on Windows.

There were some problems with a NVMe drive (Kingston 256GB), containing Linux, transplanted from another mini pc to the corebox. After each shutdown, the first boot results in kernel errors stating problems with the SSD. Another try immediately afterwards usually succeeds. This problem never came up with the build-in SSD, so it could be a problem of the specific SSD but also indicate further problems with the BIOS.

## Further resources

- The user [Wolfix on the official support forums](https://forum.chuwi.com/t/4-pin-fan-adapter-chuwi-corebox-4th/36928) found the required connector and wiring to change the fan.
- The user [ManuCE on the official support forums](https://forum.chuwi.com/t/corebox-4th-driver-win-11/36673) collected all the windows drivers.
