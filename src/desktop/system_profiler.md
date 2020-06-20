# system_profiler

system_profiler：获取系统信息

举例：

从输出中解析出：

## 真机设备ID

```bash
system_profiler SPUSBDataType
```

注：

此处输出的是很多非常多的全部的信息：

```bash
~  system_profiler SPUSBDataType
2020-04-29 14:50:16.086 system_profiler[46290:995081] SPUSBDevice: IOCreatePlugInInterfaceForService failed 0xe00002be
2020-04-29 14:50:16.086 system_profiler[46290:995081] SPUSBDevice: IOCreatePlugInInterfaceForService failed 0xe00002be
2020-04-29 14:50:16.087 system_profiler[46290:995081] SPUSBDevice: IOCreatePlugInInterfaceForService failed 0xe00002be
2020-04-29 14:50:16.087 system_profiler[46290:995081] SPUSBDevice: IOCreatePlugInInterfaceForService failed 0xe00002be
2020-04-29 14:50:16.088 system_profiler[46290:995081] SPUSBDevice: IOCreatePlugInInterfaceForService failed 0xe00002be
2020-04-29 14:50:16.089 system_profiler[46290:995081] SPUSBDevice: IOCreatePlugInInterfaceForService failed 0xe00002be
USB:

    USB 3.1 Bus:

      Host Controller Driver: AppleIntelCNLUSBXHCI
      PCI Device ID: 0x9ded
      PCI Revision ID: 0x0030
      PCI Vendor ID: 0x8086

        USB2.1 Hub:

          Product ID: 0x0610
          Vendor ID: 0x05e3  (Genesys Logic, Inc.)
          Version: 6.53
          Speed: Up to 480 Mb/sec
          Manufacturer: GenesysLogic
          Location ID: 0x14200000 / 1
          Current Available (mA): 500
          Current Required (mA): 100
          Extra Operating Current (mA): 0

            iPhone:

              Product ID: 0x12a8
              Vendor ID: 0x05ac (Apple Inc.)
              Version: 7.02
              Serial Number: ed94089f3e34d5538065a695bfdf03dfbb3c5579
              Speed: Up to 480 Mb/sec
              Manufacturer: Apple Inc.
              Location ID: 0x14230000 / 16
              Current Available (mA): 500
              Current Required (mA): 500
              Extra Operating Current (mA): 0
              Sleep current (mA): 500

            USB Composite Device:

              Product ID: 0x0002
              Vendor ID: 0x0603  (Novatek Microelectronics Corp.)
              Version: 16.12
              Speed: Up to 1.5 Mb/sec
              Manufacturer: SINO WEALTH
              Location ID: 0x14220000 / 8
              Current Available (mA): 500
              Current Required (mA): 100
              Extra Operating Current (mA): 0

    USB 3.1 Bus:

      Host Controller Driver: AppleUSBXHCITR
      PCI Device ID: 0x15ec
      PCI Revision ID: 0x0006
      PCI Vendor ID: 0x8086
      Bus Number: 0x00

    USB 3.1 Bus:

      Host Controller Driver: AppleUSBXHCITR
      PCI Device ID: 0x15ec
      PCI Revision ID: 0x0006
      PCI Vendor ID: 0x8086
      Bus Number: 0x01

        USB3.1 Hub:

          Product ID: 0x0626
          Vendor ID: 0x05e3  (Genesys Logic, Inc.)
          Version: 6.53
          Speed: Up to 5 Gb/sec
          Manufacturer: GenesysLogic
          Location ID: 0x01100000 / 1
          Current Available (mA): 900
          Current Required (mA): 0
          Extra Operating Current (mA): 0

    iBridge Bus:

      Host Controller Driver: AppleUSBVHCIBCE

        Touch Bar Backlight:

          Product ID: 0x8102
          Vendor ID: 0x05ac (Apple Inc.)
          Version: 2.01
          Serial Number: 0000000000000000
          Manufacturer: Apple Inc.
          Location ID: 0x80700000

        Touch Bar Display:

          Product ID: 0x8302
          Vendor ID: 0x05ac (Apple Inc.)
          Version: 2.01
          Serial Number: 0000000000000000
          Manufacturer: Apple Inc.
          Location ID: 0x80600000

        Apple Internal Keyboard / Trackpad:

          Product ID: 0x027b
          Vendor ID: 0x05ac (Apple Inc.)
          Version: 9.27
          Serial Number: FM7845603R8J3VXAH+TVZ
          Speed: Up to 480 Mb/sec
          Manufacturer: Apple Inc.
          Location ID: 0x80500000 / 8
          Current Available (mA): 500
          Current Required (mA): 500
          Extra Operating Current (mA): 0
          Built-In: Yes


        Headset:


          Product ID: 0x8103
          Vendor ID: 0x05ac (Apple Inc.)
          Version: 2.04
          Serial Number: 000000000000
          Manufacturer: Apple
          Location ID: 0x80400000


        Ambient Light Sensor:


          Product ID: 0x8262
          Vendor ID: 0x05ac (Apple Inc.)
          Version: 2.01
          Serial Number: 000000000000
          Manufacturer: Apple Inc.
          Location ID: 0x80300000


        FaceTime HD Camera (Built-in):


          Product ID: 0x8514
          Vendor ID: 0x05ac (Apple Inc.)
          Version: 2.01
          Serial Number: CC28493XQ52J3Y324
          Manufacturer: Apple Inc.
          Location ID: 0x80200000


        Apple T2 Controller:


          Product ID: 0x8233
          Vendor ID: 0x05ac (Apple Inc.)
          Version: 2.01
          Serial Number: 0000000000000000
          Manufacturer: Apple Inc.
          Location ID: 0x80100000
```

## 屏幕（宽度和高度等）信息

```bash
 system_profiler SPDisplaysDataType
Graphics/Displays:

    Intel Iris Plus Graphics 655:

      Chipset Model: Intel Iris Plus Graphics 655
      Type: GPU
      Bus: Built-In
      VRAM (Dynamic, Max): 1536 MB
      Vendor: Intel
      Device ID: 0x3ea5
      Revision ID: 0x0001
      Metal: Supported, feature set macOS GPUFamily2 v1
      Displays:
        Color LCD:
          Display Type: Built-In Retina LCD
          Resolution: 2560 x 1600 Retina
          Framebuffer Depth: 24-Bit Color (ARGB8888)
          Main Display: Yes
          Mirror: Off
          Online: Yes
          Rotation: Supported
          Automatically Adjust Brightness: No
```

详见：

【已解决】Mac中获取iPhone的分辨率宽高等屏幕信息

## 获取Mac的序列号

```bash
 system_profiler SPHardwareDataType | grep Serial
      Serial Number (system): C02Y3N10JHC8
```

详见：

【已解决】Mac中如何获取笔记本的序列号
