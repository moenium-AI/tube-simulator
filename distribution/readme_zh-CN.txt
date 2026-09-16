================================================================
 Tube Simulator 版本 1.0.0
================================================================

Windows 音频插件
foobar2000 DSP / VST3

  Copyright (C) 2026 moenium
  发布日期 : 2026-09-16


----------------------------------------------------------------
 1. 概述
----------------------------------------------------------------

Tube Simulator 是一款适用于 Windows 的音频插件，用于模拟电子管放大器的
动态行为。它提供 foobar2000 v2.x 64 位 DSP 组件和 64 位 VST3 插件。两个
版本使用相同的控制面板和共用的 Realtime Core。

主要功能：

  - 四种 Character：Standard、Dynamic PSU、OPT Magnetic、Full Reference
  - Input Drive、Output、Auto Gain 和 Level Match
  - 独立于 Level Match 的 COMPARE
  - Auto / 1x / 2x / 4x 线性相位 Oversampling
  - 使用默认 Linear / High Quality 配置时，处理延迟为 302 frames
  - 各配置的 PDC：Linear High / Standard / Light 为 302 / 263 / 218 frames，
    Minimum 为 28 frames
  - 44.1 / 48 / 88.2 / 96 / 176.4 / 192 kHz
  - 单声道和立体声运行
  - Factory Preset、输入/输出电平表、Diagnostics 和 About

310A、300B 和 274B 这些名称仅作为技术和历史上的型号参考使用。使用这些
名称不表示与任何特定企业或品牌存在关联、获得其批准、赞助或认可。


----------------------------------------------------------------
 2. 分发条款
----------------------------------------------------------------

Freeware。可免费用于个人、专业和商业用途。

Factory Preset 已包含在 Tube Simulator 界面中。本版本不包含单独的预设包。
请使用插件或宿主提供的功能保存和加载预设。

再分发、修改、逆向工程以及其他使用条件均规定于随附的 EULA_jp.txt /
EULA_en.txt 中。本 README 仅作摘要，不会改变 EULA 的内容。


----------------------------------------------------------------
 3. 系统要求
----------------------------------------------------------------

  操作系统 : 64 位 Windows
  宿主     : foobar2000 v2.x（64 位）或 64 位 VST3 宿主
  CPU      : x86-64（Intel / AMD）
  输出     : 宿主能够打开的任意音频设备

其他软件：不需要

不支持 32 位 foobar2000 和 32 位 VST 宿主。较高的采样率和 Oversampling
倍数会增加 CPU 负载。如果更改 Resampler profile，Linear High / Standard /
Light 的 PDC 分别为 302 / 263 / 218 frames，Minimum 为 28 frames。


----------------------------------------------------------------
 4. 安装
----------------------------------------------------------------

foobar2000 DSP：

  1. 退出 foobar2000。
  2. 双击随附的 foo_dsp_tube_simulator.fb2k-component 文件。
     （也可以打开 File > Preferences > Components 并选择 Install...）
  3. 选择 Apply 完成安装。

安装组件后不会自动将其加入播放链。打开 File > Preferences > Playback >
DSP Manager，将“Tube Simulator”移至 Active DSPs，然后使用 Configure selected
打开设置窗口。

VST3：

将随附的 VST3\\TubeSimulator.vst3 文件夹复制到宿主扫描的 VST3 插件文件夹中，
然后重新扫描插件。压缩包包含 Windows x86_64 二进制文件。


----------------------------------------------------------------
 5. 开始使用
----------------------------------------------------------------

设置窗口包含 Input、Output、Character、Oversampling、Resampler profile、
Auto Gain、Level Match、COMPARE、Factory Preset、Diagnostics 和 About。

请先将播放音量调低，再从 Standard 或 Factory Preset 开始逐步调整。Auto Gain
和 Level Match 用于调整电平，并不是安全限制器。


----------------------------------------------------------------
 6. 卸载
----------------------------------------------------------------

foobar2000 DSP：

  1. 打开 File > Preferences > Playback > DSP Manager，将 “Tube Simulator”
     从 Active DSPs 中移除。
  2. 打开 File > Preferences > Components，选择 “Tube Simulator DSP” 并移除。
  3. 选择 Apply，然后重新启动 foobar2000。

VST3：

从宿主使用的 VST3 插件文件夹中删除 TubeSimulator.vst3 文件夹，然后重新扫描
插件。

如果宿主设置或缓存仍然存在，请使用宿主自身的设置管理功能。


----------------------------------------------------------------
 7. 使用注意事项
----------------------------------------------------------------

[播放电平]

Input Drive、Output、Auto Gain、Level Match 和 COMPARE 可能改变峰值电平或
听感音量。请从较低的播放音量开始，并自行管理最终电平、听力安全和设备安全。

[Oversampling 和 Resampler profile]

较高的倍数和较高质量的配置会使用更多 CPU。在 VST3 中，更改 profile 后，
PDC 会在下一次宿主 prepare 或重启后反映出来。宿主提供的实际处理速率可以在
Diagnostics 的 HOST RATE 中查看。

[设置保存位置]

设置会保存在 foobar2000 配置文件夹或 VST3 宿主的项目/state 管理中。用户设置
不会包含在发布压缩包内。

[静音行为]

由于电子管模型处理和宿主的尾音约定，数字静音不一定在数学上严格等于零。


----------------------------------------------------------------
 8. 许可证
----------------------------------------------------------------

Tube Simulator：专有免费软件

  可免费用于个人、专业和商业用途。再分发、修改、逆向工程以及其他使用条件
  规定于 EULA_jp.txt / EULA_en.txt 中。

随附软件：

  - JUCE 9.0.1（JUCE 9 Starter 许可证）：Raw Material Software Limited
    用于构建 Tube Simulator 界面、VST3 实现及相关 UI。适用的是 JUCE 9 End
    User Licence Agreement，而不是 Tube Simulator 自身的许可证。

  - Steinberg VST 3 SDK
    使用 JUCE 9.0.1 源代码树中提供的 SDK 构建 VST3。其许可证和 VST 商标条件
    请参阅 third-party-notices.txt。

  - foobar2000 SDK（foobar2000 项目的独立条款）
    用于构建 foobar2000 组件。foobar2000 本身不是 Tube Simulator 的一部分，
    也不会随本软件分发。

  JUCE 许可证摘要以及嵌入组件的完整许可证文本，请参阅
  licenses/JUCE_LICENSE.md 和 licenses/JUCE_EMBEDDED_LICENSES.md。其他许可证
  详情请参阅 third-party-notices.txt。


----------------------------------------------------------------
 9. 联系与支持
----------------------------------------------------------------

  作者     : moenium
  网站     : https://moenium.net/
  联系方式 : contact@moenium.net

如需联系或报告问题，请向上述地址发送电子邮件。

请提供 Tube Simulator 版本、foobar2000 或 VST3 宿主版本、采样率、Character、
Oversampling、Resampler profile 以及问题重现步骤。Diagnostics 输出和宿主日志
也会有所帮助。


----------------------------------------------------------------
 10. 更新日志
----------------------------------------------------------------

每个版本的变更请参阅随附的 changelog.md。


================================================================
================================================================
