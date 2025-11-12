# QuickRecovery

QuickRecovery is a port of [QuickSilver](https://unenrollment.com) to [BadRecovery](https://github.com/BinBashBanana/BadRecovery) so devices that cannot boot shims can unenroll with QuickSilver.

## How to use

You will need:
- A USB drive or SD card (8 GB or larger)
- Something to flash the image (dd, rufus, chromebook recovery utility, etc.)
- A ChromeOS device that has not received the patch (see [patch](#patch))

### Downloads

Downloads are located at [https://unenrollment.com/QuickRecovery](https://unenrollment.com/QuickRecovery)

### Building an image

First, you must download an official recovery image for your device.
You can download them from [ChromiumDash](https://chromiumdash.appspot.com/serving-builds?deviceCategory=Chrome%20OS) or [cros.download](https://cros.download/recovery).  
See [modes of operation](#modes-of-operation) for which version you'll need, usually r124 or older.
Be sure you've downloaded the correct image for your device.

Make sure to unzip the recovery image before proceeding to the next step!

Next, you must modify the recovery image using the script included with this repository.

To get the script, run these commands on a linux machine:
```bash
git clone https://github.com/AerialiteLabs/quickrecovery && cd quickrecovery
```

To modify a recovery image using the script, run
```bash
sudo ./build_quickrecovery.sh -i <image.bin>
```
(Replace `<image.bin>` with the path to your recovery image bin.)

The script may prompt you to install required dependencies.

The recovery image is now modified, and is ready to be flashed to a USB drive or SD card.

### Running on ChromeOS device

1. Powerwash the device by pressing [Esc+Ref+Pwr]
2. Start enrolling the device then open powerwash menu [Ctrl+Alt+Shift+R] and wait till it crashes back to OOBE ('Get Started' screen)
3. Try enrolling again but the moment your chromebook says 'Enterprise Enrollment', powerwash [Esc+Ref+Pwr].
4. Enter Developer mode [Ctrl+D]. If it does not work, you messed something up.
1. Powerwash the device again by pressing [Esc+Ref+Pwr]
5. Plug in the prepared USB drive or SD card. QuickRecovery will start in only a few seconds if you've done everything correctly.

When QuickRecovery finishes, you will usually be able to skip the 5 minute developer mode delay by immediately switching back into recovery mode [Esc+Ref+Pwr] to get to developer mode.

## Credits

- Emery/[emerwyi](https://github.com/emerwyi) - discovered quicksilver
- Sophia/[soap-phia](https://github.com/soap-phia) - porting to badrecovery
- OlyB/[BinBashBanana](https://github.com/BinBashBanana) - badrecovery itself
- lxrd/[SPIRAME](https://github.com/SPIRAME) - Sh1ttyExec