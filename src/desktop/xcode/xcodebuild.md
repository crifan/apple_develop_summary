# xcodebuild

* `xcodebuild`
  * 是什么：XCode的命令行工具
  * 作用：用于命令行方式去编译项目
  * 好处：而无需打开XCode图形界面去操作
      * 可用于自动化部署等方面

用法举例：

```bash
UDID=ed94089f3e34d5538065a695bfdf03dfbb3c5579
xcodebuild -project WebDriverAgent.xcodeproj -scheme WebDriverAgentRunner -destination "id=$UDID" test
```
