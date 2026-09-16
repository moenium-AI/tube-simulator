<div align="center">

# Tube Simulator

**Плагин моделирования лампового усилителя для Windows**

[![Платформа](https://img.shields.io/badge/platform-Windows%20x64-lightgrey)](#системные-требования)
[![Хост](https://img.shields.io/badge/host-foobar2000%20v2.x%2064--bit-orange)](https://www.foobar2000.org/)
[![Лицензия](https://img.shields.io/badge/license-proprietary%20freeware-green)](#лицензия)

[Product site](https://moenium.net/tube-simulator/) · [Manual](https://moenium.net/tube-simulator/manual/1.0/ru-RU/introduction.html) ·
[GitHub Releases](../../releases/latest) · [Changelog](distribution/changelog.md)

[English](README.md) · [日本語](README.ja.md) · [Deutsch](README.de-DE.md) ·
[Español](README.es-ES.md) · [Français](README.fr-FR.md) ·
[Italiano](README.it-IT.md) · [한국어](README.ko-KR.md) ·
[Português](README.pt-BR.md) · Русский · [简体中文](README.zh-CN.md) ·
[繁體中文](README.zh-TW.md)

</div>

---

Tube Simulator — это аудиоплагин для Windows, моделирующий динамическое поведение
лампового усилителя. Он доступен как DSP-компонент для 64-битной foobar2000 v2.x
и как плагин VST3 для 64-битных хостов. Обе версии используют один и тот же
движок обработки в реальном времени и один интерфейс настройки.

<div align="center">
<img src="screenshots/tubesimulator_screenshot/tubesimulator.png" alt="Окно настройки Tube Simulator" width="720">
</div>

## Возможности

- **Четыре Character:** Standard, Dynamic PSU, OPT Magnetic и Full Reference.
- **Drive и выход:** Input Drive и Output настраиваются независимо.
- **Инструменты уровня:** Auto Gain, Level Match и независимый путь прослушивания COMPARE.
- **Oversampling:** линейно-фазовая обработка Auto, 1x, 2x и 4x.
- **Профили Resampler:** фаза Linear / Minimum и качество High, Standard или Light.
- **Задержка для хоста:** PDC 302, 263, 218 или 28 samples в зависимости от профиля.
- **Диагностика:** входной и выходной meters, hold, Diagnostics, About и Factory Preset.
- **Два формата:** DSP-компонент foobar2000 и VST3-плагин для 64-битных хостов.

## Сигнальный путь

Представление **Signal Path** показывает моделируемые каскады усилителя. Два
переключателя Character выбирают ветви Dynamic PSU и OPT Magnetic.

| Dynamic PSU | OPT Magnetic | Character |
| --- | --- | --- |
| Выкл. | Выкл. | Standard |
| Вкл. | Выкл. | Dynamic PSU |
| Выкл. | Вкл. | OPT Magnetic |
| Вкл. | Вкл. | Full Reference |

Input Drive и Character определяют voicing. Output, Auto Gain, Level Match,
COMPARE, Oversampling и Resampler являются независимыми настройками.

## Системные требования

| | |
| --- | --- |
| ОС | Windows |
| Хост | foobar2000 v2.x, **только 64-бит**, или 64-битный VST3-хост |
| CPU | x86-64 (Intel / AMD) |
| Выход | Любое аудиоустройство, которое может открыть хост |
| Дополнительная среда выполнения | Не требуется |

32-битные foobar2000 и VST-хосты не поддерживаются. Более высокие частоты
дискретизации, коэффициенты Oversampling и качественные профили Resampler
требуют больше ресурсов CPU.

## Установка

### DSP-компонент foobar2000

1. Закройте foobar2000.
2. Дважды щёлкните `foo_dsp_tube_simulator.fb2k-component` или откройте
   **File → Preferences → Components** и выберите **Install…**.
3. Выберите **Apply**.
4. Откройте **File → Preferences → Playback → DSP Manager**.
5. Переместите **Tube Simulator** в **Active DSPs**.
6. Выберите **Configure selected**.

Одна только установка компонента не добавляет его в цепочку воспроизведения.

### Плагин VST3

Скопируйте `VST3/TubeSimulator.vst3` в папку VST3, сканируемую хостом, затем
запустите повторное сканирование плагинов.

### Удаление

В foobar2000 удалите Tube Simulator из **Active DSPs**, затем удалите
**Tube Simulator DSP** в разделе **Preferences → Components**. Для VST3 удалите
`TubeSimulator.vst3` из папки VST3 хоста и выполните повторное сканирование.

## Начало работы

Начните с **Standard** или Factory Preset, затем постепенно настройте Input Drive и Output.
Перед изменением Drive, Output, Character или Oversampling уменьшите громкость
мониторинга: эти настройки могут изменить пики и воспринимаемую громкость.

Начните с **Standard** или Factory Preset, затем постепенно настройте Input Drive
и Output. Используйте **Level Match** для сравнения на близком уровне и
**COMPARE** для прослушивания эталонного пути. Auto Gain и Level Match — разные инструменты.

## Загрузка и проверка

Последняя версия доступна на странице [GitHub Releases](../../releases/latest).
На каждой странице выпуска должны быть указаны имя файла, контрольные суммы
SHA-256/SHA-512 и соответствующие примечания.

В Windows PowerShell SHA-256 можно вычислить так:

```powershell
Get-FileHash .\TubeSimulator_*.zip -Algorithm SHA256
```

## Документация

- [Онлайн-руководство и выбор языка](https://moenium.net/tube-simulator/manual/1.0/)
- [Руководство на русском](https://moenium.net/tube-simulator/manual/1.0/ru-RU/introduction.html)
- [Changelog](distribution/changelog.md)
- [README, EULA и уведомления о стороннем ПО](distribution/)
- [Документы лицензии JUCE](licenses/)

## Обратная связь и поддержка

Приветствуются сообщения об ошибках, совместимости с хостами и предложения по переводам.

**contact@moenium.net**

Укажите версию Tube Simulator, хост и его версию, частоту дискретизации,
Character, Oversampling, профиль Resampler и шаги для воспроизведения проблемы.
Также полезны сведения из Diagnostics.

## Другие программы moenium

Если вам нужен более масштабный многоступенчатый DSP для foobar2000, ознакомьтесь с
[Alauda](https://github.com/moenium-AI/Alauda).

Alauda и Tube Simulator — отдельные продукты.

## Поддержка Tube Simulator

Tube Simulator бесплатен и останется бесплатным. Если плагин занял место в вашей
цепочке прослушивания, вы можете поддержать его разработку через Ko-fi.

<p align="center">
  <a href="https://ko-fi.com/moenium">
    <img src="images/kofi_banner.jpg" alt="Поддержать Tube Simulator через Ko-fi" width="600">
  </a>
</p>

## Лицензия

Tube Simulator — **проприетарное бесплатное ПО**, которое можно бесплатно
использовать в личных, профессиональных и коммерческих целях.

Условия распространения, изменения, обратной разработки и прочие условия
определены в прилагаемой [EULA_en.txt](distribution/EULA_en.txt) /
[EULA_jp.txt](distribution/EULA_jp.txt). Приоритет имеет японская EULA. Этот
README является только кратким описанием.

Подробности о JUCE, VST3 SDK и foobar2000 SDK приведены в [уведомлениях о стороннем ПО](distribution/third-party-notices.txt).

---

Copyright © 2026 moenium · [moenium.net](https://moenium.net/)
