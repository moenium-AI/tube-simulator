<div align="center">

# Tube Simulator

**適用於 Windows 的真空管放大器建模外掛**

[![平台](https://img.shields.io/badge/platform-Windows%20x64-lightgrey)](#系統需求)
[![宿主](https://img.shields.io/badge/host-foobar2000%20v2.x%2064--bit-orange)](https://www.foobar2000.org/)
[![授權](https://img.shields.io/badge/license-proprietary%20freeware-green)](#授權)

[Product site](https://moenium.net/tube-simulator/) · [Manual](https://moenium.net/tube-simulator/manual/1.0/zh-TW/introduction.html) ·
[GitHub Releases](../../releases/latest) · [Changelog](distribution/changelog.md)

[English](README.md) · [日本語](README.ja.md) · [Deutsch](README.de-DE.md) ·
[Español](README.es-ES.md) · [Français](README.fr-FR.md) ·
[Italiano](README.it-IT.md) · [한국어](README.ko-KR.md) ·
[Português](README.pt-BR.md) · [Русский](README.ru-RU.md) ·
[简体中文](README.zh-CN.md) · 繁體中文

</div>

---

Tube Simulator 是一款適用於 Windows 的音訊外掛，用來模擬真空管放大器的動態行為。
它同時提供 foobar2000 v2.x 64 位元 DSP 元件，以及適用於 64 位元宿主的 VST3 外掛。
兩個版本使用相同的即時處理引擎與設定介面。

<div align="center">
<img src="screenshots/tubesimulator_screenshot/tubesimulator.png" alt="Tube Simulator 設定視窗" width="720">
</div>

## 功能

- **四種 Character：** Standard、Dynamic PSU、OPT Magnetic 與 Full Reference。
- **Drive 與輸出：** Input Drive 與 Output 可獨立調整。
- **電平工具：** Auto Gain、Level Match，以及獨立的 COMPARE 試聽路徑。
- **Oversampling：** Auto、1x、2x、4x 線性相位處理。
- **Resampler 設定檔：** Linear / Minimum 相位，以及 High、Standard、Light 品質選項。
- **宿主延遲：** 依設定提供 302、263、218 或 28 samples 的 PDC。
- **診斷功能：** 輸入/輸出電平表、hold、Diagnostics、About 與 Factory Preset。
- **兩種外掛格式：** foobar2000 DSP 元件與 64 位元 VST3 外掛。

## 訊號路徑

**Signal Path** 檢視會顯示建模的放大器處理級。兩個 Character 控制項用來選擇
Dynamic PSU 與 OPT Magnetic 分支。

| Dynamic PSU | OPT Magnetic | Character |
| --- | --- | --- |
| 關閉 | 關閉 | Standard |
| 開啟 | 關閉 | Dynamic PSU |
| 關閉 | 開啟 | OPT Magnetic |
| 開啟 | 開啟 | Full Reference |

Input Drive 與 Character 決定音色。Output、Auto Gain、Level Match、COMPARE、
Oversampling 與 Resampler 是彼此獨立的設定。

## 系統需求

| | |
| --- | --- |
| 作業系統 | Windows |
| 宿主 | foobar2000 v2.x，**僅支援 64 位元**，或 64 位元 VST3 宿主 |
| CPU | x86-64（Intel / AMD） |
| 輸出 | 宿主能夠開啟的任何音訊裝置 |
| 額外執行環境 | 不需要 |

不支援 32 位元 foobar2000 與 32 位元 VST 宿主。較高的取樣率、Oversampling 倍率與
高品質 Resampler 設定會使用更多 CPU。

## 安裝

### foobar2000 DSP 元件

1. 關閉 foobar2000。
2. 連按兩下 `foo_dsp_tube_simulator.fb2k-component`，或開啟
   **File → Preferences → Components** 並選擇 **Install…**。
3. 選擇 **Apply**。
4. 開啟 **File → Preferences → Playback → DSP Manager**。
5. 將 **Tube Simulator** 移至 **Active DSPs**。
6. 選擇 **Configure selected**。

僅安裝元件並不會自動將它加入播放鏈。

### VST3 外掛

將 `VST3/TubeSimulator.vst3` 複製到宿主掃描的 VST3 資料夾，然後重新掃描外掛。

### 解除安裝

在 foobar2000 中，將 Tube Simulator 從 **Active DSPs** 移除，再於
**Preferences → Components** 中刪除 **Tube Simulator DSP**。對於 VST3，請從宿主的
VST3 資料夾刪除 `TubeSimulator.vst3`，然後重新掃描。

## 開始使用

建議從 **Standard** 或 Factory Preset 開始，再逐步調整 Input Drive 與 Output。變更
Drive、Output、Character 或 Oversampling 前，請降低監聽音量；這些設定可能改變峰值電平與感知音量。

建議從 **Standard** 或 Factory Preset 開始，再逐步調整 Input Drive 與 Output。使用
**Level Match** 進行更接近音量的比較，使用 **COMPARE** 試聽參考路徑。Auto Gain 與
Level Match 是不同的工具。

## 下載與驗證

最新版本可從 [GitHub Releases](../../releases/latest) 取得。每個發行頁面應列出檔案名稱、
SHA-256/SHA-512 校驗和以及相關說明。

在 Windows PowerShell 中，可以使用以下命令計算 SHA-256：

```powershell
Get-FileHash .\TubeSimulator_*.zip -Algorithm SHA256
```

## 文件

- [線上手冊與語言選擇](https://moenium.net/tube-simulator/manual/1.0/)
- [繁體中文手冊](https://moenium.net/tube-simulator/manual/1.0/zh-TW/introduction.html)
- [Changelog](distribution/changelog.md)
- [README、EULA 與第三方聲明](distribution/)
- [JUCE 授權文件](licenses/)

## 回饋與支援

歡迎提交錯誤報告、宿主相容性報告與翻譯建議。

**contact@moenium.net**

回報問題時，請提供 Tube Simulator 版本、宿主及其版本、取樣率、Character、
Oversampling、Resampler 設定檔與重現步驟。Diagnostics 中的資訊也很有幫助。

## moenium 的其他軟體

如果您正在尋找適用於 foobar2000 的更完整多階段 DSP，請參閱
[Alauda](https://github.com/moenium-AI/Alauda)。

Alauda 與 Tube Simulator 是不同的產品。

## 支援 Tube Simulator

Tube Simulator 免費提供，今後也會維持免費。如果它已經成為您聆聽鏈路的一部分，歡迎
透過 Ko-fi 支援開發工作。

<p align="center">
  <a href="https://ko-fi.com/moenium">
    <img src="images/kofi_banner.jpg" alt="在 Ko-fi 上支援 Tube Simulator" width="600">
  </a>
</p>

## 授權

Tube Simulator 是**專有免費軟體**，可免費用於個人、專業與商業用途。

再散布、修改、逆向工程及其他條件由隨附的
[EULA_en.txt](distribution/EULA_en.txt) / [EULA_jp.txt](distribution/EULA_jp.txt)
規定。日文 EULA 具有優先效力。本 README 僅為摘要。

有關 JUCE、VST3 SDK 與 foobar2000 SDK 的詳情，請參閱[第三方聲明](distribution/third-party-notices.txt)。

---

Copyright © 2026 moenium · [moenium.net](https://moenium.net/)
