# 端口转发

用`iproxy`或`mobiledevice`

* 如果想要用`localhost`(或`127.0.0.1`)去访问（已连接到Mac上的iOS设备）
    * 需要做端口转发
        * `iproxy`
            * 安装：`brew install --HEAD libimobiledevice`
            * 语法：`iproxy <local port> <remote port> [udid]`
            * 用法举例：
                * `iproxy 8100 8100`
                    * 当前只连接一个iOS设备时，可以不指定，忽略`UDID`
                * `iproxy 8100 8100 ed94089f3e34d5538065a695bfdf03dfbb3c5579`
                    * 指定对应设备的UDID
                      * `ed94089f3e34d5538065a695bfdf03dfbb3c5579`是此处的iPhone的UDID
                    * 可以通过`idevice_id`得到
                        * `CUR_UDID=$(idevice_id -l | head -n1)`
        * `mobiledevice`
            * 安装：`brew install mobiledevice`
            * 用法：
                * `mobiledevice tunnel 8100 8100`
                * `mobiledevice tunnel -u ed94089f3e34d5538065a695bfdf03dfbb3c5579 8100 8100`
                    * 同上，可通过`-u ios_device_udid`，指定对应iOS设备

## iproxy

语法

```bash
~  iproxy --help
usage: iproxy LOCAL_TCP_PORT DEVICE_TCP_PORT [UDID]
```

## mobiledevice

语法：

```bash
~  mobiledevice help
mobiledevice help
  Display this help screen


mobiledevice version [options]
  Display program version.
  Options:
    -r: Include revision identifier


mobiledevice list_devices [options]
  Display UDID of each connected devices.
  Options:
    -t <timeout>: Timeout (in ms) to wait for devices (default: 1)
    -n <count> : Limit the number of devices to be printed


mobiledevice list_device_props [options]
  List all property names of device.
  Options:
    -u <udid> : Filter by device UDID (default: first detected device)
    -t <timeout>: Timeout (in ms) to wait for devices (default: 1)


mobiledevice get_device_prop [options] <prop_name>
  Display value of device property with given name.
  Options:
    -u <udid> : Filter by device UDID (default: first detected device)
    -t <timeout>: Timeout (in ms) to wait for devices (default: 1)


mobiledevice list_apps [options]
  Lists all apps installed on device
  Options:
    -u <udid> : Filter by device UDID (default: first detected device)
    -t <timeout>: Timeout (in ms) to wait for devices (default: 1)


mobiledevice list_app_props [options] <bundle_id>
  List all property names of app with given bundle id.
  Options:
    -u <udid> : Filter by device UDID (default: first detected device)
    -t <timeout>: Timeout (in ms) to wait for devices (default: 1)


mobiledevice get_app_prop [options] <bundle_id> <prop_name>
  Display value of app property with given name.
  Options:
    -u <udid> : Filter by device UDID (default: first detected device)
    -t <timeout>: Timeout (in ms) to wait for devices (default: 1)


mobiledevice install_app [options] <path_to_app>
  Install app (.app folder) to device
  Options:
    -u <udid> : Filter by device UDID (default: first detected device)
    -t <timeout>: Timeout (in ms) to wait for devices (default: 1)


mobiledevice uninstall_app [options] <bundle_id>
  Uninstall app with given bundle id from device
  Options:
    -u <udid> : Filter by device UDID (default: first detected device)
    -t <timeout>: Timeout (in ms) to wait for devices (default: 1)


mobiledevice tunnel [options] <from_port> <to_port>
  Forward TCP connections to connected device
  Options:
    -u <udid> : Filter by device UDID (default: first detected device)
    -t <timeout>: Timeout (in ms) to wait for devices (default: 1)


mobiledevice get_bundle_id <path_to_app>
  Display bundle identifier of app (.app folder)
```

