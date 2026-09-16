<div align="center">

# Tube Simulator

**适用于 Windows 的电子管放大器建模插件**

[![平台](https://img.shields.io/badge/platform-Windows%20x64-lightgrey)](#系统要求)
[![宿主](https://img.shields.io/badge/host-foobar2000%20v2.x%2064--bit-orange)](https://www.foobar2000.org/)
[![许可证](https://img.shields.io/badge/license-proprietary%20freeware-green)](#许可证)

[Product site](https://moenium.net/tube-simulator/) · [Manual](https://moenium.net/tube-simulator/manual/1.0/zh-CN/introduction.html) ·
[GitHub Releases](../../releases/latest) · [Changelog](distribution/changelog.md)

[English](README.md) · [日本語](README.ja.md) · [Deutsch](README.de-DE.md) ·
[Español](README.es-ES.md) · [Français](README.fr-FR.md) ·
[Italiano](README.it-IT.md) · [한국어](README.ko-KR.md) ·
[Português](README.pt-BR.md) · [Русский](README.ru-RU.md) · 简体中文 ·
[繁體中文](README.zh-TW.md)

</div>

---

Tube Simulator 是一款适用于 Windows 的音频插件，用于模拟电子管放大器的动态行为。
它同时提供 foobar2000 v2.x 64 位 DSP 组件和适用于 64 位宿主的 VST3 插件。两个版本
使用相同的实时处理引擎和配置界面。

<div align="center">
<img src="screenshots/tubesimulator_screenshot/tubesimulator.png" alt="Tube Simulator 设置窗口" width="720">
</div>

## 功能

- **四种 Character：** Standard、Dynamic PSU、OPT Magnetic 和 Full Reference。
- **Drive 与输出：** Input Drive 和 Output 可独立调节。
- **电平工具：** Auto Gain、Level Match，以及独立的 COMPARE 试听路径。
- **Oversampling：** Auto、1x、2x、4x 线性相位处理。
- **Resampler 配置：** Linear / Minimum 相位，以及 High、Standard、Light 质量选项。
- **宿主延迟：** 根据配置提供 302、263、218 或 28 samples 的 PDC。
- **诊断功能：** 输入/输出电平表、hold、Diagnostics、About 和 Factory Preset。
- **两种插件格式：** foobar2000 DSP 组件和 64 位 VST3 插件。

## 信号路径

**Signal Path** 视图显示建模的放大器处理级。两个 Character 控件用于选择 Dynamic
PSU 与 OPT Magnetic 分支。

| Dynamic PSU | OPT Magnetic | Character |
| --- | --- | --- |
| 关闭 | 关闭 | Standard |
| 开启 | 关闭 | Dynamic PSU |
| 关闭 | 开启 | OPT Magnetic |
| 开启 | 开启 | Full Reference |

Input Drive 和 Character 决定音色。Output、Auto Gain、Level Match、COMPARE、
Oversampling 和 Resampler 是相互独立的设置。

## 系统要求

| | |
| --- | --- |
| 操作系统 | Windows |
| 宿主 | foobar2000 v2.x，**仅支持 64 位**，或 64 位 VST3 宿主 |
| CPU | x86-64（Intel / AMD） |
| 输出 | 宿主能够打开的任意音频设备 |
| 额外运行库 | 无需 |

不支持 32 位 foobar2000 和 32 位 VST 宿主。较高的采样率、Oversampling 倍率和高质量
Resampler 配置会占用更多 CPU。

## 安装

### foobar2000 DSP 组件

1. 关闭 foobar2000。
2. 双击 `foo_dsp_tube_simulator.fb2k-component`，或打开
   **File → Preferences → Components** 并选择 **Install…**。
3. 选择 **Apply**。
4. 打开 **File → Preferences → Playback → DSP Manager**。
5. 将 **Tube Simulator** 移到 **Active DSPs**。
6. 选择 **Configure selected**。

仅安装组件不会自动将它加入播放链。

### VST3 插件

将 `VST3/TubeSimulator.vst3` 复制到宿主扫描的 VST3 文件夹，然后重新扫描插件。

### 卸载

在 foobar2000 中，将 Tube Simulator 从 **Active DSPs** 移除，然后在
**Preferences → Components** 中删除 **Tube Simulator DSP**。对于 VST3，请从宿主的
VST3 文件夹中删除 `TubeSimulator.vst3`，然后重新扫描。

## 开始使用

建议从 **Standard** 或 Factory Preset 开始，再逐步调整 Input Drive 和 Output。在修改
Drive、Output、Character 或 Oversampling 之前，请降低监听音量；这些设置可能改变峰值电平和感知音量。

建议从 **Standard** 或 Factory Preset 开始，再逐步调整 Input Drive 和 Output。使用
**Level Match** 进行更接近音量的比较，使用 **COMPARE** 试听参考路径。Auto Gain 和
Level Match 是不同的工具。

## 下载与验证

最新版本可从 [GitHub Releases](../../releases/latest) 获取。每个发行页面应列出文件名、
SHA-256/SHA-512 校验和以及相关说明。

在 Windows PowerShell 中，可使用以下命令计算 SHA-256：

```powershell
Get-FileHash .\TubeSimulator_*.zip -Algorithm SHA256
```

## 文档

- [在线手册与语言选择](https://moenium.net/tube-simulator/manual/1.0/)
- [简体中文手册](https://moenium.net/tube-simulator/manual/1.0/zh-CN/introduction.html)
- [Changelog](distribution/changelog.md)
- [README、EULA 和第三方声明](distribution/)
- [JUCE 许可证文档](licenses/)

## 反馈与支持

欢迎提交错误报告、宿主兼容性报告和翻译建议。

**contact@moenium.net**

报告问题时，请提供 Tube Simulator 版本、宿主及其版本、采样率、Character、
Oversampling、Resampler 配置和复现步骤。Diagnostics 中的信息也很有帮助。

## moenium 的其他软件

如果您正在寻找适用于 foobar2000 的更完整的多阶段 DSP，请参阅
[Alauda](https://github.com/moenium-AI/Alauda)。

Alauda 与 Tube Simulator 是不同的产品。

## 支持 Tube Simulator

Tube Simulator 免费提供，并将继续免费。如果它已经成为您聆听链路的一部分，欢迎通过
Ko-fi 支持开发工作。

<p align="center">
  <a href="https://ko-fi.com/moenium">
    <img src="images/kofi_banner.jpg" alt="在 Ko-fi 上支持 Tube Simulator" width="600">
  </a>
</p>

## 许可证

Tube Simulator 是**专有免费软件**，可免费用于个人、专业和商业用途。

再分发、修改、逆向工程及其他条件由随附的
[EULA_en.txt](distribution/EULA_en.txt) / [EULA_jp.txt](distribution/EULA_jp.txt)
规定。日本语 EULA 具有优先效力。本 README 仅为摘要。

有关 JUCE、VST3 SDK 和 foobar2000 SDK 的详情，请参阅[第三方声明](distribution/third-party-notices.txt)。

---

Copyright © 2026 moenium · [moenium.net](https://moenium.net/)
