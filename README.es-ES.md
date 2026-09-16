<div align="center">

# Tube Simulator

**Plugin de modelado de amplificador de válvulas para Windows**

[![Plataforma](https://img.shields.io/badge/platform-Windows%20x64-lightgrey)](#requisitos)
[![Host](https://img.shields.io/badge/host-foobar2000%20v2.x%2064--bit-orange)](https://www.foobar2000.org/)
[![Licencia](https://img.shields.io/badge/license-proprietary%20freeware-green)](#licencia)

[Product site](https://moenium.net/tube-simulator/) · [Manual](https://moenium.net/tube-simulator/manual/1.0/es-ES/introduction.html) ·
[GitHub Releases](../../releases/latest) · [Changelog](distribution/changelog.md)

[English](README.md) · [日本語](README.ja.md) · [Deutsch](README.de-DE.md) ·
Español · [Français](README.fr-FR.md) · [Italiano](README.it-IT.md) ·
[한국어](README.ko-KR.md) · [Português](README.pt-BR.md) ·
[Русский](README.ru-RU.md) · [简体中文](README.zh-CN.md) ·
[繁體中文](README.zh-TW.md)

</div>

---

Tube Simulator es un plugin de audio para Windows que modela el comportamiento
dinámico de un amplificador de válvulas. Está disponible como componente DSP
para foobar2000 v2.x de 64 bits y como plugin VST3 para hosts de 64 bits. Ambas
versiones utilizan el mismo motor de procesamiento en tiempo real y la misma
interfaz de configuración.

<div align="center">
<img src="screenshots/tubesimulator_screenshot/tubesimulator.png" alt="Ventana de configuración de Tube Simulator" width="720">
</div>

## Funciones

- **Cuatro Characters:** Standard, Dynamic PSU, OPT Magnetic y Full Reference.
- **Drive y salida:** Input Drive y Output se ajustan de forma independiente.
- **Herramientas de nivel:** Auto Gain, Level Match y una ruta de escucha COMPARE independiente.
- **Oversampling:** procesamiento de fase lineal en Auto, 1x, 2x y 4x.
- **Perfiles de Resampler:** fase Linear / Minimum con calidades High, Standard y Light.
- **Latencia para el host:** PDC de 302, 263, 218 o 28 samples según el perfil.
- **Diagnóstico:** medidores de entrada/salida, hold, Diagnostics, About y Factory Preset.
- **Dos formatos:** componente DSP de foobar2000 y plugin VST3 de 64 bits.

## Ruta de señal

La vista **Signal Path** representa las etapas modeladas del amplificador. Los
dos controles de Character seleccionan las ramas Dynamic PSU y OPT Magnetic.

| Dynamic PSU | OPT Magnetic | Character |
| --- | --- | --- |
| Desactivado | Desactivado | Standard |
| Activado | Desactivado | Dynamic PSU |
| Desactivado | Activado | OPT Magnetic |
| Activado | Activado | Full Reference |

Input Drive y Character definen el voicing. Output, Auto Gain, Level Match,
COMPARE, Oversampling y Resampler son controles independientes.

## Requisitos

| | |
| --- | --- |
| Sistema operativo | Windows |
| Host | foobar2000 v2.x, **solo 64 bits**, o un host VST3 de 64 bits |
| CPU | x86-64 (Intel / AMD) |
| Salida | Cualquier dispositivo de audio que el host pueda abrir |
| Runtime adicional | Ninguno |

No se admiten foobar2000 de 32 bits ni hosts VST de 32 bits. Las frecuencias de
muestreo, factores de Oversampling y perfiles de Resampler de mayor calidad
requieren más CPU.

## Instalación

### Componente DSP de foobar2000

1. Cierre foobar2000.
2. Haga doble clic en `foo_dsp_tube_simulator.fb2k-component`, o abra
   **File → Preferences → Components** y elija **Install…**.
3. Seleccione **Apply**.
4. Abra **File → Preferences → Playback → DSP Manager**.
5. Mueva **Tube Simulator** a **Active DSPs**.
6. Seleccione **Configure selected**.

Instalar el componente no lo añade automáticamente a la cadena de reproducción.

### Plugin VST3

Copie `VST3/TubeSimulator.vst3` a una carpeta VST3 que el host examine y vuelva
a escanear los plugins.

### Desinstalación

En foobar2000, quite Tube Simulator de **Active DSPs** y elimine
**Tube Simulator DSP** en **Preferences → Components**. Para VST3, elimine
`TubeSimulator.vst3` de la carpeta VST3 del host y vuelva a escanear.

## Primeros pasos

Comience con **Standard** o un Factory Preset y ajuste Input Drive y Output poco a
poco. Baje el volumen de monitorización antes de cambiar Drive, Output, Character u
Oversampling, ya que pueden cambiar los picos y el volumen percibido.

Empiece con **Standard** o un Factory Preset y ajuste Input Drive y Output poco a
poco. Use **Level Match** para comparar con un nivel más cercano y **COMPARE**
para escuchar la ruta de referencia. Auto Gain y Level Match son herramientas distintas.

## Descarga y verificación

La versión más reciente está disponible en [GitHub Releases](../../releases/latest).
La página de cada versión debe incluir el nombre del archivo, las sumas SHA-256/
SHA-512 y las notas correspondientes.

En Windows PowerShell puede calcular SHA-256 con:

```powershell
Get-FileHash .\TubeSimulator_*.zip -Algorithm SHA256
```

## Documentación

- [Manual en línea y selector de idioma](https://moenium.net/tube-simulator/manual/1.0/)
- [Manual en español](https://moenium.net/tube-simulator/manual/1.0/es-ES/introduction.html)
- [Changelog](distribution/changelog.md)
- [README, EULA y avisos de terceros](distribution/)
- [Documentos de licencia de JUCE](licenses/)

## Comentarios y soporte

Se aceptan informes de errores, compatibilidad con hosts y sugerencias de traducción.

**contact@moenium.net**

Incluya la versión de Tube Simulator, el host y su versión, la frecuencia de
muestreo, Character, Oversampling, el perfil de Resampler y los pasos para
reproducir el problema. La información de Diagnostics también es útil.

## Más productos de moenium

Si busca un DSP multietapa más amplio para foobar2000, consulte
[Alauda](https://github.com/moenium-AI/Alauda).

Alauda y Tube Simulator son productos independientes.

## Apoyar Tube Simulator

Tube Simulator es gratuito y seguirá siendo gratuito. Si el plugin le resulta
útil en su cadena de escucha, puede apoyar su desarrollo mediante Ko-fi.

<p align="center">
  <a href="https://ko-fi.com/moenium">
    <img src="images/kofi_banner.jpg" alt="Apoyar Tube Simulator en Ko-fi" width="600">
  </a>
</p>

## Licencia

Tube Simulator es **freeware propietario** y puede utilizarse gratuitamente con
fines personales, profesionales y comerciales.

La redistribución, modificación, ingeniería inversa y demás condiciones se
establecen en la [EULA_en.txt](distribution/EULA_en.txt) /
[EULA_jp.txt](distribution/EULA_jp.txt) incluida. La EULA japonesa es la versión
autoritaria. Este README es solo un resumen.

Consulte los [avisos de terceros](distribution/third-party-notices.txt) para
JUCE, el SDK VST3 y el SDK de foobar2000.

---

Copyright © 2026 moenium · [moenium.net](https://moenium.net/)
