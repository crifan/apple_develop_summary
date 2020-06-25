# idevice_id

可以用`idevice_id`列出当前（Mac中已）连接的（iOS）的`设备ID`=`UDID`

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

## 使用

举例：

```bash
> idevice_id -l
ed94089f3e34d5538065a695bfdf03dfbb3c5579
```

如果有多个设备，想要获取第一个，则可以借助`head`：

```bash
> idevice_id -l | head -n1
ed94089f3e34d5538065a695bfdf03dfbb3c5579
```

## 帮助和语法

```bash
~  idevice_id --help
Usage: idevice_id [OPTIONS] [UDID]
Prints device name or a list of attached devices.

  If UDID is given, the name of the connected device with that UDID  will be retrieved.

  -l, --list      list UDIDs of all devices attached via USB
  -n, --network   list UDIDs of all devices available via network
  -d, --debug     enable communication debugging
  -h, --help      prints usage information

Homepage: <http://libimobiledevice.org>
```
