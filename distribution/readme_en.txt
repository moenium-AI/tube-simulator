================================================================
 Tube Simulator Version 1.0.0
================================================================

Windows audio plug-in
foobar2000 DSP / VST3

  Copyright (C) 2026 moenium
  Release date : 2026-09-16


----------------------------------------------------------------
 1. Overview
----------------------------------------------------------------

Tube Simulator is a Windows audio plug-in that models the dynamic behaviour
of a vacuum-tube amplifier. It provides a foobar2000 v2.x 64-bit DSP
component and a 64-bit VST3 plug-in, using the same control panel and shared
Realtime Core.

Its main features are:

  - Four Characters: Standard, Dynamic PSU, OPT Magnetic, Full Reference
  - Input Drive, Output, Auto Gain and Level Match
  - COMPARE, independent from Level Match
  - Auto / 1x / 2x / 4x linear-phase oversampling
  - 302-frame processing latency with the default Linear / High Quality profile
  - Profile PDC of 302 / 263 / 218 frames for Linear High / Standard / Light,
    and 28 frames for Minimum
  - 44.1 / 48 / 88.2 / 96 / 176.4 / 192 kHz
  - Mono and stereo operation
  - Factory presets, input/output meters, Diagnostics and About

The names 310A, 300B and 274B are used solely as technical and historical type
references. Their use does not imply any affiliation with, approval by,
sponsorship by, or endorsement from any particular company or brand.


----------------------------------------------------------------
 2. Distribution terms
----------------------------------------------------------------

Freeware. Free for personal, professional and commercial use.

Factory presets are included in the Tube Simulator interface. This release
does not include a separate preset pack. Save and
load presets using the facilities provided by the plug-in or host.

Redistribution, modification, reverse engineering and all other use
conditions are set out in the bundled EULA_jp.txt / EULA_en.txt. This README
provides only a summary and does not change the EULA.


----------------------------------------------------------------
 3. Requirements
----------------------------------------------------------------

  OS       : 64-bit Windows
  Host     : foobar2000 v2.x (64-bit) or a 64-bit VST3 host
  CPU      : x86-64 (Intel / AMD)
  Output   : Any audio device the host can open

Additional software: none required

32-bit foobar2000 and 32-bit VST hosts are not supported. CPU load increases
with higher sample rates and oversampling factors. If the Resampler profile
is changed, the PDC is 302 / 263 / 218 frames for Linear High / Standard /
Light and 28 frames for Minimum.


----------------------------------------------------------------
 4. Installation
----------------------------------------------------------------

foobar2000 DSP:

  1. Quit foobar2000.
  2. Double-click the bundled foo_dsp_tube_simulator.fb2k-component.
     (Or open File > Preferences > Components and choose Install...)
  3. Select Apply to complete the installation.

Installing the component does not put it in the playback chain. Open
File > Preferences > Playback > DSP Manager, move "Tube Simulator" into
Active DSPs, and use Configure selected to open the settings window.

VST3:

Copy the bundled VST3\TubeSimulator.vst3 folder to a VST3 plug-in folder
scanned by your host, then rescan plug-ins. The archive contains the Windows
x86_64 binary.


----------------------------------------------------------------
 5. Getting started
----------------------------------------------------------------

The settings window includes Input, Output, Character, Oversampling,
Resampler profile, Auto Gain, Level Match, COMPARE, Factory Preset,
Diagnostics and About.

Start with a low playback volume and adjust gradually, beginning with
Standard or a Factory Preset. Auto Gain and Level Match adjust level; they
are not safety limiters.

----------------------------------------------------------------
6. Uninstalling
----------------------------------------------------------------

foobar2000 DSP:

  1. Open File > Preferences > Playback > DSP Manager and move
     "Tube Simulator" out of Active DSPs.
  2. Open File > Preferences > Components, select "Tube Simulator DSP"
     and remove it.
  3. Select Apply and restart foobar2000.

VST3:

Delete the TubeSimulator.vst3 folder from the VST3 plug-in folder used by
your host, then rescan plug-ins.

If host settings or caches remain, use the host's own settings management.


----------------------------------------------------------------
 7. Notes on use
----------------------------------------------------------------

[Playback level]

Input Drive, Output, Auto Gain, Level Match and COMPARE can change peak or
perceived level. Start with a low playback volume and manage final level,
hearing safety and equipment safety yourself.

[Oversampling and Resampler profiles]

Higher factors and higher-quality profiles use more CPU. In VST3, a profile
change is reflected in PDC after the next host prepare or restart. The actual
processing rate supplied by the host can be checked in Diagnostics under
HOST RATE.

[Where settings are stored]

Settings are stored in the foobar2000 profile or in the VST3 host's project /
state management. User settings are not included in the release archive.

[Silence behaviour]

The tube-model processing and host tail contract mean that digital silence is
not necessarily mathematical zero.


----------------------------------------------------------------
 8. Licence
----------------------------------------------------------------

Tube Simulator: proprietary freeware

  Free for personal, professional and commercial use. Redistribution,
  modification, reverse engineering and all other conditions are set out in
  the bundled EULA_jp.txt / EULA_en.txt.

Bundled software:

  - JUCE 9.0.1 (JUCE 9 Starter licence): Raw Material Software Limited
    Used to build the Tube Simulator interface, VST3 implementation and
    related UI. It is governed by the JUCE 9 End User Licence Agreement, not
    by Tube Simulator's own licence.

  - Steinberg VST 3 SDK
    The SDK supplied in the JUCE 9.0.1 source tree is used for the VST3 build.
    See third-party-notices.txt for its licence and VST trademark terms.

  - foobar2000 SDK (foobar2000 project's own terms)
    Used to build Tube Simulator as a foobar2000 component. foobar2000 itself
    is not part of Tube Simulator and is not distributed with it.

  See the bundled licenses/JUCE_LICENSE.md and
  licenses/JUCE_EMBEDDED_LICENSES.md for the JUCE licence summary and the
  complete texts for the embedded components. See third-party-notices.txt
  for other licence details.


----------------------------------------------------------------
 9. Contact and support
----------------------------------------------------------------

  Author        : moenium
  Website       : https://moenium.net/
  Contact       : contact@moenium.net

For contact and bug reports, email the address above.

Include the Tube Simulator version, foobar2000 or VST3 host version, sample
rate, Character, Oversampling, Resampler profile and reproduction steps.
Diagnostics output and host logs are also useful.


----------------------------------------------------------------
 10. Changelog
----------------------------------------------------------------

See the bundled changelog.md for changes in each version.


================================================================
================================================================
