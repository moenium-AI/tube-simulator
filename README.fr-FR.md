<div align="center">

# Tube Simulator

**Plug-in de modélisation d’amplificateur à lampes pour Windows**

[![Plateforme](https://img.shields.io/badge/platform-Windows%20x64-lightgrey)](#configuration-requise)
[![Hôte](https://img.shields.io/badge/host-foobar2000%20v2.x%2064--bit-orange)](https://www.foobar2000.org/)
[![Licence](https://img.shields.io/badge/license-proprietary%20freeware-green)](#licence)

[Product site](https://moenium.net/tube-simulator/) · [Manual](https://moenium.net/tube-simulator/manual/1.0/fr-FR/introduction.html) ·
[GitHub Releases](../../releases/latest) · [Changelog](distribution/changelog.md)

[English](README.md) · [日本語](README.ja.md) · [Deutsch](README.de-DE.md) ·
[Español](README.es-ES.md) · Français · [Italiano](README.it-IT.md) ·
[한국어](README.ko-KR.md) · [Português](README.pt-BR.md) ·
[Русский](README.ru-RU.md) · [简体中文](README.zh-CN.md) ·
[繁體中文](README.zh-TW.md)

</div>

---

Tube Simulator est un plug-in audio Windows qui modélise le comportement
dynamique d’un amplificateur à lampes. Il existe sous forme de composant DSP
pour foobar2000 v2.x 64 bits et de plug-in VST3 pour les hôtes 64 bits. Les deux
versions utilisent le même moteur temps réel et la même interface de réglage.

<div align="center">
<img src="screenshots/tubesimulator_screenshot/tubesimulator.png" alt="Fenêtre de configuration de Tube Simulator" width="720">
</div>

## Fonctionnalités

- **Quatre Characters :** Standard, Dynamic PSU, OPT Magnetic et Full Reference.
- **Drive et sortie :** Input Drive et Output sont réglés séparément.
- **Outils de niveau :** Auto Gain, Level Match et une écoute COMPARE indépendante.
- **Oversampling :** traitement à phase linéaire en Auto, 1x, 2x et 4x.
- **Profils Resampler :** phase Linear / Minimum et qualités High, Standard et Light.
- **Latence gérée par l’hôte :** PDC de 302, 263, 218 ou 28 samples selon le profil.
- **Diagnostic :** vumètres d’entrée/sortie, hold, Diagnostics, About et Factory Preset.
- **Deux formats :** composant DSP foobar2000 et plug-in VST3 64 bits.

## Chemin du signal

La vue **Signal Path** représente les étages modélisés de l’amplificateur. Les
deux commandes Character sélectionnent les branches Dynamic PSU et OPT Magnetic.

| Dynamic PSU | OPT Magnetic | Character |
| --- | --- | --- |
| Désactivé | Désactivé | Standard |
| Activé | Désactivé | Dynamic PSU |
| Désactivé | Activé | OPT Magnetic |
| Activé | Activé | Full Reference |

Input Drive et Character définissent le voicing. Output, Auto Gain, Level Match,
COMPARE, Oversampling et Resampler sont des commandes indépendantes.

## Configuration requise

| | |
| --- | --- |
| Système | Windows |
| Hôte | foobar2000 v2.x, **64 bits uniquement**, ou hôte VST3 64 bits |
| CPU | x86-64 (Intel / AMD) |
| Sortie | Tout périphérique audio que l’hôte peut ouvrir |
| Runtime supplémentaire | Aucun |

foobar2000 32 bits et les hôtes VST 32 bits ne sont pas pris en charge. Les
fréquences d’échantillonnage, facteurs d’Oversampling et profils Resampler de
qualité élevée consomment davantage de CPU.

## Installation

### Composant DSP foobar2000

1. Fermez foobar2000.
2. Double-cliquez sur `foo_dsp_tube_simulator.fb2k-component`, ou ouvrez
   **File → Preferences → Components** et choisissez **Install…**.
3. Sélectionnez **Apply**.
4. Ouvrez **File → Preferences → Playback → DSP Manager**.
5. Déplacez **Tube Simulator** dans **Active DSPs**.
6. Sélectionnez **Configure selected**.

L’installation seule n’ajoute pas le composant à la chaîne de lecture.

### Plug-in VST3

Copiez `VST3/TubeSimulator.vst3` dans un dossier VST3 analysé par l’hôte, puis
relancez l’analyse des plug-ins.

### Désinstallation

Dans foobar2000, retirez Tube Simulator de **Active DSPs**, puis supprimez
**Tube Simulator DSP** dans **Preferences → Components**. Pour VST3, supprimez
`TubeSimulator.vst3` du dossier VST3 de l’hôte et relancez l’analyse.

## Premiers pas

Commencez avec **Standard** ou un Factory Preset, puis réglez progressivement
Input Drive et Output. Baissez le niveau d’écoute avant de modifier Drive, Output, Character ou
Oversampling : ces réglages peuvent modifier les crêtes et le niveau perçu.

Commencez avec **Standard** ou un Factory Preset, puis réglez progressivement
Input Drive et Output. Utilisez **Level Match** pour comparer à niveau proche et
**COMPARE** pour écouter le chemin de référence. Auto Gain et Level Match sont
deux outils différents.

## Téléchargement et vérification

La version actuelle est disponible sur [GitHub Releases](../../releases/latest).
Chaque page de version doit indiquer le nom du fichier, les sommes SHA-256/SHA-512
et les notes associées.

Sous Windows PowerShell, calculez SHA-256 avec :

```powershell
Get-FileHash .\TubeSimulator_*.zip -Algorithm SHA256
```

## Documentation

- [Manuel en ligne et choix de la langue](https://moenium.net/tube-simulator/manual/1.0/)
- [Manuel en français](https://moenium.net/tube-simulator/manual/1.0/fr-FR/introduction.html)
- [Changelog](distribution/changelog.md)
- [README, EULA et avis de tiers](distribution/)
- [Documents de licence JUCE](licenses/)

## Retours et assistance

Les rapports de bugs, de compatibilité avec les hôtes et les suggestions de
traduction sont les bienvenus.

**contact@moenium.net**

Indiquez la version de Tube Simulator, l’hôte et sa version, la fréquence
d’échantillonnage, Character, Oversampling, le profil Resampler et les étapes de
reproduction. Les informations de Diagnostics sont également utiles.

## Les autres logiciels de moenium

Si vous cherchez un DSP multi-étapes plus complet pour foobar2000, consultez
[Alauda](https://github.com/moenium-AI/Alauda).

Alauda et Tube Simulator sont deux produits distincts.

## Soutenir Tube Simulator

Tube Simulator est gratuit et le restera. Si le plug-in vous accompagne dans
votre chaîne d’écoute, vous pouvez soutenir son développement via Ko-fi.

<p align="center">
  <a href="https://ko-fi.com/moenium">
    <img src="images/kofi_banner.jpg" alt="Soutenir Tube Simulator sur Ko-fi" width="600">
  </a>
</p>

## Licence

Tube Simulator est un **freeware propriétaire** utilisable gratuitement à des
fins personnelles, professionnelles et commerciales.

La redistribution, la modification, la rétro-ingénierie et les autres conditions
sont définies par l’[EULA_en.txt](distribution/EULA_en.txt) /
[EULA_jp.txt](distribution/EULA_jp.txt) fournie. L’EULA japonaise fait foi. Ce
README est uniquement un résumé.

Consultez les [avis de tiers](distribution/third-party-notices.txt) pour JUCE,
le SDK VST3 et le SDK foobar2000.

---

Copyright © 2026 moenium · [moenium.net](https://moenium.net/)
