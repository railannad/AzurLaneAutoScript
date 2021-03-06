[English Quick Guide](doc%2FQuick_guide.md) 
[English Readme](README_en.md) `Translation in progress`

[Japanese Readme](README_jp.md) `Translation in progress`

[Download Easy Install-v2](https://github.com/whoamikyo/AzurLaneAutoScript/releases)

# AzurLaneAutoScript

Alas, an Azur Lane automation tool with GUI (Support CN, EN, JP, able to support other servers).

Alas, 一个带GUI的碧蓝航线脚本 (支持国服, 国际服, 日服, 可以支持其他服务器).

**Event Updates** Support Air Raid Drills with Essex

**活动更新** 支持「复刻特别演习埃塞克斯级」

EN support, Thanks **[@whoamikyo](https://github.com/whoamikyo)**

JP support, Thanks **[@ferina8-14](https://github.com/ferina8-14)**, some features might not work

![gui](doc/README.assets/gui.png)



## 功能 Features

- **主线图出击** 基本完成, 请在 `./campaign/campaign_main` 目录下查看支持的地图

- **活动图出击** 支持开荒

- **每日任务** 半小时左右一套做完, 重复运行时会跳过当天做过的

  每日任务(不支持潜艇每日). 困难图. 演习(自动SL), 活动图每日三倍PT, 共斗活动每天15把

- **委托收派** 出击时每20分钟切出去收获, 支持收委托, 收科研, 收任务, 派委托

- **特定模式出击** 7-2三战拣垃圾, 12图练级. ~~碧蓝航线不就只有两张图吗? 最多再算上1-1~~ (

- **其他小功能**

  心情控制, 计算心情防止红脸或者保持经验加成状态

  血量监控, 低血量撤退, 先锋血量平衡

  整队换装备

  掉落截图记录

  自动退役

  开荒模式



## 安装 Installation

详见 [中文安装教程](doc/Installation_cn.md)

包含傻瓜式安装教程和高级用户安装教程.



## 使用注意事项 Note

- 模拟器分辨率需要为 1280 x 720.
- 当修改完设置后, 需要点击"开始"来保存选项, 然后点击"编辑"返回主界面. 因为位于左侧的每一项功能都是分别保存和运行的.
- 在提问题前, 请先阅读 [常见问题(FAQ)](doc/FAQ_en_cn.md)



## 已知问题 Known issue

按出现频率排列

- **GUI启动慢, uiautomator2启动慢**

- **无法处理网络波动** 重连弹窗, 跳小黄鸡

- **在极低配电脑上运行可能会出现各种问题** 缓慢修复中

  极低配, 指截图耗时大于1s. 一般电脑耗时约0.5s, 高配耗时约0.3s, 高配+aScreenCap截图耗时小于0.15s.

- **会显示绿脸黄脸红脸** 这个是瓜游心情值更新BUG, Alas会每隔2小时重启游戏来更新心情.

- **演习可能SL失败** 演习看的是屏幕上方的血槽, 血槽可能被立绘遮挡, 因此需要一定时间(默认1s)血量低于一定值(默认40%)才会触发SL.  一个血皮后排就有30%左右的血槽, 所以别以为在1s内被打掉40%是不可能的. 另外如果后排立绘过大且CD重叠严重, 建议增大确认时间(比如3s), 或者换皮肤, 这样可以减少误判.

- **极少数情况下ADB和uiautomator2会抽风**

- **拖动操作在极少数情况下无效**



## 文档 Doc

[海图识别 perspective](doc/perspective.md)

`海图识别` 是一个碧蓝航线脚本的核心. 如果只是单纯地使用 `模板匹配 (Template matching)` 来进行索敌, 就不可避免地会出现 BOSS被小怪堵住 的情况.  `AzurLaneAutoScript` 提供了一个更好的海图识别方法, 在 `module.map` 中, 你将可以得到完整的海域信息, 比如:

```
2020-03-10 22:09:03.830 | INFO |    A  B  C  D  E  F  G  H
2020-03-10 22:09:03.830 | INFO | 1 -- ++ 2E -- -- -- -- --
2020-03-10 22:09:03.830 | INFO | 2 -- ++ ++ MY -- -- 2E --
2020-03-10 22:09:03.830 | INFO | 3 == -- FL -- -- -- 2E MY
2020-03-10 22:09:03.830 | INFO | 4 -- == -- -- -- -- ++ ++
2020-03-10 22:09:03.830 | INFO | 5 -- -- -- 2E -- 2E ++ ++
```

[参与开发 development](doc/development.md)

- 如何添加一个按钮 How to add a button
- 如何适配一张新的地图 How to adapt to a new map
- 如何支持其他服务器/语言 How to support other server/language



## 参考 Reference

- (Not open source) http://asaiq2.lofter.com/

  现成的碧蓝航线脚本, 完成度很高. 参考了主要的功能和设置.

- https://github.com/Egoistically/ALAuto

  (Archived) https://github.com/perryhuynh/azurlane-auto

  EN服的碧蓝航线脚本, 模仿了脚本架构.

