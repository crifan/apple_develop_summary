# iPhone

`iOS`设备中普通用户接触最多的就是`iPhone`了。

此处整理相关开发心得。

## 开发相关设置

新版iPhone中的设置中有个`开发者`，有很多开发相关的设置。

其中和自动化测试有关的是：

`设置`->`开发者`->`Enable UI Automation`

![iphone_settings_developer](../../assets/img/iphone_settings_developer.png)

![developer_enable_ui_automation](../../assets/img/developer_enable_ui_automation.png)

对于后续自动化测试，或许有用。

## iPhone真机的log日志查看

可以通过 控制台 查看iPhone真机的Log日志

如何打开控制台：
* 启动台Launch Pad -> 其他 -> 控制台
    * ![launch_pad_control_panel](../../assets/img/launch_pad_control_panel.png)
* XCode->Window->Devices and Simulators->Devices
    * ![devices_and_simulators_devices](../../assets/img/devices_and_simulators_devices.jpg)

启动后，即可看到iPhone真机的log日志了：

![iphone_real_log_info](../../assets/img/iphone_real_log_info.png)

也支持条件过滤，比如：

任一 包含：`WebDriverAgentRunner`

![log_filter_any_one](../../assets/img/log_filter_any_one.png)

![added_filter_show_log](../../assets/img/added_filter_show_log.png)

## 关闭悬浮球

iOS自动化测试期间，记得要关闭：悬浮球

【已解决】iPhone中关闭全屏显示的悬浮球

否则有时候会误触发，影响自动化测试
