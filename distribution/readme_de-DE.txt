================================================================
 Tube Simulator Version 1.0.0
================================================================

Windows-Audio-Plug-in
foobar2000-DSP / VST3

  Copyright (C) 2026 moenium
  Veröffentlichungsdatum : 2026-09-16


----------------------------------------------------------------
 1. Übersicht
----------------------------------------------------------------

Tube Simulator ist ein Windows-Audio-Plug-in, das das dynamische Verhalten
eines Röhrenverstärkers modelliert. Es bietet eine 64-Bit-DSP-Komponente für
foobar2000 v2.x und ein 64-Bit-VST3-Plug-in. Beide verwenden dasselbe Bedienfeld
und denselben gemeinsamen Realtime Core.

Die wichtigsten Funktionen:

  - Vier Characters: Standard, Dynamic PSU, OPT Magnetic, Full Reference
  - Input Drive, Output, Auto Gain und Level Match
  - Von Level Match unabhängiges COMPARE
  - Linear-Phase-Oversampling mit Auto / 1x / 2x / 4x
  - 302 Frames Verarbeitungslatenz mit dem Standardprofil Linear / High Quality
  - PDC je Profil: Linear High / Standard / Light mit 302 / 263 / 218 Frames,
    Minimum mit 28 Frames
  - 44,1 / 48 / 88,2 / 96 / 176,4 / 192 kHz
  - Mono- und Stereobetrieb
  - Factory Presets, Eingangs-/Ausgangsanzeigen, Diagnostics und About

Die Bezeichnungen 310A, 300B und 274B werden ausschließlich als technische und
historische Typenbezeichnungen verwendet. Ihre Verwendung bedeutet keine
Verbindung, Genehmigung, Förderung oder Empfehlung durch ein bestimmtes
Unternehmen oder eine bestimmte Marke.


----------------------------------------------------------------
 2. Vertriebsbedingungen
----------------------------------------------------------------

Freeware. Kostenlose Nutzung für private, berufliche und kommerzielle Zwecke.

Factory Presets sind in der Tube-Simulator-Oberfläche enthalten. Dieses Release
enthält kein separates Preset Pack. Speichern und laden Sie Presets mit den vom
Plug-in oder Host bereitgestellten Funktionen.

Bedingungen für Weitergabe, Änderung, Reverse Engineering und jede andere
Nutzung sind in der beiliegenden EULA_jp.txt / EULA_en.txt festgelegt. Diese
README ist nur eine Zusammenfassung und ändert die EULA nicht.


----------------------------------------------------------------
 3. Systemanforderungen
----------------------------------------------------------------

  Betriebssystem : Windows 64-Bit
  Host           : foobar2000 v2.x (64-Bit) oder ein 64-Bit-VST3-Host
  CPU            : x86-64 (Intel / AMD)
  Ausgabe        : Jedes Audiogerät, das der Host öffnen kann

Zusätzliche Software: nicht erforderlich

32-Bit-foobar2000 und 32-Bit-VST-Hosts werden nicht unterstützt. Höhere
Abtastraten und Oversampling-Faktoren erhöhen die CPU-Last. Bei Änderung des
Resampler-Profils beträgt die PDC 302 / 263 / 218 Frames für Linear High /
Standard / Light und 28 Frames für Minimum.


----------------------------------------------------------------
 4. Installation
----------------------------------------------------------------

foobar2000-DSP:

  1. Beenden Sie foobar2000.
  2. Doppelklicken Sie auf die beiliegende
     foo_dsp_tube_simulator.fb2k-component-Datei.
     (Oder öffnen Sie File > Preferences > Components und wählen Sie Install...)
  3. Wählen Sie Apply, um die Installation abzuschließen.

Durch die Installation wird das Plug-in nicht automatisch in die Wiedergabekette
aufgenommen. Öffnen Sie File > Preferences > Playback > DSP Manager, verschieben
Sie "Tube Simulator" nach Active DSPs und öffnen Sie mit Configure selected das
Einstellungsfenster.

VST3:

Kopieren Sie den beiliegenden Ordner VST3\\TubeSimulator.vst3 in einen vom Host
gescannten VST3-Plug-in-Ordner und starten Sie anschließend einen erneuten Scan.
Das Archiv enthält die Windows-x86_64-Binärdatei.


----------------------------------------------------------------
 5. Erste Schritte
----------------------------------------------------------------

Das Einstellungsfenster enthält Input, Output, Character, Oversampling,
Resampler profile, Auto Gain, Level Match, COMPARE, Factory Preset,
Diagnostics und About.

Beginnen Sie mit geringer Wiedergabelautstärke und erhöhen Sie die Einstellungen
schrittweise, zunächst mit Standard oder einem Factory Preset. Auto Gain und
Level Match passen den Pegel an; sie sind keine Sicherheitsbegrenzer.


----------------------------------------------------------------
 6. Deinstallation
----------------------------------------------------------------

foobar2000-DSP:

  1. Öffnen Sie File > Preferences > Playback > DSP Manager und verschieben
     Sie "Tube Simulator" aus Active DSPs.
  2. Öffnen Sie File > Preferences > Components, wählen Sie "Tube Simulator DSP"
     und entfernen Sie es.
  3. Wählen Sie Apply und starten Sie foobar2000 neu.

VST3:

Löschen Sie den Ordner TubeSimulator.vst3 aus dem vom Host verwendeten VST3-
Plug-in-Ordner und starten Sie einen erneuten Scan.

Falls Host-Einstellungen oder Caches zurückbleiben, verwenden Sie die eigene
Einstellungsverwaltung des Hosts.


----------------------------------------------------------------
 7. Hinweise zur Verwendung
----------------------------------------------------------------

[Wiedergabelautstärke]

Input Drive, Output, Auto Gain, Level Match und COMPARE können Spitzenpegel oder
die wahrgenommene Lautstärke verändern. Beginnen Sie mit geringer Lautstärke und
verwalten Sie Endpegel sowie den Schutz von Gehör und Geräten selbst.

[Oversampling- und Resampler-Profile]

Höhere Faktoren und höhere Qualitätsprofile benötigen mehr CPU. In VST3 wird eine
Profiländerung nach dem nächsten Host-Prepare oder Neustart in der PDC wirksam.
Die tatsächliche vom Host bereitgestellte Verarbeitungsrate kann in Diagnostics
unter HOST RATE geprüft werden.

[Speicherort der Einstellungen]

Einstellungen werden im foobar2000-Profil oder in der Projekt-/State-Verwaltung
des VST3-Hosts gespeichert. Benutzereinstellungen sind nicht im Release-Archiv
enthalten.

[Verhalten bei Stille]

Aufgrund der Röhrenmodellverarbeitung und des Tail-Vertrags des Hosts ist digitale
Stille nicht notwendigerweise mathematisch exakt null.


----------------------------------------------------------------
 8. Lizenz
----------------------------------------------------------------

Tube Simulator: proprietäre Freeware

  Kostenlose Nutzung für private, berufliche und kommerzielle Zwecke. Bedingungen
  für Weitergabe, Änderung, Reverse Engineering und jede andere Nutzung sind in
  der beiliegenden EULA_jp.txt / EULA_en.txt festgelegt.

Enthaltene Software:

  - JUCE 9.0.1 (JUCE 9 Starter-Lizenz): Raw Material Software Limited
    Verwendet für die Tube-Simulator-Oberfläche, die VST3-Implementierung und
    zugehörige UI. Es gelten die Bedingungen der JUCE 9 End User Licence
    Agreement, nicht die eigene Lizenz von Tube Simulator.

  - Steinberg VST 3 SDK
    Das im JUCE-9.0.1-Quellbaum enthaltene SDK wird für den VST3-Build verwendet.
    Die Lizenz- und VST-Markenbedingungen stehen in third-party-notices.txt.

  - foobar2000 SDK (eigene Bedingungen des foobar2000-Projekts)
    Verwendet zum Erstellen der foobar2000-Komponente. foobar2000 selbst ist kein
    Bestandteil von Tube Simulator und wird nicht mitgeliefert.

  Siehe licenses/JUCE_LICENSE.md und licenses/JUCE_EMBEDDED_LICENSES.md für die
  JUCE-Lizenzübersicht und die vollständigen Texte der eingebetteten Komponenten.
  Weitere Lizenzdetails finden Sie in third-party-notices.txt.


----------------------------------------------------------------
 9. Kontakt und Support
----------------------------------------------------------------

  Autor          : moenium
  Website        : https://moenium.net/
  Kontakt        : contact@moenium.net

Für Kontaktaufnahmen und Fehlerberichte senden Sie bitte eine E-Mail an die
oben genannte Adresse.

Bitte geben Sie die Tube-Simulator-Version, die foobar2000- oder VST3-Hostversion,
Abtastrate, Character, Oversampling, Resampler profile und die Schritte zur
Reproduktion an. Diagnostics-Ausgaben und Host-Logs sind ebenfalls hilfreich.


----------------------------------------------------------------
 10. Änderungsverlauf
----------------------------------------------------------------

Änderungen der einzelnen Versionen finden Sie in der beiliegenden changelog.md.


================================================================
================================================================
