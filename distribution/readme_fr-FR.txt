================================================================
 Tube Simulator Version 1.0.0
================================================================

Plug-in audio pour Windows
DSP foobar2000 / VST3

  Copyright (C) 2026 moenium
  Date de sortie : 2026-09-16


----------------------------------------------------------------
 1. Présentation
----------------------------------------------------------------

Tube Simulator est un plug-in audio pour Windows qui modélise le comportement
dynamique d’un amplificateur à tubes. Il fournit un composant DSP 64 bits pour
foobar2000 v2.x et un plug-in VST3 64 bits. Les deux utilisent le même panneau
de commande et le même Realtime Core partagé.

Ses principales fonctions sont les suivantes :

  - Quatre Characters : Standard, Dynamic PSU, OPT Magnetic, Full Reference
  - Input Drive, Output, Auto Gain et Level Match
  - COMPARE, indépendant de Level Match
  - Suréchantillonnage à phase linéaire Auto / 1x / 2x / 4x
  - Latence de traitement de 302 frames avec le profil par défaut Linear /
    High Quality
  - PDC selon le profil : 302 / 263 / 218 frames pour Linear High / Standard /
    Light, et 28 frames pour Minimum
  - 44,1 / 48 / 88,2 / 96 / 176,4 / 192 kHz
  - Fonctionnement mono et stéréo
  - Factory Presets, indicateurs d’entrée/sortie, Diagnostics et About

Les noms 310A, 300B et 274B sont utilisés uniquement comme références techniques
et historiques de types. Leur utilisation n’implique aucune affiliation,
approbation, promotion ni recommandation par une entreprise ou une marque
particulière.


----------------------------------------------------------------
 2. Conditions de distribution
----------------------------------------------------------------

Freeware. Gratuit pour un usage personnel, professionnel et commercial.

Les Factory Presets sont inclus dans l’interface de Tube Simulator. Cette version
ne contient pas de pack de presets séparé. Enregistrez et chargez les presets à
l’aide des fonctions fournies par le plug-in ou l’hôte.

Les conditions de redistribution, de modification, de rétro-ingénierie et de
toute autre utilisation sont définies dans les EULA joints, EULA_jp.txt /
EULA_en.txt. Ce README est un simple résumé et ne modifie pas l’EULA.


----------------------------------------------------------------
 3. Configuration requise
----------------------------------------------------------------

  Système : Windows 64 bits
  Hôte    : foobar2000 v2.x (64 bits) ou un hôte VST3 64 bits
  CPU     : x86-64 (Intel / AMD)
  Sortie  : Tout périphérique audio que l’hôte peut ouvrir

Logiciel supplémentaire : aucun

foobar2000 32 bits et les hôtes VST 32 bits ne sont pas pris en charge. Les
fréquences d’échantillonnage et facteurs de suréchantillonnage élevés augmentent
la charge CPU. Si le profil du Resampler est modifié, la PDC est de 302 / 263 /
218 frames pour Linear High / Standard / Light et de 28 frames pour Minimum.


----------------------------------------------------------------
 4. Installation
----------------------------------------------------------------

DSP foobar2000 :

  1. Quittez foobar2000.
  2. Double-cliquez sur le fichier fourni
     foo_dsp_tube_simulator.fb2k-component.
     (Ou ouvrez File > Preferences > Components et choisissez Install...)
  3. Sélectionnez Apply pour terminer l’installation.

L’installation n’ajoute pas automatiquement le plug-in à la chaîne de lecture.
Ouvrez File > Preferences > Playback > DSP Manager, déplacez "Tube Simulator"
dans Active DSPs et utilisez Configure selected pour ouvrir la fenêtre de réglage.

VST3 :

Copiez le dossier fourni VST3\\TubeSimulator.vst3 dans un dossier de plug-ins
VST3 analysé par votre hôte, puis relancez l’analyse. L’archive contient le
binaire Windows x86_64.


----------------------------------------------------------------
 5. Prise en main
----------------------------------------------------------------

La fenêtre de réglage comprend Input, Output, Character, Oversampling, Resampler
profile, Auto Gain, Level Match, COMPARE, Factory Preset, Diagnostics et About.

Commencez avec un faible volume de lecture et réglez progressivement, en partant
de Standard ou d’un Factory Preset. Auto Gain et Level Match ajustent le niveau ;
ce ne sont pas des limiteurs de sécurité.


----------------------------------------------------------------
 6. Désinstallation
----------------------------------------------------------------

DSP foobar2000 :

  1. Ouvrez File > Preferences > Playback > DSP Manager et retirez
     "Tube Simulator" de Active DSPs.
  2. Ouvrez File > Preferences > Components, sélectionnez "Tube Simulator DSP"
     et supprimez-le.
  3. Sélectionnez Apply et redémarrez foobar2000.

VST3 :

Supprimez le dossier TubeSimulator.vst3 du dossier de plug-ins VST3 utilisé par
votre hôte, puis relancez l’analyse des plug-ins.

Si des réglages ou caches de l’hôte subsistent, utilisez la gestion des réglages
proposée par l’hôte.


----------------------------------------------------------------
 7. Remarques d’utilisation
----------------------------------------------------------------

[Niveau de lecture]

Input Drive, Output, Auto Gain, Level Match et COMPARE peuvent modifier le niveau
de crête ou le volume perçu. Commencez avec un faible volume et gérez vous-même
le niveau final ainsi que la protection de votre audition et de votre matériel.

[Suréchantillonnage et profils du Resampler]

Les facteurs élevés et les profils de meilleure qualité utilisent davantage de
CPU. En VST3, un changement de profil est reflété dans la PDC après le prochain
prepare ou redémarrage de l’hôte. Le taux de traitement réellement fourni par
l’hôte peut être vérifié dans Diagnostics, sous HOST RATE.

[Emplacement des réglages]

Les réglages sont enregistrés dans le profil foobar2000 ou dans la gestion du
projet/de l’état de l’hôte VST3. Les réglages utilisateur ne sont pas inclus
dans l’archive de version.

[Comportement en silence]

En raison du traitement du modèle de tube et du contrat de queue de l’hôte, le
silence numérique n’est pas nécessairement égal à zéro mathématique.


----------------------------------------------------------------
 8. Licence
----------------------------------------------------------------

Tube Simulator : freeware propriétaire

  Gratuit pour un usage personnel, professionnel et commercial. Les conditions
  de redistribution, de modification, de rétro-ingénierie et de toute autre
  utilisation sont définies dans EULA_jp.txt / EULA_en.txt.

Logiciels inclus :

  - JUCE 9.0.1 (licence JUCE 9 Starter) : Raw Material Software Limited
    Utilisé pour construire l’interface de Tube Simulator, l’implémentation VST3
    et l’UI associée. Le JUCE 9 End User Licence Agreement s’applique, et non la
    licence propre de Tube Simulator.

  - Steinberg VST 3 SDK
    Le SDK fourni dans l’arbre source de JUCE 9.0.1 est utilisé pour la
    compilation VST3. Consultez third-party-notices.txt pour sa licence et les
    conditions relatives aux marques VST.

  - foobar2000 SDK (conditions propres au projet foobar2000)
    Utilisé pour créer le composant foobar2000. foobar2000 ne fait pas partie de
    Tube Simulator et n’est pas distribué avec celui-ci.

  Consultez licenses/JUCE_LICENSE.md et licenses/JUCE_EMBEDDED_LICENSES.md pour
  le résumé de la licence JUCE et les textes complets des composants intégrés.
  Consultez third-party-notices.txt pour les autres détails de licence.


----------------------------------------------------------------
 9. Contact et assistance
----------------------------------------------------------------

  Auteur      : moenium
  Site web    : https://moenium.net/
  Contact     : contact@moenium.net

Pour toute demande ou tout rapport de problème, écrivez à l’adresse ci-dessus.

Indiquez la version de Tube Simulator, la version de l’hôte foobar2000 ou VST3,
la fréquence d’échantillonnage, Character, Oversampling, Resampler profile et
les étapes de reproduction. La sortie de Diagnostics et les journaux de l’hôte
sont également utiles.


----------------------------------------------------------------
 10. Historique des modifications
----------------------------------------------------------------

Consultez le fichier changelog.md fourni pour connaître les modifications de
chaque version.


================================================================
================================================================
