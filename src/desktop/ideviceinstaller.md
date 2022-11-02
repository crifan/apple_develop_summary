# ideviceinstaller

TODO：

* 【已解决】ideviceinstaller卸载iPhone中app后导致无法快捷键截图
* 【已解决】Mac中如何获取到iPhone中自带应用设置的bundle ID

---

在Mac中，想要查看（已通过USB连接上的）iOS设备中已安装的应用信息：

* app名称
* app包名=`bundle id`
* app版本
* 等

可以用：

* ideviceinstaller
  * 作用：列出已安装的app信息

## 安装ideviceinstaller

```bash
brew install --HEAD ideviceinstaller
```

安装后就有了：

* `ideviceinstaller`
  * 内部会自动安装额外的依赖
    * `libusb`
    * `libusbmuxd`
    * `libimobiledevice`
      * 其包含多个工具：
        * `idevice_id`
        * 等
      * 如果单独安装则是：
        ```bash
        brew install libimobiledevice
        ```
    * `libplist`
    * `libtasn1`
    * `libzip`

## 使用

语法：

```bash
ideviceinstaller -l
```

举例：

```bash
 ideviceinstaller -l
Total: 37 apps
com.suiyi.foodshop1 - 食行生鲜 4911
com.cisco.anyconnect - AnyConnect 4.6.03052
com.smartisan.reader - 锤子阅读 1311
com.baidu.BaiduMobile - 百度 10.5.5.10
com.ishuyin.iShuYin - 爱书音 1.22
com.evernote.iPhone.Evernote - 印象笔记 358974
com.alipay.iphoneclient - 支付宝 10.1.2.091512
com.autonavi.amap - 高德地图 8.3.0.2104
ctrip.com - 携程旅行 8.3.0
com.Qting.QTTour - 蜻蜓FM 8.0.1.4
com.iflytek.iflyinput - 讯飞输入法 7.0.1815.9602
com.360buy.jdmobile - 京东 7.3.6
com.taobao.tmall - 手机天猫 10948419
com.crifan.voicerecorddemo - 飞语录音Demo 1
org.reactjs.native.example.AwesomeProject - AwesomeProject 1
com.yingwen.xqlv - 中国象棋 1.01.1
com.crifan.WebDriverAgentRunner.xctrunner - WebDriverAgentRunner-Runner 1
com.tencent.xin - 微信 6.7.4.44
com.cnvcs.xiangqi - 中国象棋 1.5.0
com.netease.cloudmusic - 网易云音乐 876
com.tencent.mqq - QQ 7.2.9.404
。。。
```

获取iPhone中已安装app信息：包名等

* `ideviceinstaller -u {iOSDeviceId} -l -o list_system`
  * 显示系统的app
* `ideviceinstaller -u {iOSDeviceId} -l -o list_user`
  * 显示已安装的用户的app
  * 等价于：
    * `ideviceinstaller -u {iOSDeviceId} -l`
* `ideviceinstaller -u {iOSDeviceId} -l -o list_all`
  * 显示所有（用户+系统）的app

-> 如果只连接了一个iOS设备（比如，只有一个iPhone），则可以省略`-u`参数

```bash
ideviceinstaller -l -o list_system
ideviceinstaller -l -o list_user
ideviceinstaller -l -o list_all
```

举例：

用户安装的程序：

```bash
➜  ~ ideviceinstaller -u ed94089f3e34d5538065a695bfdf03dfbb3c5579 -l
CFBundleIdentifier, CFBundleVersion, CFBundleDisplayName
com.suiyi.foodshop1, "4911", "食行生鲜"
com.cisco.anyconnect, "4.6.03052", "AnyConnect"
com.baidu.BaiduMobile, "10.5.5.10", "百度"
com.ishuyin.iShuYin, "1.22", "爱书音"
com.evernote.iPhone.Evernote, "358974", "印象笔记"
com.alipay.iphoneclient, "10.1.2.091512", "支付宝”
ctrip.com, "8.3.0", "携程旅行"
com.Qting.QTTour, "8.0.1.4", "蜻蜓FM"
com.360buy.jdmobile, "7.3.6", "京东"
com.taobao.tmall, "10948419", "手机天猫"
com.tencent.xin, "6.7.4.44", "微信"
im.workhub.app, "2016.7.31", "Workhub"
com.netease.cloudmusic, "876", "网易云音乐"
com.tencent.mqq, "7.2.9.404", "QQ"
developer.apple.wwdc-Release, "801.5.2", "Developer"
com.ss.iphone.ugc.Aweme, "114011", "抖音短视频"
com.3WRHBBSBW4.com.rileytestut.AltStore, "1", "AltStore"
rn.notes.best, "11122019", "爱思极速版"
```

系统自带（和后来已安装的，被视为系统的）应用 -> 可以查看到系统的应用：

```bash
➜  ~ ideviceinstaller -u ed94089f3e34d5538065a695bfdf03dfbb3c5579 -l -o list_system
CFBundleIdentifier, CFBundleVersion, CFBundleDisplayName
com.apple.MobileAddressBook, "1.0", "通讯录"
com.apple.weather, "1.0", "天气"
com.apple.VoiceMemos, "2.0", "语音备忘录"
com.apple.mobilecal, "1.0", "日历"
com.apple.Home, "1", "家庭"
com.apple.reminders, "1.0", "提醒事项"
com.apple.Maps, "7.0", "地图"
com.apple.mobilemail, "3445.104.12", "邮件"
com.apple.mobilenotes, "1349.30", "备忘录"
com.apple.AXUIViewService, "1", "AXUIViewService"
com.apple.AccountAuthenticationDialog, "1.0", "AccountAuthenticationDialog"
com.apple.AdPlatformsDiagnostics, "1", "Ad Platforms Diagnostics"
com.apple.AppStore, "1", "App Store"
com.apple.AskPermissionUI, "1.0", "AskPermissionUI"
com.apple.CTCarrierSpaceAuth, "1", "CTCarrierSpaceAuth"
com.apple.camera, "1", "相机"
com.apple.CheckerBoard, "1", "CheckerBoard"
com.apple.CompassCalibrationViewService, "1.0", "CompassCalibrationViewService"
com.apple.sidecar.camera, "38", "Continuity Camera"
com.apple.CoreAuthUI, "425.270.3", "用户鉴定"
com.apple.datadetectors.DDActionsService, "331.18", "DDActionsService"
com.apple.carkit.DNDBuddy, "1", "Do Not Disturb While Driving"
com.apple.DataActivation, "1.0", "DataActivation"
com.apple.DemoApp, "1.0", "DemoApp"
com.apple.Diagnostics, "1", "诊断信息"
com.apple.DiagnosticsService, "1", "DiagnosticsService"
com.apple.family, "1", "Family"
com.apple.appleseed.FeedbackAssistant, "390.11", "Feedback"
com.apple.fieldtest, "1.0", "FieldTest"
com.apple.mobileme.fmip1, "500", "查找 iPhone"
com.apple.gamecenter.GameCenterUIService, "577.8", "Game Center 用户界面服务"
com.apple.Health, "1.0", "健康"
com.apple.HealthPrivacyService, "1.0", "HealthPrivacyService"
com.apple.Home.HomeUIService, "1", "HomeUIService"
com.apple.InCallService, "1.0", "InCallService"
com.apple.Magnifier, "1", "放大器"
com.apple.MailCompositionService, "3445.104.12", "MailCompositionService"
com.apple.mobilesms.compose, "1.0", "MessagesViewService"
com.apple.mobilephone, "36", "电话"
com.apple.MobileSMS, "1.0", "信息"
com.apple.mobilesafari, "604.1", "Safari 浏览器"
com.apple.mobileslideshow, "43", "照片"
com.apple.mobiletimer, "1.0", "时钟"
com.apple.MusicUIService, "1.0", "MusicUIService"
com.apple.Passbook, "1.0", "钱包"
com.apple.PassbookStub, "1", "Wallet"
com.apple.PassbookUIService, "1.0", "钱包"
com.apple.PhotosViewService, "1", "PhotosViewService"
com.apple.PreBoard, "1.0", "PreBoard"
com.apple.Preferences, "1.0", "设置"
com.apple.PrintKit.Print-Center, "1.0", "打印中心"
com.apple.SIMSetupUIService, "1", "SIMSetupUIService"
com.apple.social.SLYahooAuth, "1", "SLYahooAuth"
com.apple.SafariViewService, "1.0", "SafariViewService"
com.apple.ScreenSharingViewService, "46.2", "ScreenSharingViewService"
com.apple.ScreenshotServicesService, "1", "ScreenshotServicesService"
com.apple.purplebuddy, "1.0", "设置"
com.apple.SharedWebCredentialViewService, "1.0", "SharedWebCredentialViewService"
com.apple.SharingViewService, "1288.66", "SharingViewService"
com.apple.SiriViewService, "1.0", "Siri"
com.apple.susuiservice, "1", "SoftwareUpdateUIService"
com.apple.StoreDemoViewService, "1", "StoreDemoViewService"
com.apple.ios.StoreKitUIService, "1", "iTunes"
com.apple.TVAccessViewService, "282.60.36", "TVAccessViewService"
com.apple.TVRemoteUIService, "1", "TVRemoteUIService"
com.apple.TrustMe, "1.0", "TrustMe"
com.apple.VSViewService, "291.60.3", "VideoSubscriberAccountViewService"
com.apple.webapp, "1.0", "Web"
com.apple.webapp1, "1.0", "WebApp1"
com.apple.WebContentFilter.remoteUI.WebContentAnalysisUI, "1.0", "WebContentAnalysisUI"
com.apple.WebSheet, "1.0", "WebSheet"
com.apple.iad.iAdOptOut, "1.0", "Workbench Ad Tester"
com.apple.CloudKit.ShareBear, "1", "iCloud"
kjc.loader, "1", "checkra1n"
com.saurik.Cydia, "0.9", "Cydia"
com.tigisoftware.Filza, "2", "Filza"
com.apple.MobileReplayer, "99.97", "MobileReplayer"
```

另外一个已越狱的iPhone7

```bash
➜  ~ ideviceinstaller  -l -o list_user
CFBundleIdentifier, CFBundleVersion, CFBundleDisplayName
com.ccb.ccbDemo, "20211207", "中国建设银行"
com.hxb.mobile.client, "0.0.0.6", "华夏银行"
com.baidu.searchcraft, "3.9.0.0", "简单搜索"
com.netease.cloudmusic, "2546", "网易云音乐"
com.yum.kfc.brand, "1", "肯德基"
com.autohome, "353135", "汽车之家"
com.suzhoubank.SZBank, "5.1.7.2", "苏州银行"
com.cmbchina.MPBBank, "10001", "招商银行"
com.boc.BOCMBCI, "3.0.4", "中国银行"
rn.notes.best, "11122019", "爱思极速版"
com.tencent.xin, "8.0.14.34", "微信"
com.ss.iphone.ugc.Aweme, "178022", "抖音"
science.xnu.undecimus.LT938RA3P2, "1", "unc0ver"
com.crifan.ShowSysInfo, "1", "ShowSysInfo"
```
