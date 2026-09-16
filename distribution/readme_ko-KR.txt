================================================================
 Tube Simulator 버전 1.0.0
================================================================

Windows 오디오 플러그인
foobar2000 DSP / VST3

  Copyright (C) 2026 moenium
  출시일 : 2026-09-16


----------------------------------------------------------------
 1. 개요
----------------------------------------------------------------

Tube Simulator는 진공관 앰프의 동적인 동작을 모델링하는 Windows용 오디오
플러그인입니다. foobar2000 v2.x 64비트용 DSP 컴포넌트와 64비트 VST3
플러그인을 제공하며, 두 형식 모두 동일한 제어 패널과 공통 Realtime Core를
사용합니다.

주요 기능은 다음과 같습니다.

  - 네 가지 Character: Standard, Dynamic PSU, OPT Magnetic, Full Reference
  - Input Drive, Output, Auto Gain, Level Match
  - Level Match와 독립적으로 동작하는 COMPARE
  - Auto / 1x / 2x / 4x Linear-phase Oversampling
  - 기본 Linear / High Quality 프로필에서 302 frames 처리 지연
  - 프로필별 PDC: Linear High / Standard / Light는 302 / 263 / 218 frames,
    Minimum은 28 frames
  - 44.1 / 48 / 88.2 / 96 / 176.4 / 192 kHz
  - 모노 및 스테레오 동작
  - Factory Preset, 입력/출력 미터, Diagnostics, About

310A, 300B, 274B라는 이름은 기술적·역사적인 형식 참조로만 사용됩니다.
이 이름의 사용은 특정 기업 또는 브랜드와의 제휴, 승인, 후원 또는 보증을
의미하지 않습니다.


----------------------------------------------------------------
 2. 배포 조건
----------------------------------------------------------------

프리웨어입니다. 개인적, 업무적, 상업적 용도로 무료로 사용할 수 있습니다.

Factory Preset은 Tube Simulator 인터페이스에 포함되어 있습니다. 이 릴리스에는
별도의 프리셋 팩이 포함되지 않습니다. 플러그인 또는 호스트가 제공하는 기능을
사용하여 프리셋을 저장하고 불러오십시오.

재배포, 수정, 리버스 엔지니어링 및 기타 사용 조건은 함께 제공되는
EULA_jp.txt / EULA_en.txt에 정해져 있습니다. 이 README는 요약본이며 EULA의
내용을 변경하지 않습니다.


----------------------------------------------------------------
 3. 요구 사항
----------------------------------------------------------------

  운영체제 : 64비트 Windows
  호스트   : foobar2000 v2.x (64비트) 또는 64비트 VST3 호스트
  CPU      : x86-64 (Intel / AMD)
  출력     : 호스트가 열 수 있는 모든 오디오 장치

추가 소프트웨어: 필요하지 않음

32비트 foobar2000과 32비트 VST 호스트는 지원하지 않습니다. 더 높은 샘플
레이트와 Oversampling 배율을 사용하면 CPU 부하가 증가합니다. Resampler
profile을 변경하면 Linear High / Standard / Light의 PDC는 각각 302 / 263 /
218 frames이며, Minimum은 28 frames입니다.


----------------------------------------------------------------
 4. 설치
----------------------------------------------------------------

foobar2000 DSP:

  1. foobar2000을 종료합니다.
  2. 함께 제공되는 foo_dsp_tube_simulator.fb2k-component 파일을 더블 클릭합니다.
     (또는 File > Preferences > Components에서 Install...을 선택합니다.)
  3. Apply를 선택하여 설치를 완료합니다.

설치만으로는 재생 체인에 플러그인이 추가되지 않습니다. File > Preferences >
Playback > DSP Manager를 열고 "Tube Simulator"를 Active DSPs로 이동한 뒤,
Configure selected를 사용하여 설정 창을 여십시오.

VST3:

함께 제공되는 VST3\\TubeSimulator.vst3 폴더를 호스트가 검색하는 VST3 플러그인
폴더에 복사한 다음 플러그인을 다시 검색하십시오. 아카이브에는 Windows
x86_64 바이너리가 포함되어 있습니다.


----------------------------------------------------------------
 5. 시작하기
----------------------------------------------------------------

설정 창에는 Input, Output, Character, Oversampling, Resampler profile,
Auto Gain, Level Match, COMPARE, Factory Preset, Diagnostics, About이
포함되어 있습니다.

재생 음량을 낮게 설정한 상태에서 시작하고 Standard 또는 Factory Preset을
기준으로 조금씩 조절하십시오. Auto Gain과 Level Match는 레벨을 조절하는
기능이며 안전 리미터가 아닙니다.


----------------------------------------------------------------
 6. 제거
----------------------------------------------------------------

foobar2000 DSP:

  1. File > Preferences > Playback > DSP Manager를 열고 "Tube Simulator"를
     Active DSPs에서 제거합니다.
  2. File > Preferences > Components를 열고 "Tube Simulator DSP"를 선택하여
     제거합니다.
  3. Apply를 선택하고 foobar2000을 다시 시작합니다.

VST3:

호스트가 사용하는 VST3 플러그인 폴더에서 TubeSimulator.vst3 폴더를 삭제한
다음 플러그인을 다시 검색하십시오.

호스트 설정이나 캐시가 남아 있다면 호스트 자체의 설정 관리 기능을 사용하십시오.


----------------------------------------------------------------
 7. 사용 시 주의 사항
----------------------------------------------------------------

[재생 레벨]

Input Drive, Output, Auto Gain, Level Match, COMPARE는 피크 레벨 또는 청감상
음량을 바꿀 수 있습니다. 낮은 재생 음량에서 시작하고 최종 레벨, 청각 안전,
장비 보호는 사용자 스스로 관리하십시오.

[Oversampling 및 Resampler profile]

높은 배율과 높은 품질의 프로필은 더 많은 CPU를 사용합니다. VST3에서는 다음
host prepare 또는 재시작 후 프로필 변경이 PDC에 반영됩니다. 호스트가 제공하는
실제 처리 레이트는 Diagnostics의 HOST RATE에서 확인할 수 있습니다.

[설정 저장 위치]

설정은 foobar2000 프로필 또는 VST3 호스트의 프로젝트/state 관리 기능에
저장됩니다. 사용자 설정은 릴리스 아카이브에 포함되지 않습니다.

[무음 동작]

진공관 모델 처리와 호스트의 tail 계약에 따라 디지털 무음이 수학적으로 정확한
0이 아닐 수 있습니다.


----------------------------------------------------------------
 8. 라이선스
----------------------------------------------------------------

Tube Simulator: 독점적 프리웨어

  개인적, 업무적, 상업적 용도로 무료로 사용할 수 있습니다. 재배포, 수정,
  리버스 엔지니어링 및 기타 사용 조건은 EULA_jp.txt / EULA_en.txt에 정해져
  있습니다.

포함된 소프트웨어:

  - JUCE 9.0.1 (JUCE 9 Starter 라이선스): Raw Material Software Limited
    Tube Simulator 인터페이스, VST3 구현 및 관련 UI를 만드는 데 사용됩니다.
    Tube Simulator 자체 라이선스가 아니라 JUCE 9 End User Licence Agreement가
    적용됩니다.

  - Steinberg VST 3 SDK
    JUCE 9.0.1 소스 트리에 포함된 SDK를 VST3 빌드에 사용합니다. 라이선스와
    VST 상표 조건은 third-party-notices.txt를 참조하십시오.

  - foobar2000 SDK (foobar2000 프로젝트의 자체 조건)
    foobar2000 컴포넌트를 빌드하는 데 사용됩니다. foobar2000 자체는 Tube
    Simulator의 일부가 아니며 함께 배포되지 않습니다.

  JUCE 라이선스 요약과 포함된 구성 요소의 전체 내용은
  licenses/JUCE_LICENSE.md 및 licenses/JUCE_EMBEDDED_LICENSES.md를 참조하십시오.
  그 밖의 라이선스 세부 사항은 third-party-notices.txt를 참조하십시오.


----------------------------------------------------------------
 9. 문의 및 지원
----------------------------------------------------------------

  제작자   : moenium
  웹사이트 : https://moenium.net/
  연락처   : contact@moenium.net

문의 및 버그 신고는 위의 주소로 이메일을 보내 주십시오.

Tube Simulator 버전, foobar2000 또는 VST3 호스트 버전, 샘플 레이트, Character,
Oversampling, Resampler profile 및 재현 절차를 포함해 주십시오. Diagnostics
출력과 호스트 로그도 도움이 됩니다.


----------------------------------------------------------------
 10. 변경 이력
----------------------------------------------------------------

각 버전의 변경 사항은 함께 제공되는 changelog.md를 참조하십시오.


================================================================
================================================================
