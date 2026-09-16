================================================================
 Tube Simulator Versión 1.0.0
================================================================

Complemento de audio para Windows
DSP para foobar2000 / VST3

  Copyright (C) 2026 moenium
  Fecha de lanzamiento : 2026-09-16


----------------------------------------------------------------
 1. Descripción general
----------------------------------------------------------------

Tube Simulator es un complemento de audio para Windows que modela el
comportamiento dinámico de un amplificador de válvulas. Ofrece un componente
DSP de 64 bits para foobar2000 v2.x y un complemento VST3 de 64 bits. Ambos
utilizan el mismo panel de control y el mismo Realtime Core compartido.

Sus funciones principales son:

  - Cuatro Characters: Standard, Dynamic PSU, OPT Magnetic, Full Reference
  - Input Drive, Output, Auto Gain y Level Match
  - COMPARE, independiente de Level Match
  - Oversampling de fase lineal Auto / 1x / 2x / 4x
  - Latencia de procesamiento de 302 frames con el perfil predeterminado
    Linear / High Quality
  - PDC por perfil: 302 / 263 / 218 frames para Linear High / Standard / Light,
    y 28 frames para Minimum
  - 44,1 / 48 / 88,2 / 96 / 176,4 / 192 kHz
  - Funcionamiento mono y estéreo
  - Factory Presets, medidores de entrada/salida, Diagnostics y About

Los nombres 310A, 300B y 274B se utilizan únicamente como referencias técnicas
e históricas de tipos. Su uso no implica afiliación, aprobación, patrocinio ni
respaldo por parte de ninguna empresa o marca concreta.


----------------------------------------------------------------
 2. Condiciones de distribución
----------------------------------------------------------------

Freeware. Gratuito para uso personal, profesional y comercial.

Los Factory Presets están incluidos en la interfaz de Tube Simulator. Esta
versión no incluye un paquete de presets independiente. Guarde y cargue los
presets mediante las funciones proporcionadas por el complemento o el host.

Las condiciones de redistribución, modificación, ingeniería inversa y cualquier
otro uso se establecen en los EULA adjuntos, EULA_jp.txt / EULA_en.txt. Este
README es solo un resumen y no modifica el EULA.


----------------------------------------------------------------
 3. Requisitos
----------------------------------------------------------------

  Sistema operativo : Windows de 64 bits
  Host              : foobar2000 v2.x (64 bits) o un host VST3 de 64 bits
  CPU               : x86-64 (Intel / AMD)
  Salida            : Cualquier dispositivo de audio que el host pueda abrir

Software adicional: no se necesita ninguno

No se admiten foobar2000 de 32 bits ni hosts VST de 32 bits. Las frecuencias de
muestreo y los factores de Oversampling más altos aumentan la carga de CPU. Si
se cambia el perfil del Resampler, la PDC es de 302 / 263 / 218 frames para
Linear High / Standard / Light y de 28 frames para Minimum.


----------------------------------------------------------------
 4. Instalación
----------------------------------------------------------------

DSP para foobar2000:

  1. Cierre foobar2000.
  2. Haga doble clic en el archivo incluido
     foo_dsp_tube_simulator.fb2k-component.
     (También puede abrir File > Preferences > Components y elegir Install...)
  3. Seleccione Apply para completar la instalación.

La instalación no añade el complemento automáticamente a la cadena de
reproducción. Abra File > Preferences > Playback > DSP Manager, mueva
"Tube Simulator" a Active DSPs y use Configure selected para abrir la ventana
de ajustes.

VST3:

Copie la carpeta incluida VST3\\TubeSimulator.vst3 a una carpeta de complementos
VST3 que el host examine y vuelva a explorar los complementos. El archivo
contiene el binario para Windows x86_64.


----------------------------------------------------------------
 5. Primeros pasos
----------------------------------------------------------------

La ventana de ajustes incluye Input, Output, Character, Oversampling, Resampler
profile, Auto Gain, Level Match, COMPARE, Factory Preset, Diagnostics y About.

Comience con un volumen de reproducción bajo y ajuste gradualmente, empezando
por Standard o un Factory Preset. Auto Gain y Level Match ajustan el nivel; no
son limitadores de seguridad.


----------------------------------------------------------------
 6. Desinstalación
----------------------------------------------------------------

DSP para foobar2000:

  1. Abra File > Preferences > Playback > DSP Manager y quite "Tube Simulator"
     de Active DSPs.
  2. Abra File > Preferences > Components, seleccione "Tube Simulator DSP" y
     elimínelo.
  3. Seleccione Apply y reinicie foobar2000.

VST3:

Elimine la carpeta TubeSimulator.vst3 de la carpeta VST3 utilizada por el host
y vuelva a explorar los complementos.

Si quedan ajustes o cachés del host, utilice la gestión de ajustes del propio
host.


----------------------------------------------------------------
 7. Notas de uso
----------------------------------------------------------------

[Nivel de reproducción]

Input Drive, Output, Auto Gain, Level Match y COMPARE pueden cambiar el nivel
de pico o el volumen percibido. Comience con un volumen bajo y gestione usted
mismo el nivel final, la seguridad auditiva y la seguridad del equipo.

[Oversampling y perfiles del Resampler]

Los factores más altos y los perfiles de mayor calidad utilizan más CPU. En VST3,
un cambio de perfil se refleja en la PDC después del siguiente prepare o reinicio
del host. La frecuencia de procesamiento real proporcionada por el host puede
comprobarse en Diagnostics, en HOST RATE.

[Dónde se guardan los ajustes]

Los ajustes se guardan en el perfil de foobar2000 o en la gestión de proyecto /
estado del host VST3. Los ajustes del usuario no se incluyen en el archivo de
lanzamiento.

[Comportamiento en silencio]

Debido al procesamiento del modelo de válvulas y al contrato de cola del host,
el silencio digital no tiene por qué ser exactamente cero matemático.


----------------------------------------------------------------
 8. Licencia
----------------------------------------------------------------

Tube Simulator: freeware propietario

  Gratuito para uso personal, profesional y comercial. Las condiciones de
  redistribución, modificación, ingeniería inversa y cualquier otro uso se
  establecen en EULA_jp.txt / EULA_en.txt.

Software incluido:

  - JUCE 9.0.1 (licencia JUCE 9 Starter): Raw Material Software Limited
    Se utiliza para crear la interfaz, la implementación VST3 y la UI relacionada
    de Tube Simulator. Se aplica el acuerdo de licencia de usuario final de JUCE 9,
    no la licencia propia de Tube Simulator.

  - Steinberg VST 3 SDK
    El SDK incluido en el árbol de fuentes de JUCE 9.0.1 se utiliza para compilar
    VST3. Consulte third-party-notices.txt para conocer su licencia y las
    condiciones de las marcas VST.

  - foobar2000 SDK (condiciones propias del proyecto foobar2000)
    Se utiliza para crear el componente de foobar2000. foobar2000 no forma parte
    de Tube Simulator y no se distribuye con él.

  Consulte licenses/JUCE_LICENSE.md y licenses/JUCE_EMBEDDED_LICENSES.md para
  ver el resumen de la licencia JUCE y los textos completos de los componentes
  integrados. Consulte third-party-notices.txt para otros detalles.


----------------------------------------------------------------
 9. Contacto y soporte
----------------------------------------------------------------

  Autor       : moenium
  Sitio web   : https://moenium.net/
  Contacto    : contact@moenium.net

Para contactar o informar de errores, escriba a la dirección anterior.

Incluya la versión de Tube Simulator, la versión del host foobar2000 o VST3,
la frecuencia de muestreo, Character, Oversampling, Resampler profile y los
pasos para reproducir el problema. También son útiles la salida de Diagnostics
y los registros del host.


----------------------------------------------------------------
 10. Historial de cambios
----------------------------------------------------------------

Consulte changelog.md, incluido con el producto, para ver los cambios de cada
versión.


================================================================
================================================================
