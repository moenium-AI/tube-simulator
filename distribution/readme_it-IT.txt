================================================================
 Tube Simulator Versione 1.0.0
================================================================

Plug-in audio per Windows
DSP foobar2000 / VST3

  Copyright (C) 2026 moenium
  Data di rilascio : 2026-09-16


----------------------------------------------------------------
 1. Panoramica
----------------------------------------------------------------

Tube Simulator è un plug-in audio per Windows che modella il comportamento
dinamico di un amplificatore a valvole. Fornisce un componente DSP a 64 bit per
foobar2000 v2.x e un plug-in VST3 a 64 bit. Entrambi usano lo stesso pannello di
controllo e lo stesso Realtime Core condiviso.

Le funzioni principali sono:

  - Quattro Characters: Standard, Dynamic PSU, OPT Magnetic, Full Reference
  - Input Drive, Output, Auto Gain e Level Match
  - COMPARE, indipendente da Level Match
  - Oversampling a fase lineare Auto / 1x / 2x / 4x
  - Latenza di elaborazione di 302 frames con il profilo predefinito Linear /
    High Quality
  - PDC per profilo: 302 / 263 / 218 frames per Linear High / Standard / Light,
    e 28 frames per Minimum
  - 44,1 / 48 / 88,2 / 96 / 176,4 / 192 kHz
  - Funzionamento mono e stereo
  - Factory Presets, indicatori di ingresso/uscita, Diagnostics e About

I nomi 310A, 300B e 274B sono utilizzati esclusivamente come riferimenti
tecnici e storici ai tipi. Il loro utilizzo non implica alcuna affiliazione,
approvazione, sponsorizzazione o raccomandazione da parte di una specifica
azienda o marca.


----------------------------------------------------------------
 2. Condizioni di distribuzione
----------------------------------------------------------------

Freeware. Gratuito per uso personale, professionale e commerciale.

I Factory Presets sono inclusi nell’interfaccia di Tube Simulator. Questa release
non include un pacchetto di preset separato. Salvare e caricare i preset usando
le funzioni fornite dal plug-in o dall’host.

Le condizioni di ridistribuzione, modifica, reverse engineering e ogni altro
utilizzo sono stabilite negli EULA allegati, EULA_jp.txt / EULA_en.txt. Questo
README è solo un riepilogo e non modifica l’EULA.


----------------------------------------------------------------
 3. Requisiti
----------------------------------------------------------------

  Sistema operativo : Windows a 64 bit
  Host              : foobar2000 v2.x (64 bit) o un host VST3 a 64 bit
  CPU               : x86-64 (Intel / AMD)
  Uscita            : Qualsiasi dispositivo audio che l’host possa aprire

Software aggiuntivo: nessuno

foobar2000 a 32 bit e gli host VST a 32 bit non sono supportati. Frequenze di
campionamento e fattori di Oversampling più elevati aumentano il carico della
CPU. Se si cambia il profilo del Resampler, la PDC è di 302 / 263 / 218 frames
per Linear High / Standard / Light e di 28 frames per Minimum.


----------------------------------------------------------------
 4. Installazione
----------------------------------------------------------------

DSP foobar2000:

  1. Chiudere foobar2000.
  2. Fare doppio clic sul file incluso
     foo_dsp_tube_simulator.fb2k-component.
     (Oppure aprire File > Preferences > Components e scegliere Install...)
  3. Selezionare Apply per completare l’installazione.

L’installazione non inserisce automaticamente il plug-in nella catena di
riproduzione. Aprire File > Preferences > Playback > DSP Manager, spostare
"Tube Simulator" in Active DSPs e usare Configure selected per aprire la finestra
delle impostazioni.

VST3:

Copiare la cartella inclusa VST3\\TubeSimulator.vst3 in una cartella di plug-in
VST3 analizzata dall’host, quindi eseguire nuovamente la scansione. L’archivio
contiene il binario Windows x86_64.


----------------------------------------------------------------
 5. Primi passi
----------------------------------------------------------------

La finestra delle impostazioni include Input, Output, Character, Oversampling,
Resampler profile, Auto Gain, Level Match, COMPARE, Factory Preset, Diagnostics
e About.

Iniziare con un volume di riproduzione basso e regolare gradualmente, partendo da
Standard o da un Factory Preset. Auto Gain e Level Match regolano il livello; non
sono limitatori di sicurezza.


----------------------------------------------------------------
 6. Disinstallazione
----------------------------------------------------------------

DSP foobar2000:

  1. Aprire File > Preferences > Playback > DSP Manager e rimuovere
     "Tube Simulator" da Active DSPs.
  2. Aprire File > Preferences > Components, selezionare "Tube Simulator DSP"
     e rimuoverlo.
  3. Selezionare Apply e riavviare foobar2000.

VST3:

Eliminare la cartella TubeSimulator.vst3 dalla cartella VST3 usata dall’host,
quindi eseguire nuovamente la scansione dei plug-in.

Se rimangono impostazioni o cache dell’host, usare la gestione delle impostazioni
fornita dall’host stesso.


----------------------------------------------------------------
 7. Note sull’uso
----------------------------------------------------------------

[Livello di riproduzione]

Input Drive, Output, Auto Gain, Level Match e COMPARE possono cambiare il livello
di picco o il volume percepito. Iniziare con un volume basso e gestire
personalmente il livello finale, la sicurezza dell’udito e quella dell’apparecchio.

[Oversampling e profili del Resampler]

Fattori più elevati e profili di qualità superiore usano più CPU. In VST3, una
modifica del profilo viene riflessa nella PDC dopo il successivo prepare o riavvio
dell’host. La frequenza di elaborazione effettivamente fornita dall’host può
essere controllata in Diagnostics alla voce HOST RATE.

[Dove vengono salvate le impostazioni]

Le impostazioni vengono salvate nel profilo di foobar2000 o nella gestione del
progetto/stato dell’host VST3. Le impostazioni dell’utente non sono incluse
nell’archivio di rilascio.

[Comportamento in assenza di segnale]

A causa dell’elaborazione del modello valvolare e del contratto di coda dell’host,
il silenzio digitale non è necessariamente matematicamente uguale a zero.


----------------------------------------------------------------
 8. Licenza
----------------------------------------------------------------

Tube Simulator: freeware proprietario

  Gratuito per uso personale, professionale e commerciale. Le condizioni di
  ridistribuzione, modifica, reverse engineering e ogni altro utilizzo sono
  stabilite in EULA_jp.txt / EULA_en.txt.

Software incluso:

  - JUCE 9.0.1 (licenza JUCE 9 Starter): Raw Material Software Limited
    Utilizzato per creare l’interfaccia di Tube Simulator, l’implementazione VST3
    e la UI collegata. Si applicano i termini del JUCE 9 End User Licence
    Agreement, non la licenza propria di Tube Simulator.

  - Steinberg VST 3 SDK
    L’SDK incluso nell’albero dei sorgenti di JUCE 9.0.1 viene usato per la build
    VST3. Consultare third-party-notices.txt per la licenza e i termini relativi
    ai marchi VST.

  - foobar2000 SDK (termini propri del progetto foobar2000)
    Usato per creare il componente foobar2000. foobar2000 non fa parte di Tube
    Simulator e non viene distribuito con esso.

  Consultare licenses/JUCE_LICENSE.md e licenses/JUCE_EMBEDDED_LICENSES.md per
  il riepilogo della licenza JUCE e i testi completi dei componenti incorporati.
  Per gli altri dettagli sulle licenze, consultare third-party-notices.txt.


----------------------------------------------------------------
 9. Contatti e supporto
----------------------------------------------------------------

  Autore       : moenium
  Sito web     : https://moenium.net/
  Contatto     : contact@moenium.net

Per contatti e segnalazioni di bug, scrivere all’indirizzo sopra indicato.

Indicare la versione di Tube Simulator, la versione dell’host foobar2000 o VST3,
la frequenza di campionamento, Character, Oversampling, Resampler profile e i
passaggi per riprodurre il problema. Sono utili anche l’output di Diagnostics
e i log dell’host.


----------------------------------------------------------------
 10. Registro delle modifiche
----------------------------------------------------------------

Per le modifiche di ogni versione, consultare il changelog.md incluso.


================================================================
================================================================
