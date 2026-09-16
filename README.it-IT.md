<div align="center">

# Tube Simulator

**Plugin per il modellamento di amplificatori valvolari per Windows**

[![Piattaforma](https://img.shields.io/badge/platform-Windows%20x64-lightgrey)](#requisiti)
[![Host](https://img.shields.io/badge/host-foobar2000%20v2.x%2064--bit-orange)](https://www.foobar2000.org/)
[![Licenza](https://img.shields.io/badge/license-proprietary%20freeware-green)](#licenza)

[Product site](https://moenium.net/tube-simulator/) · [Manual](https://moenium.net/tube-simulator/manual/1.0/it-IT/introduction.html) ·
[GitHub Releases](../../releases/latest) · [Changelog](distribution/changelog.md)

[English](README.md) · [日本語](README.ja.md) · [Deutsch](README.de-DE.md) ·
[Español](README.es-ES.md) · [Français](README.fr-FR.md) · Italiano ·
[한국어](README.ko-KR.md) · [Português](README.pt-BR.md) ·
[Русский](README.ru-RU.md) · [简体中文](README.zh-CN.md) ·
[繁體中文](README.zh-TW.md)

</div>

---

Tube Simulator è un plugin audio per Windows che modella il comportamento
dinamico di un amplificatore valvolare. È disponibile come componente DSP per
foobar2000 v2.x a 64 bit e come plugin VST3 per host a 64 bit. Entrambe le
versioni usano lo stesso motore di elaborazione in tempo reale e la stessa
interfaccia di configurazione.

<div align="center">
<img src="screenshots/tubesimulator_screenshot/tubesimulator.png" alt="Finestra di configurazione di Tube Simulator" width="720">
</div>

## Funzioni

- **Quattro Character:** Standard, Dynamic PSU, OPT Magnetic e Full Reference.
- **Drive e uscita:** Input Drive e Output sono regolati separatamente.
- **Strumenti di livello:** Auto Gain, Level Match e un percorso di ascolto COMPARE indipendente.
- **Oversampling:** elaborazione a fase lineare Auto, 1x, 2x e 4x.
- **Profili Resampler:** fase Linear / Minimum con qualità High, Standard e Light.
- **Latenza gestita dall’host:** PDC di 302, 263, 218 o 28 samples in base al profilo.
- **Diagnostica:** meter di ingresso/uscita, hold, Diagnostics, About e Factory Preset.
- **Due formati:** componente DSP foobar2000 e plugin VST3 a 64 bit.

## Percorso del segnale

La vista **Signal Path** rappresenta gli stadi modellati dell’amplificatore. I
due controlli Character selezionano i rami Dynamic PSU e OPT Magnetic.

| Dynamic PSU | OPT Magnetic | Character |
| --- | --- | --- |
| Disattivato | Disattivato | Standard |
| Attivato | Disattivato | Dynamic PSU |
| Disattivato | Attivato | OPT Magnetic |
| Attivato | Attivato | Full Reference |

Input Drive e Character definiscono il voicing. Output, Auto Gain, Level Match,
COMPARE, Oversampling e Resampler sono controlli indipendenti.

## Requisiti

| | |
| --- | --- |
| Sistema operativo | Windows |
| Host | foobar2000 v2.x, **solo 64 bit**, oppure un host VST3 a 64 bit |
| CPU | x86-64 (Intel / AMD) |
| Uscita | Qualsiasi dispositivo audio che l’host possa aprire |
| Runtime aggiuntivo | Nessuno |

foobar2000 a 32 bit e gli host VST a 32 bit non sono supportati. Frequenze di
campionamento, fattori di Oversampling e profili Resampler di qualità più alta
richiedono più CPU.

## Installazione

### Componente DSP foobar2000

1. Chiudere foobar2000.
2. Fare doppio clic su `foo_dsp_tube_simulator.fb2k-component`, oppure aprire
   **File → Preferences → Components** e scegliere **Install…**.
3. Selezionare **Apply**.
4. Aprire **File → Preferences → Playback → DSP Manager**.
5. Spostare **Tube Simulator** in **Active DSPs**.
6. Selezionare **Configure selected**.

L’installazione da sola non aggiunge il componente alla catena di riproduzione.

### Plugin VST3

Copiare `VST3/TubeSimulator.vst3` in una cartella VST3 analizzata dall’host, poi
eseguire una nuova scansione dei plugin.

### Disinstallazione

In foobar2000, rimuovere Tube Simulator da **Active DSPs** e cancellare
**Tube Simulator DSP** in **Preferences → Components**. Per VST3, rimuovere
`TubeSimulator.vst3` dalla cartella VST3 dell’host e ripetere la scansione.

## Primi passi

Iniziare con **Standard** o con un Factory Preset, quindi regolare lentamente
Input Drive e Output. Abbassare il volume di ascolto prima di modificare Drive, Output, Character o
Oversampling, perché possono cambiare i picchi e il volume percepito.

Iniziare con **Standard** o con un Factory Preset, quindi regolare lentamente
Input Drive e Output. Usare **Level Match** per un confronto a volume più vicino
e **COMPARE** per ascoltare il percorso di riferimento. Auto Gain e Level Match
sono strumenti diversi.

## Download e verifica

La versione più recente è disponibile su [GitHub Releases](../../releases/latest).
Ogni pagina di release dovrebbe indicare il nome del file, i checksum SHA-256/
SHA-512 e le note relative.

In Windows PowerShell è possibile calcolare SHA-256 con:

```powershell
Get-FileHash .\TubeSimulator_*.zip -Algorithm SHA256
```

## Documentazione

- [Manuale online e selezione della lingua](https://moenium.net/tube-simulator/manual/1.0/)
- [Manuale in italiano](https://moenium.net/tube-simulator/manual/1.0/it-IT/introduction.html)
- [Changelog](distribution/changelog.md)
- [README, EULA e avvisi di terze parti](distribution/)
- [Documenti sulle licenze JUCE](licenses/)

## Feedback e assistenza

Sono benvenute segnalazioni di bug, compatibilità con gli host e suggerimenti
sulle traduzioni.

**contact@moenium.net**

Indicare la versione di Tube Simulator, l’host e la relativa versione, la
frequenza di campionamento, Character, Oversampling, il profilo Resampler e i
passaggi per riprodurre il problema. Sono utili anche i dati di Diagnostics.

## Altri software di moenium

Se si cerca un DSP multi-stage più ampio per foobar2000, vedere
[Alauda](https://github.com/moenium-AI/Alauda).

Alauda e Tube Simulator sono prodotti distinti.

## Supportare Tube Simulator

Tube Simulator è gratuito e resterà gratuito. Se il plugin è diventato parte
della propria catena di ascolto, è possibile sostenere il suo sviluppo tramite Ko-fi.

<p align="center">
  <a href="https://ko-fi.com/moenium">
    <img src="images/kofi_banner.jpg" alt="Supportare Tube Simulator su Ko-fi" width="600">
  </a>
</p>

## Licenza

Tube Simulator è **freeware proprietario** e può essere utilizzato gratuitamente
per scopi personali, professionali e commerciali.

Redistribuzione, modifica, reverse engineering e altre condizioni sono stabiliti
nella [EULA_en.txt](distribution/EULA_en.txt) /
[EULA_jp.txt](distribution/EULA_jp.txt) inclusa. Fa fede l’EULA giapponese.
Questo README è solo un riepilogo.

Per JUCE, il VST3 SDK e il foobar2000 SDK, consultare gli [avvisi di terze parti](distribution/third-party-notices.txt).

---

Copyright © 2026 moenium · [moenium.net](https://moenium.net/)
