<div align="center">

# Tube Simulator

**Windows向け真空管アンプ・モデリング・プラグイン**

[![Platform](https://img.shields.io/badge/platform-Windows%20x64-lightgrey)](#動作環境)
[![Host](https://img.shields.io/badge/host-foobar2000%20v2.x%2064--bit-orange)](https://www.foobar2000.org/)
[![License](https://img.shields.io/badge/license-proprietary%20freeware-green)](#ライセンス)

[製品サイト](https://moenium.net/tube-simulator/) ·
[マニュアル / 日本語](https://moenium.net/tube-simulator/manual/1.0/ja/introduction.html) ·
[English](https://moenium.net/tube-simulator/manual/1.0/en/introduction.html) ·
[Deutsch](https://moenium.net/tube-simulator/manual/1.0/de-DE/introduction.html) ·
[Español](https://moenium.net/tube-simulator/manual/1.0/es-ES/introduction.html) ·
[Français](https://moenium.net/tube-simulator/manual/1.0/fr-FR/introduction.html) ·
[Italiano](https://moenium.net/tube-simulator/manual/1.0/it-IT/introduction.html) ·
[한국어](https://moenium.net/tube-simulator/manual/1.0/ko-KR/introduction.html) ·
[Português](https://moenium.net/tube-simulator/manual/1.0/pt-BR/introduction.html) ·
[Русский](https://moenium.net/tube-simulator/manual/1.0/ru-RU/introduction.html) ·
[简体中文](https://moenium.net/tube-simulator/manual/1.0/zh-CN/introduction.html) ·
[繁體中文](https://moenium.net/tube-simulator/manual/1.0/zh-TW/introduction.html) ·
[言語選択](https://moenium.net/tube-simulator/manual/1.0/)
 [GitHub Releases](../../releases/latest) ·
 [更新履歴](distribution/changelog.md) ·
 [English README](README.md)

</div>

---

Tube Simulator は、真空管アンプの動的な振る舞いをモデル化する
Windows向けオーディオ・プラグインです。foobar2000 v2.x 64-bit用DSP版と
64-bit VST3版を提供し、どちらも共通のリアルタイム処理エンジンと設定画面を
使用します。

<div align="center">
<img src="screenshots/tubesimulator_screenshot/tubesimulator.png" alt="Tube Simulator 設定画面" width="720">
</div>

## 目次

- [主な機能](#主な機能)
- [信号の流れ](#信号の流れ)
- [スクリーンショット](#スクリーンショット)
- [動作環境](#動作環境)
- [インストール](#インストール)
- [使いはじめ](#使いはじめ)
- [ダウンロードと検証](#ダウンロードと検証)
- [ドキュメント](#ドキュメント)
- [フィードバック・不具合報告](#フィードバック不具合報告)
- [moeniumの他のオーディオソフト](#moeniumの他のオーディオソフト)
- [Tube Simulatorを応援する](#tube-simulatorを応援する)
- [ライセンス](#ライセンス)

## 主な機能

- **4種類のCharacter** Standard、Dynamic PSU、OPT Magnetic、Full Reference。
- **真空管らしいドライブと出力調整** Input DriveとOutputを独立して調整できます。
- **ゲイン・レベル調整と比較** Input Drive、Output、Auto Gain、Level Match、および処理音と基準信号を比較するCOMPARE。
- **内部オーバーサンプリング** Auto、1x、2x、4x。
- **選択可能なResampler profile** Linear / Minimum phaseと、High、Standard、Lightの品質設定。
- **ホスト連携レイテンシ** 選択したprofileに応じて302、263、218、28 samplesのPDC。
- **診断機能** 入出力メーター、ホールド、Diagnostics、About、Factory Preset。
- **2種類のプラグイン形式** foobar2000 DSPコンポーネントと64-bit VST3版。

## 信号の流れ

中央のSignal Path表示は、モデル化されたアンプの処理段を表します。2つの
Character設定で、Dynamic PSUとOPT Magneticの分岐を選びます。

| Dynamic PSU | OPT Magnetic | Character |
| --- | --- | --- |
| Off | Off | Standard |
| On | Off | Dynamic PSU |
| Off | On | OPT Magnetic |
| On | On | Full Reference |

Input DriveとCharacterが音色の設定を決めます。Output、Auto Gain、Level Match、
COMPARE、Oversampling、Resamplerは独立した設定で、音色設定を変えずに調整できます。

## スクリーンショット

<table>
<tr><th width="50%">メイン画面</th><th width="50%">Diagnostics</th></tr>
<tr>
<td><img src="screenshots/tubesimulator_screenshot/tubesimulator.png" alt="Tube Simulator メイン画面"></td>
<td><img src="screenshots/tubesimulator_screenshot/tubesimulator_diagnostics.png" alt="Tube Simulator Diagnostics"></td>
</tr>
</table>

## 動作環境

| | |
| --- | --- |
| OS | Windows |
| ホスト | foobar2000 v2.x **64-bit版のみ**、または64-bit VST3ホスト |
| CPU | x86-64（Intel / AMD） |
| 出力 | ホストが開けるオーディオデバイス |
| 追加ランタイム | 不要 |

32-bit版のfoobar2000および32-bit VSTホストには対応していません。高いサンプル
レート、Oversampling倍率、高品質のResampler profileではCPU負荷が増加します。

## インストール

### foobar2000 DSPコンポーネント

1. foobar2000を終了します。
2. `foo_dsp_tube_simulator.fb2k-component` をダブルクリックします。または
   **File → Preferences → Components** を開き、**Install…** を選びます。
3. **Apply** を選び、インストールを完了します。
4. **File → Preferences → Playback → DSP Manager** を開きます。
5. **Tube Simulator** を **Active DSPs** に移動します。
6. **Configure selected** で設定画面を開きます。

コンポーネントをインストールしただけでは、再生チェーンには入りません。

### VST3プラグイン

`VST3/TubeSimulator.vst3` フォルダーを、ホストが検索するVST3プラグイン
フォルダーへコピーし、ホストで再スキャンしてください。

### アンインストール

foobar2000では、Tube Simulatorを **Active DSPs** から外し、
**Preferences → Components** で **Tube Simulator DSP** を削除して
**Apply** を選びます。VST3では、ホストのVST3プラグインフォルダーから
`TubeSimulator.vst3` を削除し、再スキャンしてください。

## 使いはじめ

最初は **Standard** またはFactory Presetから始め、Input DriveとOutputを少しずつ
調整してください。詳しくは[日本語マニュアルのクイックスタート](https://moenium.net/tube-simulator/manual/1.0/ja/quick-start.html)
をご覧ください。

> **Drive、Output、Character、Oversamplingを変更する前に、再生音量を下げてください。**
> これらの設定はピークレベルや聴感上の音量を変えることがあります。

最初は **Standard** またはFactory Presetから始め、Input DriveとOutputを少しずつ
調整してください。音量を揃えて比較するときは **Level Match** を使用し、基準経路を
試聴するときは **COMPARE** を使用します。Auto GainとLevel Matchは異なる機能です。

[Diagnosticsのスクリーンショット](screenshots/tubesimulator_screenshot/tubesimulator_diagnostics.png)
では、ホストレート、処理状態、Character、Oversampling、レイテンシなどを確認できます。

## ダウンロードと検証

最新版は [GitHub Releases](../../releases/latest) から入手できます。各リリースページには、
配布ファイル名、SHA-256/SHA-512チェックサム、リリース固有の注意事項を掲載します。

Windows PowerShellでは、次のコマンドでSHA-256を確認できます。

```powershell
Get-FileHash .\TubeSimulator_*.zip -Algorithm SHA256
```

チェックサムが一致すれば、ダウンロードしたアーカイブがリリースページに記載された
ファイルと同一であることを確認できます。

## ドキュメント

- [オンラインマニュアルと言語選択](https://moenium.net/tube-simulator/manual/1.0/)
- [更新履歴](distribution/changelog.md)
- [同梱README（日本語）](distribution/readme.txt)
- [Bundled README（English）](distribution/readme_en.txt)
- [EULA（日本語正文）](distribution/EULA_jp.txt)
- [EULA（英訳）](distribution/EULA_en.txt)
- [第三者ソフトウェア表記](distribution/third-party-notices.txt)
- [JUCEライセンス概要](licenses/JUCE_LICENSE.md)
- [組み込まれているJUCEコンポーネントのライセンス全文](licenses/JUCE_EMBEDDED_LICENSES.md)

## フィードバック・不具合報告

不具合報告、ホスト互換性の報告、その他のフィードバックを受け付けています。

**contact@moenium.net**

報告の際は、Tube Simulatorのバージョン、ホストとそのバージョン、サンプルレート、
Character、Oversampling、Resampler profile、再現手順を添えてください。Diagnosticsの
表示内容も役立ちます。

## moeniumの他のオーディオソフト

foobar2000向けの多機能DSPをお探しの場合は、
[Alauda](https://github.com/moenium-AI/Alauda)もご覧ください。

AlaudaとTube Simulatorは別の製品です。

## Tube Simulatorを応援する

Tube Simulatorは無料で提供しており、これからも無料で提供する予定です。お気に召し
ましたら、開発を応援していただけると幸いです。

<p align="center">
  <a href="https://ko-fi.com/moenium">
    <img src="images/kofi_banner.jpg" alt="Ko-fiでTube Simulatorを応援する" width="600">
  </a>
</p>

## ライセンス

Tube Simulatorは**プロプライエタリなフリーソフトウェア**です。個人・業務・商用を
問わず無償でご利用いただけます。

再配布、改変、リバースエンジニアリングその他の条件は、同梱の
[EULA_jp.txt](distribution/EULA_jp.txt) / [EULA_en.txt](distribution/EULA_en.txt)
に定めます。日本語版が正文です。

このREADMEは概要のみを示すものであり、EULAの内容を変更または置き換えるものではありません。

### 同梱のサードパーティーソフトウェア

- **JUCE 9.0.1**（JUCE 9 Starterライセンス）Raw Material Software Limited。
  設定画面とVST3実装に使用しており、JUCE自身のライセンス条件に従います。
- **Steinberg VST 3 SDK**。SDK自身のライセンスおよび商標条件に従います。
- **foobar2000 SDK**。foobar2000プロジェクトの定める条件に従います。
  foobar2000本体はTube Simulatorの一部ではなく、同梱もしていません。

詳細は[第三者ソフトウェア表記](distribution/third-party-notices.txt)と
[JUCEライセンス文書](licenses/)をご覧ください。

---

Copyright © 2026 moenium · [moenium.net](https://moenium.net/)
