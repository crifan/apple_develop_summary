# ideviceinfo

可以用`ideviceinfo`查看当前已连接的iOS设备的各种信息。

## 安装

```bash
brew install libimobiledevice
```

其中会包含很多工具，其中就有此处的`ideviceinfo`

## 使用

查看设备的其他参数信息：

* `ideviceinfo -u {iOSDeviceId} -k DeviceName`
* `ideviceinfo -u {iOSDeviceId} -k ProductVersion`
* `ideviceinfo -u {iOSDeviceId} -k ProductType`
* `ideviceinfo -u {iOSDeviceId} -k ProductName`

举例：

```bash
➜  ~ ideviceinfo -u ed94089f3e34d5538065a695bfdf03dfbb3c5579 -k DeviceName
Crifan iPhone6
➜  ~ ideviceinfo -u ed94089f3e34d5538065a695bfdf03dfbb3c5579 -k ProductVersion
12.4.5
➜  ~ ideviceinfo -u ed94089f3e34d5538065a695bfdf03dfbb3c5579 -k ProductType
iPhone7,2
➜  ~ ideviceinfo -u ed94089f3e34d5538065a695bfdf03dfbb3c5579 -k ProductName
iPhone OS
```

不加参数，则输出全部信息：


举例：

```bash
 ideviceinfo
ActivationState: Activated
BasebandActivationTicketVersion: V2
BasebandCertId: 2315222105
BasebandChipID: 9781473
BasebandKeyHashInformation:
 AKeyStatus: 2
 SKeyHash: u+/tcCwvaQ+1Y9t40I4yegCEmB28mALlaROhaIVGBWo=
 SKeyStatus: 0
BasebandMasterKeyHash: 8CB15EE4C8002199070D9500BB8FB183B02713A5CA2A6B92DB5E75CE15536182
BasebandRegionSKU: AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==
BasebandSerialNumber: yuMYKA==
BasebandStatus: BBInfoAvailable
BasebandVersion: 7.30.01
BluetoothAddress: 14:bd:61:9d:3d:01
BoardId: 8
BrickState: false
BuildVersion: 17D50
CPUArchitecture: arm64
CarrierBundleInfoArray[1]:
 0:
  CFBundleIdentifier: com.apple.ChinaTelecom_USIM_cn
  CFBundleVersion: 40.0.1
  IntegratedCircuitCardIdentity: 89860321945128778023
  InternationalMobileSubscriberIdentity: 460115142016109
  MCC: 460
  MNC: 11
  MobileEquipmentIdentifier: 35534108315977
  Slot: kOne
  kCTPostponementInfoAvailable: SIMCarrierInfo
CertID: 2315222105
ChipID: 32784
ChipSerialNo: yuMYKA==
DeviceClass: iPhone
DeviceColor: 2
DeviceName: iPhone7_1331
DieID: 1707430441053478
EthernetAddress: 14:bd:61:9d:3d:02
FirmwareVersion: iBoot-5540.80.2
FusingStatus: 3
HardwareModel: D10AP
HardwarePlatform: t8010
HasSiDP: true
HostAttached: true
IntegratedCircuitCardIdentity: 89860321945128778023
InternationalMobileEquipmentIdentity: 355341083159771
InternationalMobileSubscriberIdentity: 460115142016109
InternationalMobileSubscriberIdentityOverride: false
MLBSerialNumber: F3X65340DPJH6TGD
MobileEquipmentIdentifier: 35534108315977
MobileSubscriberCountryCode: 460
MobileSubscriberNetworkCode: 11
ModelNumber: MNH12
NonVolatileRAM:
 IONVRAM-SYNCNOW-PROPERTY: SU9OVlJBTS1TWU5DTk9XLVBST1BFUlRZ
 auto-boot: dHJ1ZQ==
 backlight-level: MTQ5NA==
 boot-args:
 com.apple.System.tz0-size: MHhDMDAwMDA=
 oblit-begins: T2JsaXRUeXBlOiBPYmxpdGVyYXRlRGF0YVBhcnRpdGlvbi4gUmVhc29uOiB1bmtub3du
 obliteration: aGFuZGxlX21lc3NhZ2U6IE9ibGl0ZXJhdGlvbiBDb21wbGV0ZQo=
PRIVersion_Major: 0
PRIVersion_Minor: 1
PRIVersion_ReleaseNo: 192
PartitionType: GUID_partition_scheme
PasswordProtected: false
PhoneNumber: +86 xxx xxxx xxxx
PkHash: if98WU1oTt+jcaZlvUC9AOG/rlbJxZpIN+cg7Rv1bCY=
ProductName: iPhone OS
ProductType: iPhone9,1
ProductVersion: 13.3.1
ProductionSOC: true
ProtocolVersion: 2
ProximitySensorCalibration: f3oABTIAHgC34qNBL26oQQAAyELcV5BB8x98QQAAFkPcV5BB8x98QQAAFkPyMktDG2RYwB9thUQAkIVE4fqERK5nhESCc91BppveQUdy8kEOrfpBAAAgQhkEAEM60gtCAABIQg00skMbr7FD2OoDRt9vVkOGGB4eAiAYDvRxlkXj1YlDSDmuRQIAAAAAAACa
RegionInfo: CH/A
SIMStatus: kCTSIMSupportSIMStatusReady
SIMTrayStatus: kCTSIMSupportSIMTrayInsertedWithSIM
SerialNumber: DNPT1P8EHG74
SoftwareBehavior: QQEAAAAAAAAAAAAAAAAAAA==
SoftwareBundleVersion:
SupportedDeviceFamilies[1]:
 0: 1
TelephonyCapability: true
TimeIntervalSince1970: 1667395772.152844
TimeZone: Asia/Shanghai
TimeZoneOffsetFromUTC: 28800.000000
TrustedHostAttached: true
UniqueChipID: 1707430441053478
UniqueDeviceID: adab53e3250e8be1ee0db75bccdc2063df608b46
UseRaptorCerts: true
Uses24HourClock: true
WiFiAddress: 14:bd:61:9d:3d:00
WirelessBoardSerialNumber: F5007716F2
kCTPostponementInfoPRIVersion: 0.1.192
kCTPostponementInfoPRLName: 301
kCTPostponementInfoServiceProvisioningState: true
kCTPostponementStatus: kCTPostponementStatusActivated
```

## help语法

```bash
 ideviceinfo --help
Usage: ideviceinfo [OPTIONS]

Show information about a connected device.

OPTIONS:
  -u, --udid UDID    target specific device by UDID
  -n, --network      connect to network device
  -s, --simple       use a simple connection to avoid auto-pairing with the device
  -q, --domain NAME  set domain of query to NAME. Default: None
  -k, --key NAME     only query key specified by NAME. Default: All keys.
  -x, --xml          output information as xml plist instead of key/value pairs
  -h, --help         prints usage information
  -d, --debug        enable communication debugging
  -v, --version      prints version information

Known domains are:

  com.apple.disk_usage
  com.apple.disk_usage.factory
  com.apple.mobile.battery
  com.apple.iqagent
  com.apple.purplebuddy
  com.apple.PurpleBuddy
  com.apple.mobile.chaperone
  com.apple.mobile.third_party_termination
  com.apple.mobile.lockdownd
  com.apple.mobile.lockdown_cache
  com.apple.xcode.developerdomain
  com.apple.international
  com.apple.mobile.data_sync
  com.apple.mobile.tethered_sync
  com.apple.mobile.mobile_application_usage
  com.apple.mobile.backup
  com.apple.mobile.nikita
  com.apple.mobile.restriction
  com.apple.mobile.user_preferences
  com.apple.mobile.sync_data_class
  com.apple.mobile.software_behavior
  com.apple.mobile.iTunes.SQLMusicLibraryPostProcessCommands
  com.apple.mobile.iTunes.accessories
  com.apple.mobile.internal
  com.apple.mobile.wireless_lockdown
  com.apple.fairplay
  com.apple.iTunes
  com.apple.mobile.iTunes.store
  com.apple.mobile.iTunes

Homepage:    <https://libimobiledevice.org>
Bug Reports: <https://github.com/libimobiledevice/libimobiledevice/issues>
```
