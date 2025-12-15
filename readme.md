![GoodSilver logo](/logo.svg)

GoodSilver is a port of [QuickSilver](https://unenrollment.com) to [BadRecovery](https://github.com/BinBashBanana/BadRecovery) so devices that cannot boot shims can unenroll with QuickSilver.

## How to use

You will need:
- A USB drive or SD card (8 GB or larger)
- Something to flash the image (dd, rufus, chromebook recovery utility, etc.)
- A ChromeOS device that is below r143

### Downloads

Downloads are located at [https://unenrollment.com/GoodSilver](https://unenrollment.com/GoodSilver)

### Building an image

First, you must download an official r124 recovery image for your device.
You can download them from [ChromiumDash](https://chromiumdash.appspot.com/serving-builds?deviceCategory=Chrome%20OS) or [cros.download](https://cros.download/recovery).  
Be sure you've downloaded the correct image for your device.

Make sure to unzip the recovery image before proceeding to the next step!

Next, you must modify the recovery image using the script included with this repository.

To get the script, run these commands on a linux machine:
```bash
git clone https://github.com/AerialiteLabs/GoodSilver && cd GoodSilver
```

To modify a recovery image using the script, run
```bash
sudo ./build_goodsilver.sh -i <image.bin>
```
(Replace `<image.bin>` with the path to your recovery image bin.)

The script may prompt you to install required dependencies.

The recovery image is now modified, and is ready to be flashed to a USB drive or SD card.

### Running on ChromeOS device (this is an example utilizing Sh1ttyExec by lxrd)

1. Powerwash the device by pressing [Ctrl+Alt+Shift+R]
2. Start enrolling the device then open the powerwash menu [Ctrl+Alt+Shift+R] and wait till it crashes back to OOBE ('Get Started' screen)
3. Try enrolling again but the moment your chromebook says 'Enterprise Enrollment', enter recovery mode [Esc+Ref+Pwr].
4. Enter Developer mode [Ctrl+D].
5. Enter recovery mode again by pressing [Esc+Ref+Pwr]
6. Plug in the prepared USB drive or SD card. GoodSilver will start in only a few seconds if you've done everything correctly. If not, turn off developer mode and try again from the start
7. Go through setup, you should be unenrolled!!

## Credits

- Emery/[emerwyi](https://github.com/emerwyi) - discovered quicksilver
- Sophia/[soap-phia](https://github.com/soap-phia) - porting to badrecovery
- OlyB/[BinBashBanana](https://github.com/BinBashBanana) - badrecovery itself
- vk6/[ading2210](http://github.com/ading2210) - badrecovery github workflow
- lxrd/[SPIRAME](https://github.com/SPIRAME) - Sh1ttyExec
