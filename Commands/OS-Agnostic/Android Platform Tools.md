The android platform tools are `adb` and `fastboot`.

**ADB**  a.k.a. **Android Debug Bridge** is a set of tools distributed by Google, which brings useful features (shell, copy, paste, etc) from an Android device.

## Install
For Windows: 
`choco install adb`

For Linux (depending on the distro):
- Debian-based
`apt install adb`
- Arch-based
`pacman -S adb`
- RPM-based
`dnf install adb`

## Usage
`adb` needs a `deamon` to run and connect to the device. The first time it runs, it stars the `deamon` automatically in the background. 

```shell
adb
*** starting deamon ***
```

The **device** which will be connected to `adb` needs to be in `debug mode`. This option can be activated through the `developer options` menu.

When run again, `adb` will list all the devices attached:

```shell
List devices attached
Device      Status
```

## Options
1. List connected devices
```shell
adb devices
```

2. Copy file from device
```shell
adb pull device/folder/file
```

3. Copy file to device
```shell
adb pull file device/folder
```

4. Interactive Shell
```shell
adb shell
```

5. Reboot
```shell
adb reboot {bootloader|recovery|fastboot}
```

## Fastboot
Reboot
```shell
fastboot reboot {recovery|bootloader}
```

Flash
```shell
fastboot flash {recovery|boot}
```