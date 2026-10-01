# 屏幕录制

一个极简的 Windows 屏幕录制工具。**单文件 exe，约 67 KB，无需安装，双击即用。**

基于 [mmozeiko/wcap](https://github.com/mmozeiko/wcap) 二次开发，界面与提示已完整汉化，并增加了可视化主窗口。

## 下载

> **wcap-x64.exe** —— [点击下载（本仓库自动编译）](https://github.com/yunhui2026/wcap/releases/latest/download/wcap-x64.exe)

每次向 `main` 推送代码，GitHub Actions 都会自动重新编译并更新上面的安装包，链接永久不变。

系统要求：**Windows 10 1903（2019 年 5 月更新）或更高版本**。

> ⚠️ 由于程序无数字签名，Windows Defender 或第三方杀软可能误报。这是开源无签名程序的常见现象，确认来源可信后添加信任即可。

## 怎么用

启动后会出现主窗口，同时程序常驻系统托盘：

| 操作 | 方式 |
|---|---|
| 录整屏 | 点「● 开始录制」，或按 <kbd>Ctrl</kbd> + <kbd>PrintScreen</kbd> |
| 录活动窗口 | 点「录制窗口」，或按 <kbd>Ctrl</kbd> + <kbd>Win</kbd> + <kbd>PrintScreen</kbd> |
| 录指定区域 | 点「录制选区」，或按 <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>PrintScreen</kbd> |
| 停止 | 再按一次相同的组合键，或右键托盘图标选「停止录制」 |
| 打开设置 | 点「设置」，或右键托盘图标选「设置」 |
| 重新打开主窗口 | 双击托盘图标 |

录制过程中主窗口会自动隐藏，避免被录进视频；停止后自动恢复。点窗口的 × 是最小化到托盘，不会退出程序，右键托盘图标选「退出」才是真正退出。

视频默认保存在「视频」文件夹，文件名为录制开始的时间。

## 功能

- 使用 Windows.Graphics.Capture 捕获，**硬件编码**，CPU 与内存占用极低
- 视频编码：H264/AVC、H265/HEVC、AV1（HEVC 与 AV1 支持 10-bit）
- 音频编码：AAC、FLAC；通过 WASAPI 环回录制系统声音
- 录制单个窗口时可**只录该应用自身的声音**，不混入其它程序
- 可只录窗口客户区（不含标题栏与边框）
- 可选是否录鼠标指针、是否显示录制边框、是否保留窗口圆角
- 可限制录制时长（秒）或文件大小（MB）
- 可限制最大分辨率与帧率，超出时自动缩放
- 可选伽马校正缩放、优化色彩转换
- 碎片化 MP4 输出（仅 H264）：程序崩溃或断电后，已录部分仍可正常播放

## 从源码构建

需要安装 Visual Studio（含 MSVC 与 Windows 10 SDK，用于 `cl.exe` / `rc.exe` / `fxc.exe`）：

```
build.cmd x64
```

产物为 `wcap-x64.exe`。也可以直接推到 GitHub，用本仓库的 Actions 自动编译。

源码中的中文界面依赖以下三点，改动时请一并保持：UTF-8 编码、带 BOM、编译时加 `/utf-8`。

## 联系我

- QQ：**3314967083**

使用中遇到问题、有功能建议，或者需要定制开发，都可以直接加我。

## 赞赏支持

如果这个工具帮到了你，欢迎扫码打赏，金额随意，感谢支持。

<img src="assets/donate.png" width="220" alt="赞赏码">

---

## 许可证

Unlicense —— 本项目及其上游 [mmozeiko/wcap](https://github.com/mmozeiko/wcap) 均释放至公有领域。

任何人可自由复制、修改、发布、使用、编译、销售或分发本软件，无论用于商业或非商业目的，无需署名。
