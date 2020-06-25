# ideviceinstaller

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
