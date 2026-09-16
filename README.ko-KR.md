<div align="center">

# Tube Simulator

**Windows용 진공관 앰프 모델링 플러그인**

[![플랫폼](https://img.shields.io/badge/platform-Windows%20x64-lightgrey)](#시스템-요구-사항)
[![호스트](https://img.shields.io/badge/host-foobar2000%20v2.x%2064--bit-orange)](https://www.foobar2000.org/)
[![라이선스](https://img.shields.io/badge/license-proprietary%20freeware-green)](#라이선스)

[Product site](https://moenium.net/tube-simulator/) · [Manual](https://moenium.net/tube-simulator/manual/1.0/ko-KR/introduction.html) ·
[GitHub Releases](../../releases/latest) · [Changelog](distribution/changelog.md)

[English](README.md) · [日本語](README.ja.md) · [Deutsch](README.de-DE.md) ·
[Español](README.es-ES.md) · [Français](README.fr-FR.md) ·
[Italiano](README.it-IT.md) · 한국어 · [Português](README.pt-BR.md) ·
[Русский](README.ru-RU.md) · [简体中文](README.zh-CN.md) ·
[繁體中文](README.zh-TW.md)

</div>

---

Tube Simulator는 진공관 앰프의 동적인 동작을 모델링하는 Windows용 오디오
플러그인입니다. foobar2000 v2.x 64비트용 DSP 컴포넌트와 64비트 호스트용 VST3
플러그인으로 제공됩니다. 두 버전은 동일한 실시간 처리 엔진과 설정 화면을 사용합니다.

<div align="center">
<img src="screenshots/tubesimulator_screenshot/tubesimulator.png" alt="Tube Simulator 설정 화면" width="720">
</div>

## 주요 기능

- **4가지 Character:** Standard, Dynamic PSU, OPT Magnetic, Full Reference.
- **Drive 및 출력 조절:** Input Drive와 Output을 독립적으로 조절합니다.
- **레벨 도구:** Auto Gain, Level Match, 독립적인 COMPARE 청취 경로.
- **Oversampling:** Auto, 1x, 2x, 4x 리니어 페이즈 처리.
- **Resampler 프로필:** Linear / Minimum 페이즈와 High, Standard, Light 품질 설정.
- **호스트 레이턴시 연동:** 프로필에 따라 302, 263, 218, 28 samples의 PDC.
- **진단 기능:** 입력/출력 미터, hold, Diagnostics, About, Factory Preset.
- **두 가지 플러그인 형식:** foobar2000 DSP 컴포넌트와 64비트 VST3.

## 신호 경로

**Signal Path** 화면은 모델링된 앰프 단계를 보여 줍니다. 두 Character 조절기는
Dynamic PSU 및 OPT Magnetic 분기를 선택합니다.

| Dynamic PSU | OPT Magnetic | Character |
| --- | --- | --- |
| 끔 | 끔 | Standard |
| 켬 | 끔 | Dynamic PSU |
| 끔 | 켬 | OPT Magnetic |
| 켬 | 켬 | Full Reference |

Input Drive와 Character가 보이싱을 결정합니다. Output, Auto Gain, Level Match,
COMPARE, Oversampling, Resampler는 독립적인 설정입니다.

## 시스템 요구 사항

| | |
| --- | --- |
| 운영 체제 | Windows |
| 호스트 | foobar2000 v2.x **64비트 전용**, 또는 64비트 VST3 호스트 |
| CPU | x86-64 (Intel / AMD) |
| 출력 | 호스트가 열 수 있는 모든 오디오 장치 |
| 추가 런타임 | 없음 |

32비트 foobar2000과 32비트 VST 호스트는 지원하지 않습니다. 높은 샘플레이트,
Oversampling 배율, 고품질 Resampler 프로필은 더 많은 CPU를 사용합니다.

## 설치

### foobar2000 DSP 컴포넌트

1. foobar2000을 종료합니다.
2. `foo_dsp_tube_simulator.fb2k-component`를 더블 클릭하거나,
   **File → Preferences → Components**에서 **Install…**을 선택합니다.
3. **Apply**를 선택합니다.
4. **File → Preferences → Playback → DSP Manager**를 엽니다.
5. **Tube Simulator**를 **Active DSPs**로 이동합니다.
6. **Configure selected**를 선택합니다.

컴포넌트를 설치하는 것만으로는 재생 체인에 자동으로 추가되지 않습니다.

### VST3 플러그인

`VST3/TubeSimulator.vst3`를 호스트가 검색하는 VST3 폴더에 복사한 뒤 플러그인을
다시 검색합니다.

### 제거

foobar2000에서는 **Active DSPs**에서 Tube Simulator를 제거한 다음
**Preferences → Components**에서 **Tube Simulator DSP**를 삭제합니다. VST3에서는
호스트의 VST3 폴더에서 `TubeSimulator.vst3`를 삭제하고 다시 검색합니다.

## 시작하기

**Standard** 또는 Factory Preset에서 시작한 뒤 Input Drive와 Output을 천천히
조절하십시오. Drive, Output, Character 또는 Oversampling을 변경하기 전에 모니터링 음량을
낮추십시오. 이 설정들은 피크 레벨과 체감 음량을 바꿀 수 있습니다.

**Standard** 또는 Factory Preset에서 시작한 뒤 Input Drive와 Output을 천천히
조절하십시오. 더 가까운 음량으로 비교하려면 **Level Match**, 기준 경로를
들으려면 **COMPARE**를 사용하십시오. Auto Gain과 Level Match는 서로 다른 도구입니다.

## 다운로드 및 확인

최신 버전은 [GitHub Releases](../../releases/latest)에서 받을 수 있습니다. 각
릴리스 페이지에는 파일 이름, SHA-256/SHA-512 체크섬과 관련 안내가 포함됩니다.

Windows PowerShell에서는 다음 명령으로 SHA-256을 계산할 수 있습니다.

```powershell
Get-FileHash .\TubeSimulator_*.zip -Algorithm SHA256
```

## 문서

- [온라인 매뉴얼 및 언어 선택](https://moenium.net/tube-simulator/manual/1.0/)
- [한국어 매뉴얼](https://moenium.net/tube-simulator/manual/1.0/ko-KR/introduction.html)
- [Changelog](distribution/changelog.md)
- [README, EULA 및 서드파티 고지](distribution/)
- [JUCE 라이선스 문서](licenses/)

## 피드백 및 지원

버그, 호스트 호환성, 번역에 대한 의견을 환영합니다.

**contact@moenium.net**

문제 보고 시 Tube Simulator 버전, 호스트 및 호스트 버전, 샘플레이트, Character,
Oversampling, Resampler 프로필과 재현 절차를 알려 주세요. Diagnostics의 내용도
도움이 됩니다.

## moenium의 다른 소프트웨어

foobar2000용 더 폭넓은 멀티 스테이지 DSP를 찾고 있다면
[Alauda](https://github.com/moenium-AI/Alauda)를 확인해 보세요.

Alauda와 Tube Simulator는 별개의 제품입니다.

## Tube Simulator 후원

Tube Simulator는 무료이며 앞으로도 무료로 제공할 예정입니다. 청취 체인에서
유용하게 사용하고 계시다면 Ko-fi를 통해 개발을 후원할 수 있습니다.

<p align="center">
  <a href="https://ko-fi.com/moenium">
    <img src="images/kofi_banner.jpg" alt="Ko-fi에서 Tube Simulator 후원하기" width="600">
  </a>
</p>

## 라이선스

Tube Simulator는 **독점 프리웨어**이며 개인적, 전문적, 상업적 용도로 무료 사용할
수 있습니다.

재배포, 수정, 리버스 엔지니어링 및 기타 조건은 함께 제공되는
[EULA_en.txt](distribution/EULA_en.txt) / [EULA_jp.txt](distribution/EULA_jp.txt)에
정해져 있습니다. 일본어 EULA가 우선합니다. 이 README는 요약문일 뿐입니다.

JUCE, VST3 SDK, foobar2000 SDK에 관한 자세한 내용은
[서드파티 고지](distribution/third-party-notices.txt)를 확인하십시오.

---

Copyright © 2026 moenium · [moenium.net](https://moenium.net/)
