<div align="center">

# Tube Simulator

**Plug-in zur Modellierung eines Röhrenverstärkers für Windows**

[![Plattform](https://img.shields.io/badge/platform-Windows%20x64-lightgrey)](#anforderungen)
[![Host](https://img.shields.io/badge/host-foobar2000%20v2.x%2064--bit-orange)](https://www.foobar2000.org/)
[![Lizenz](https://img.shields.io/badge/license-proprietary%20freeware-green)](#lizenz)

[Product site](https://moenium.net/tube-simulator/) · [Manual](https://moenium.net/tube-simulator/manual/1.0/de-DE/introduction.html) ·
[GitHub Releases](../../releases/latest) · [Changelog](distribution/changelog.md)

[English](README.md) · [日本語](README.ja.md) · Deutsch ·
[Español](README.es-ES.md) · [Français](README.fr-FR.md) ·
[Italiano](README.it-IT.md) · [한국어](README.ko-KR.md) ·
[Português](README.pt-BR.md) · [Русский](README.ru-RU.md) ·
[简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md)

</div>

---

Tube Simulator ist ein Windows-Audio-Plug-in, das das dynamische Verhalten eines
Röhrenverstärkers modelliert. Es ist als DSP-Komponente für foobar2000 v2.x
64-Bit und als VST3-Plug-in für 64-Bit-Hosts verfügbar. Beide Versionen nutzen
dieselbe Echtzeit-Engine und dieselbe Bedienoberfläche.

<div align="center">
<img src="screenshots/tubesimulator_screenshot/tubesimulator.png" alt="Tube Simulator Konfigurationsfenster" width="720">
</div>

## Funktionen

- **Vier Characters:** Standard, Dynamic PSU, OPT Magnetic und Full Reference.
- **Drive und Ausgang:** Input Drive und Output werden unabhängig eingestellt.
- **Pegelwerkzeuge:** Auto Gain, Level Match und ein unabhängiger COMPARE-Hörweg.
- **Oversampling:** Auto, 1x, 2x und 4x mit linearer Phase.
- **Resampler-Profile:** Linear / Minimum Phase mit High, Standard und Light.
- **Hostgerechte Latenz:** PDC-Werte von 302, 263, 218 oder 28 Samples, abhängig vom Profil.
- **Diagnose:** Eingangs- und Ausgangsmeter, Hold, Diagnostics, About und Factory Preset.
- **Zwei Plug-in-Formate:** foobar2000-DSP-Komponente und 64-Bit-VST3.

## Signalweg

Die Ansicht **Signal Path** stellt die modellierten Verstärkerstufen dar. Die
beiden Character-Schalter wählen die Zweige Dynamic PSU und OPT Magnetic.

| Dynamic PSU | OPT Magnetic | Character |
| --- | --- | --- |
| Aus | Aus | Standard |
| Ein | Aus | Dynamic PSU |
| Aus | Ein | OPT Magnetic |
| Ein | Ein | Full Reference |

Input Drive und Character bestimmen das Voicing. Output, Auto Gain, Level Match,
COMPARE, Oversampling und Resampler sind davon unabhängige Einstellungen.

## Anforderungen

| | |
| --- | --- |
| Betriebssystem | Windows |
| Host | foobar2000 v2.x, **nur 64-Bit**, oder ein 64-Bit-VST3-Host |
| CPU | x86-64 (Intel / AMD) |
| Ausgabe | Jedes Audiogerät, das der Host öffnen kann |
| Zusätzliche Laufzeit | Keine |

32-Bit-foobar2000 und 32-Bit-VST-Hosts werden nicht unterstützt. Höhere
Sampleraten, Oversampling-Faktoren und hochwertige Resampler-Profile benötigen
mehr CPU-Leistung.

## Installation

### foobar2000-DSP-Komponente

1. Beenden Sie foobar2000.
2. Doppelklicken Sie auf `foo_dsp_tube_simulator.fb2k-component`, oder wählen
   Sie unter **File → Preferences → Components** die Option **Install…**.
3. Wählen Sie **Apply**.
4. Öffnen Sie **File → Preferences → Playback → DSP Manager**.
5. Verschieben Sie **Tube Simulator** zu **Active DSPs**.
6. Wählen Sie **Configure selected**.

Die Installation allein fügt die Komponente noch nicht zur Wiedergabekette hinzu.

### VST3-Plug-in

Kopieren Sie `VST3/TubeSimulator.vst3` in einen vom Host gescannten VST3-Ordner
und führen Sie anschließend einen erneuten Plug-in-Scan durch.

### Deinstallation

Entfernen Sie Tube Simulator in foobar2000 aus **Active DSPs** und löschen Sie
**Tube Simulator DSP** unter **Preferences → Components**. Beim VST3-Plug-in
entfernen Sie `TubeSimulator.vst3` aus dem VST3-Ordner des Hosts und scannen erneut.

## Erste Schritte

Beginnen Sie mit **Standard** oder einem Factory Preset und stellen Sie Input Drive
und Output langsam ein. Senken Sie die Abhörlautstärke, bevor Sie Drive, Output, Character oder
Oversampling ändern. Diese Einstellungen können Spitzenpegel und die empfundene
Lautstärke verändern.

Starten Sie mit **Standard** oder einem Factory Preset und stellen Sie Input Drive
und Output langsam ein. Verwenden Sie **Level Match** für einen vergleichbaren
Pegel und **COMPARE** zum Anhören des Referenzwegs. Auto Gain und Level Match
sind unterschiedliche Werkzeuge.

## Download und Überprüfung

Die aktuelle Version ist auf der Seite [GitHub Releases](../../releases/latest)
verfügbar. Dort werden Dateiname, SHA-256/SHA-512-Prüfsummen und wichtige
Hinweise zur jeweiligen Veröffentlichung angegeben.

Unter Windows PowerShell können Sie SHA-256 so berechnen:

```powershell
Get-FileHash .\TubeSimulator_*.zip -Algorithm SHA256
```

## Dokumentation

- [Online-Handbuch und Sprachauswahl](https://moenium.net/tube-simulator/manual/1.0/)
- [Deutsches Handbuch](https://moenium.net/tube-simulator/manual/1.0/de-DE/introduction.html)
- [Changelog](distribution/changelog.md)
- [README, EULA und Third-Party-Hinweise](distribution/)
- [JUCE-Lizenzdokumente](licenses/)

## Feedback und Support

Fehlerberichte, Host-Kompatibilitätsberichte und Übersetzungshinweise sind willkommen.

**contact@moenium.net**

Bitte nennen Sie Version, Host und Host-Version, Samplerate, Character,
Oversampling, Resampler-Profil und reproduzierbare Schritte. Die Anzeige von
Diagnostics ist ebenfalls hilfreich.

## Mehr von moenium

Wenn Sie einen umfangreicheren Multi-Stage-DSP für foobar2000 suchen, sehen Sie
sich [Alauda](https://github.com/moenium-AI/Alauda) an.

Alauda und Tube Simulator sind getrennte Produkte.

## Tube Simulator unterstützen

Tube Simulator ist kostenlos und soll kostenlos bleiben. Wenn das Plug-in einen
Platz in Ihrer Wiedergabekette gefunden hat, können Sie die Weiterentwicklung
über Ko-fi unterstützen.

<p align="center">
  <a href="https://ko-fi.com/moenium">
    <img src="images/kofi_banner.jpg" alt="Tube Simulator auf Ko-fi unterstützen" width="600">
  </a>
</p>

## Lizenz

Tube Simulator ist **proprietäre Freeware** und darf für private, berufliche und
kommerzielle Zwecke kostenlos verwendet werden.

Weitergabe, Änderung, Reverse Engineering und weitere Bedingungen sind in der
beiliegenden [EULA_en.txt](distribution/EULA_en.txt) /
[EULA_jp.txt](distribution/EULA_jp.txt) geregelt. Die japanische EULA ist
maßgeblich. Dieses README ist nur eine Zusammenfassung.

Weitere Informationen zu JUCE, dem VST3 SDK und dem foobar2000 SDK finden Sie in
den [Third-Party-Hinweisen](distribution/third-party-notices.txt).

---

Copyright © 2026 moenium · [moenium.net](https://moenium.net/)
