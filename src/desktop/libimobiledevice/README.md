# libimobiledevice

## 安装

```bash
brew install libimobiledevice
```

安装`libimobiledevice`后，根据[GitHub官网](https://github.com/libimobiledevice/libimobiledevice)介绍，其会包含很多工具：

| Utility | Description |
| ------- | ----------- |
| idevice_id | List attached devices or print device name of given device |
| idevicebackup | Create or restore backup for devices (legacy) |
| idevicebackup2 | Create or restore backups for devices running iOS 4 or later |
| idevicecrashreport | Retrieve crash reports from a device |
| idevicedate | Display the current date or set it on a device |
| idevicedebug | Interact with the debugserver service of a device |
| idevicedebugserverproxy | Proxy a debugserver connection from a device for remote debugging |
| idevicediagnostics | Interact with the diagnostics interface of a device |
| ideviceenterrecovery | Make a device enter recovery mode |
| ideviceimagemounter | Mount disk images on the device |
| ideviceinfo | Show information about a connected device |
| idevicename | Display or set the device name |
| idevicenotificationproxy | Post or observe notifications on a device |
| idevicepair | Manage host pairings with devices and usbmuxd |
| ideviceprovision | Manage provisioning profiles on a device |
| idevicescreenshot | Gets a screenshot from the connected device |
| idevicesetlocation | Simulate location on device |
| idevicesyslog | Relay syslog of a connected device |

其中常用的一些工具有：

* `idevice_id`
* `ideviceinfo`

## 子工具

## idevicename

举例：

```bash
 idevicename
iPhone7_1331
```

## idevicedate

举例：

```bash
 idevicedate
Wed Nov  2 21:30:01 CST 2022
```

## ideviceprovision

help语法：

```bash
 ideviceprovision
Usage: ideviceprovision [OPTIONS] COMMAND

Manage provisioning profiles on a device.

Where COMMAND is one of:
  install FILE	Installs the provisioning profile specified by FILE.
              	A valid .mobileprovision file is expected.
  list		Get a list of all provisioning profiles on the device.
  copy PATH	Retrieves all provisioning profiles from the device and
           	stores them into the existing directory specified by PATH.
           	The files will be stored as UUID.mobileprovision
  copy UUID PATH  Retrieves the provisioning profile identified by UUID
           	from the device and stores it into the existing directory
           	specified by PATH. The file will be stored as UUID.mobileprovision.
  remove UUID	Removes the provisioning profile identified by UUID.
  remove-all	Removes all installed provisioning profiles.
  dump FILE	Prints detailed information about the provisioning profile
           	specified by FILE.

The following OPTIONS are accepted:
  -u, --udid UDID  target specific device by UDID
  -n, --network    connect to network device
  -x, --xml        print XML output when using the 'dump' command
  -d, --debug      enable communication debugging
  -h, --help       prints usage information
  -v, --version    prints version information

Homepage:    <https://libimobiledevice.org>
Bug Reports: <https://github.com/libimobiledevice/libimobiledevice/issues>
```
