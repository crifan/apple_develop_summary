# idevice_id

可以用`idevice_id`列出当前（Mac中已）连接的（iOS）的设备

举例：

```bash
 idevice_id -l
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
