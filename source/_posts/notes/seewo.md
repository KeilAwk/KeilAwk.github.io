---
title: Seewo运维
date: 2024-08
note: true
tags:
---

# 希沃生态应用

## PPT小助手

一个在Office放映ppt时显示的工具栏，现在已经被整合到 希沃课堂助手 (SeewoIwbAssistant) ，原有独立版已经不再维护

对标替代有[鸿合演示助手](https://pie.hitecloud.cn/pie?flag=CxLPzyieeAHOTuOpyfnpdaFJPcLCZox5B7%2FcJtkr%2BZCInMxHGMc8Mh7%2Fd9TFGEZ7)功能相对更丰富，触控体验更友好（UI排布位置偏低，不会高高在上），不依赖自启动，通过加载项（Office工具栏）的方式启动即可

另有网传的MAXHUB版的PPT小工具，但未公开下载，估计跟希沃的差不多

新版长这样（在原有的翻页按钮、页面跳转与预览、一般工具、ppt分享的基础上添加了手机遥控翻页和更好的UI动效与隐藏工具栏）：

![截图](/img/notes/seewo.1.jpg)

### PPT小助手修复

B站上有旧代机提取的PPTChecker工具，优先使用这个修复

如果无效，使用[IOBit Uninstaller](https://www.iobit.com/en/advanceduninstaller.php)彻底卸载Office后重启，使用[Office Tool Plus](https://otp.landian.vip/zh-cn/)重新部署安装Office并重新安装PPT小工具即可

### 设置禁用PPT小助手

关闭PPT小助手的自启动即可（则下次开机时应用，否则应一并停止其现在运行的后台进程）

## 希沃白板

希沃家主打的白板教学软件

国际版(好像停更)在 [easinote.seewo.com/english](https://easinote.seewo.com/english)

网页版在 [enweb.seewo.com](https://enweb.seewo.com/)

MAXHUB国际版(HAXHUB Class)在 [www.maxhub.com/en/class](https://www.maxhub.com/en/class/)

### 插件

依赖插件，可以扩展EN5的画笔、启动匿名离线模式，IWB强制识别，云云

官方插件开发支持在 [github.com/EasiNote](https://github.com/EasiNote/)

网上已知有整合 [BV1gP4y1i7TV](https://www.bilibili.com/video/BV1gP4y1i7TV)

IWB插件（把非希沃设备识别成希沃，使EN5进入白板模式）: [bilibili.com/opus/744736836725768208](https://www.bilibili.com/opus/744736836725768208) 文中的蓝奏云链接是[lanzoue.com/iinUx0jfsw2h](https://lanzoue.com/iinUx0jfsw2h)

### EasiAgent 单点登录

类似QQ PC的登陆服务，一次登录，各希沃APP和网页都可以直接快速登陆

原理是将登录请求以hosts定向的方式转发到本地服务

已知有对此的项目用于希沃账号自动登录 ENAL（弃坑状态，开源，可在B站 [BV1fz42197kn](https://www.bilibili.com/video/BV1fz42197kn) 找到原视频） [enal.nlrdev.top](https://enal.nlrdev.top)

# MAXHUB

和希沃出自同一个母公司[CVTE视源股份](http://www.cvte.com/)，俗称C厂

MAXHUB一些国内没有公开的资源如MAXHUB Windows镜像，在国际版官网的下载中心可以直接拿到链接下载

# 希沃大板维护

“大板”指的是里那些白板（实体）

## 打开工程菜单

使用遥控器，依次按`INPUT`、`1`、`3`、`7`、`9`即可

## 大板还原Windows

旧代机（即Android版本低于9的），依次 进入安卓通道 -> 设置 -> 关于 -> 多次点击触控信息，直到出现还原提示即可

新代机关机状态下长按开机键，直到开机键红蓝交替闪烁后松手，等待一下即可进入还原菜单（还原会同时还原安卓通道和PC模块，用时较长。还原后需要激活，硬件层面上）

**切勿通过工程菜单还原（除非你是教师或校方管理，则有能力取得激活授权）**，这只会还原安卓通道而不是Windows（即PC模块），并且**设备需要重新激活（真的是硬件层面的，而不是Windows激活，未激活会锁设备）**

## 激活大板

开机后等待二维码出现（插网线到大板而不是PC模块，可能可以加快加载速度），使用微信扫码，按提示操作，填入实际地址，即可获得几位数（好像是八位数？）的激活码

一码一设备，同设备激活码不会改变

## 希沃白板修改

包括：

```
- 修改TouchService自启方式为计划任务（仅win7设备）
- 修改UAC
- 浏览器替换为Chrome并使用SwitchyOmega代理指向无效地址
- 删除应用商店
- 添加CooderDesk或MyDock
- 使用火绒锁定CooderDesk或MyDock、桌面快捷方式设定、桌面快捷方式
- 删除开始菜单系统程序，使用组策略禁用控制面板与设置、锁定任务栏
- 网线改直插OPS
- 禁用快速启动
```
