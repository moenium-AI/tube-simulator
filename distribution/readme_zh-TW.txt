================================================================
 Tube Simulator 版本 1.0.0
================================================================

Windows 音訊外掛程式
foobar2000 DSP / VST3

  Copyright (C) 2026 moenium
  發行日期 : 2026-09-16


----------------------------------------------------------------
 1. 概要
----------------------------------------------------------------

Tube Simulator 是一款適用於 Windows 的音訊外掛程式，用於模擬真空管放大器的
動態行為。它提供 foobar2000 v2.x 64 位元 DSP 元件和 64 位元 VST3 外掛程式。
兩個版本使用相同的控制面板和共用的 Realtime Core。

主要功能：

  - 四種 Character：Standard、Dynamic PSU、OPT Magnetic、Full Reference
  - Input Drive、Output、Auto Gain 和 Level Match
  - 獨立於 Level Match 的 COMPARE
  - Auto / 1x / 2x / 4x 線性相位 Oversampling
  - 使用預設 Linear / High Quality 設定時，處理延遲為 302 frames
  - 各設定的 PDC：Linear High / Standard / Light 為 302 / 263 / 218 frames，
    Minimum 為 28 frames
  - 44.1 / 48 / 88.2 / 96 / 176.4 / 192 kHz
  - 單聲道和立體聲運作
  - Factory Preset、輸入/輸出電平表、Diagnostics 和 About

310A、300B 和 274B 這些名稱僅作為技術和歷史上的型號參考使用。使用這些
名稱不表示與任何特定企業或品牌存在關聯、獲得其批准、贊助或認可。


----------------------------------------------------------------
 2. 發行條款
----------------------------------------------------------------

Freeware。可免費用於個人、專業和商業用途。

Factory Preset 已包含在 Tube Simulator 介面中。本版本不包含獨立的預設套件。
請使用外掛程式或宿主提供的功能儲存和載入預設。

再散布、修改、逆向工程以及其他使用條件均規定於隨附的 EULA_jp.txt /
EULA_en.txt 中。本 README 僅作摘要，不會改變 EULA 的內容。


----------------------------------------------------------------
 3. 系統需求
----------------------------------------------------------------

  作業系統 : 64 位元 Windows
  宿主     : foobar2000 v2.x（64 位元）或 64 位元 VST3 宿主
  CPU      : x86-64（Intel / AMD）
  輸出     : 宿主能夠開啟的任何音訊裝置

其他軟體：不需要

不支援 32 位元 foobar2000 和 32 位元 VST 宿主。較高的取樣率和 Oversampling
倍數會增加 CPU 負載。如果變更 Resampler profile，Linear High / Standard /
Light 的 PDC 分別為 302 / 263 / 218 frames，Minimum 為 28 frames。


----------------------------------------------------------------
 4. 安裝
----------------------------------------------------------------

foobar2000 DSP：

  1. 結束 foobar2000。
  2. 連按兩下隨附的 foo_dsp_tube_simulator.fb2k-component 檔案。
     （也可以開啟 File > Preferences > Components 並選擇 Install...）
  3. 選擇 Apply 完成安裝。

安裝元件後不會自動將它加入播放鏈。開啟 File > Preferences > Playback >
DSP Manager，將「Tube Simulator」移至 Active DSPs，然後使用 Configure selected
開啟設定視窗。

VST3：

將隨附的 VST3\\TubeSimulator.vst3 資料夾複製到宿主掃描的 VST3 外掛程式資料夾，
然後重新掃描外掛程式。壓縮檔包含 Windows x86_64 二進位檔。


----------------------------------------------------------------
 5. 開始使用
----------------------------------------------------------------

設定視窗包含 Input、Output、Character、Oversampling、Resampler profile、
Auto Gain、Level Match、COMPARE、Factory Preset、Diagnostics 和 About。

請先將播放音量調低，再從 Standard 或 Factory Preset 開始逐步調整。Auto Gain
和 Level Match 用於調整電平，並不是安全限制器。


----------------------------------------------------------------
 6. 解除安裝
----------------------------------------------------------------

foobar2000 DSP：

  1. 開啟 File > Preferences > Playback > DSP Manager，將「Tube Simulator」
     從 Active DSPs 中移除。
  2. 開啟 File > Preferences > Components，選擇「Tube Simulator DSP」並移除。
  3. 選擇 Apply，然後重新啟動 foobar2000。

VST3：

從宿主使用的 VST3 外掛程式資料夾中刪除 TubeSimulator.vst3 資料夾，然後重新
掃描外掛程式。

如果宿主設定或快取仍然存在，請使用宿主本身的設定管理功能。


----------------------------------------------------------------
 7. 使用注意事項
----------------------------------------------------------------

[播放電平]

Input Drive、Output、Auto Gain、Level Match 和 COMPARE 可能改變峰值電平或
聽感音量。請從較低的播放音量開始，並自行管理最終電平、聽力安全和設備安全。

[Oversampling 和 Resampler profile]

較高的倍數和較高品質的設定會使用更多 CPU。在 VST3 中，變更 profile 後，PDC
會在下一次宿主 prepare 或重新啟動後反映出來。宿主提供的實際處理速率可以在
Diagnostics 的 HOST RATE 中查看。

[設定儲存位置]

設定會儲存在 foobar2000 設定檔或 VST3 宿主的專案/state 管理中。使用者設定
不會包含在發行壓縮檔內。

[靜音行為]

由於真空管模型處理和宿主的尾音約定，數位靜音不一定在數學上嚴格等於零。


----------------------------------------------------------------
 8. 授權
----------------------------------------------------------------

Tube Simulator：專有免費軟體

  可免費用於個人、專業和商業用途。再散布、修改、逆向工程以及其他使用條件
  規定於 EULA_jp.txt / EULA_en.txt 中。

隨附軟體：

  - JUCE 9.0.1（JUCE 9 Starter 授權）：Raw Material Software Limited
    用於建立 Tube Simulator 介面、VST3 實作及相關 UI。適用的是 JUCE 9 End
    User Licence Agreement，而不是 Tube Simulator 自身的授權。

  - Steinberg VST 3 SDK
    使用 JUCE 9.0.1 原始碼樹中提供的 SDK 建立 VST3。其授權和 VST 商標條件
    請參閱 third-party-notices.txt。

  - foobar2000 SDK（foobar2000 專案的獨立條款）
    用於建立 foobar2000 元件。foobar2000 本身不是 Tube Simulator 的一部分，
    也不會隨本軟體發行。

  JUCE 授權摘要以及嵌入元件的完整授權文字，請參閱
  licenses/JUCE_LICENSE.md 和 licenses/JUCE_EMBEDDED_LICENSES.md。其他授權
  詳情請參閱 third-party-notices.txt。


----------------------------------------------------------------
 9. 聯絡與支援
----------------------------------------------------------------

  作者     : moenium
  網站     : https://moenium.net/
  聯絡方式 : contact@moenium.net

如需聯絡或回報問題，請向上述地址寄送電子郵件。

請提供 Tube Simulator 版本、foobar2000 或 VST3 宿主版本、取樣率、Character、
Oversampling、Resampler profile 以及問題重現步驟。Diagnostics 輸出和宿主記錄
也會有所幫助。


----------------------------------------------------------------
 10. 更新記錄
----------------------------------------------------------------

各版本的變更請參閱隨附的 changelog.md。


================================================================
================================================================
