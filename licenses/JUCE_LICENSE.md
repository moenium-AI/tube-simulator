# The JUCE Framework

The JUCE Framework is an open source framework licensed under a combination of
open source and commercial licences.

The JUCE Framework modules are dual-licensed under the
[AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html) and the commercial [JUCE
licence](https://juce.com/legal/juce-9-licence/).

## The JUCE Licence

If you are not licensing the JUCE Framework modules under the
[AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html) then by downloading,
installing, or using the JUCE Framework, or combining the JUCE Framework with
any other source code, object code, content or any other copyrightable work, you
agree to the terms of the [JUCE 9 End User Licence
Agreement](https://juce.com/legal/juce-9-licence/), and all incorporated terms
including the [JUCE Privacy Policy](https://juce.com/legal/juce-privacy-policy/)
and the [JUCE Website Terms of
Service](https://juce.com/legal/juce-website-terms-of-service/), as applicable,
which will bind you. If you do not agree to the terms of this Agreement, we will
not license the JUCE Framework to you, and you must discontinue the installation
or download process and cease use of the JUCE Framework.

THE JUCE FRAMEWORK IS PROVIDED "AS IS" WITHOUT ANY WARRANTY, AND ALL WARRANTIES,
WHETHER EXPRESSED OR IMPLIED, INCLUDING WARRANTY OF MERCHANTABILITY OR FITNESS
FOR A PARTICULAR PURPOSE, ARE DISCLAIMED.

For more information, visit the [JUCE website](https://juce.com).

## Licence selected for Tube Simulator

Tube Simulator uses JUCE 9.0.1 under the JUCE 9 Starter licence. The Starter
licence is a JUCE licence type and applies only to Tube Simulator's use of the
JUCE Framework; it does not change the licence for Tube Simulator itself or for
any other third-party software.

The official terms are the [JUCE 9 End User Licence
Agreement](https://juce.com/legal/juce-9-licence/). This file is a licence
summary and third-party notice; it is not a replacement for that Agreement.

Official licence terms:
- [JUCE 9 End User Licence Agreement](https://juce.com/legal/juce-9-licence/)
- [JUCE Privacy Policy](https://juce.com/legal/juce-privacy-policy/)
- [JUCE Website Terms of Service](https://juce.com/legal/juce-website-terms-of-service/)

## Components included through Tube Simulator's JUCE build

Tube Simulator directly builds against the following JUCE 9.0.1 modules:

- `juce_core`
- `juce_events`
- `juce_data_structures`
- `juce_graphics`
- `juce_gui_basics`
- `juce_gui_extra`
- `juce_audio_basics`
- `juce_audio_processors_headless`
- `juce_audio_processors`
- `juce_audio_plugin_client`

The Windows JUCE GUI and VST3 projects also compile the following embedded components:

| Component | Licence | Full text |
| --- | --- | --- |
| zlib | zlib License | [`JUCE_EMBEDDED_LICENSES.md#zlib`](JUCE_EMBEDDED_LICENSES.md#zlib) |
| libpng | PNG Reference Library License | [`JUCE_EMBEDDED_LICENSES.md#libpng`](JUCE_EMBEDDED_LICENSES.md#libpng) |
| Independent JPEG Group JPEG software | IJG license | [`JUCE_EMBEDDED_LICENSES.md#independent-jpeg-group-jpeg-software`](JUCE_EMBEDDED_LICENSES.md#independent-jpeg-group-jpeg-software) |
| HarfBuzz | Old MIT license | [`JUCE_EMBEDDED_LICENSES.md#harfbuzz`](JUCE_EMBEDDED_LICENSES.md#harfbuzz) |
| SheenBidi | Apache License 2.0 | [`JUCE_EMBEDDED_LICENSES.md#sheenbidi`](JUCE_EMBEDDED_LICENSES.md#sheenbidi) |
| LunaSVG | MIT License | [`JUCE_EMBEDDED_LICENSES.md#lunasvg`](JUCE_EMBEDDED_LICENSES.md#lunasvg) |
| PlutoVG | MIT License | [`JUCE_EMBEDDED_LICENSES.md#plutovg`](JUCE_EMBEDDED_LICENSES.md#plutovg) |

These notices are part of the vendored JUCE source tree and are separate from
Tube Simulator's own licence. In particular, the accompanying documentation includes
the acknowledgement required by the Independent JPEG Group for binary
redistribution:

> This software is based in part on the work of the Independent JPEG Group.

The complete license and notice texts for these embedded components are
collected in [`JUCE_EMBEDDED_LICENSES.md`](JUCE_EMBEDDED_LICENSES.md). The
original notice files are also retained in the vendored JUCE source tree.

The full JUCE archive contains additional optional modules and dependencies,
including AudioUnitSDK, Oboe, FLAC, Ogg Vorbis, CHOC/QuickJS, LV2, AAX, VST3,
Box2D, and ASIO. Those modules are not vendored or built by Tube Simulator. The Windows
build uses DirectWrite for font rendering and does not bundle FreeType.
