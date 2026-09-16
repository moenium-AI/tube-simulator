================================================================
 Tube Simulator Versão 1.0.0
================================================================

Plugin de áudio para Windows
DSP para foobar2000 / VST3

  Copyright (C) 2026 moenium
  Data de lançamento : 2026-09-16


----------------------------------------------------------------
 1. Visão geral
----------------------------------------------------------------

Tube Simulator é um plugin de áudio para Windows que modela o comportamento
dinâmico de um amplificador valvulado. Ele oferece um componente DSP de 64 bits
para o foobar2000 v2.x e um plugin VST3 de 64 bits. Ambos usam o mesmo painel de
controle e o mesmo Realtime Core compartilhado.

Seus principais recursos são:

  - Quatro Characters: Standard, Dynamic PSU, OPT Magnetic, Full Reference
  - Input Drive, Output, Auto Gain e Level Match
  - COMPARE, independente de Level Match
  - Oversampling de fase linear Auto / 1x / 2x / 4x
  - Latência de processamento de 302 frames com o perfil padrão Linear /
    High Quality
  - PDC por perfil: 302 / 263 / 218 frames para Linear High / Standard / Light,
    e 28 frames para Minimum
  - 44,1 / 48 / 88,2 / 96 / 176,4 / 192 kHz
  - Operação mono e estéreo
  - Factory Presets, medidores de entrada/saída, Diagnostics e About

Os nomes 310A, 300B e 274B são usados exclusivamente como referências técnicas
e históricas de tipos. Seu uso não implica afiliação, aprovação, patrocínio ou
endosso por parte de qualquer empresa ou marca específica.


----------------------------------------------------------------
 2. Termos de distribuição
----------------------------------------------------------------

Freeware. Gratuito para uso pessoal, profissional e comercial.

Os Factory Presets estão incluídos na interface do Tube Simulator. Esta versão
não inclui um pacote de presets separado. Salve e carregue presets usando os
recursos fornecidos pelo plugin ou pelo host.

As condições de redistribuição, modificação, engenharia reversa e qualquer outro
uso estão definidas nos EULAs incluídos, EULA_jp.txt / EULA_en.txt. Este README é
apenas um resumo e não altera o EULA.


----------------------------------------------------------------
 3. Requisitos
----------------------------------------------------------------

  Sistema operacional : Windows de 64 bits
  Host                : foobar2000 v2.x (64 bits) ou um host VST3 de 64 bits
  CPU                 : x86-64 (Intel / AMD)
  Saída               : Qualquer dispositivo de áudio que o host possa abrir

Software adicional: nenhum

O foobar2000 de 32 bits e hosts VST de 32 bits não são compatíveis. Taxas de
amostragem e fatores de Oversampling mais altos aumentam o uso da CPU. Se o
perfil do Resampler for alterado, a PDC será de 302 / 263 / 218 frames para
Linear High / Standard / Light e de 28 frames para Minimum.


----------------------------------------------------------------
 4. Instalação
----------------------------------------------------------------

DSP para foobar2000:

  1. Feche o foobar2000.
  2. Clique duas vezes no arquivo incluído
     foo_dsp_tube_simulator.fb2k-component.
     (Ou abra File > Preferences > Components e escolha Install...)
  3. Selecione Apply para concluir a instalação.

A instalação não coloca o plugin automaticamente na cadeia de reprodução. Abra
File > Preferences > Playback > DSP Manager, mova "Tube Simulator" para Active
DSPs e use Configure selected para abrir a janela de configurações.

VST3:

Copie a pasta incluída VST3\\TubeSimulator.vst3 para uma pasta de plugins VST3
pesquisada pelo host e faça uma nova varredura. O arquivo contém o binário para
Windows x86_64.


----------------------------------------------------------------
 5. Primeiros passos
----------------------------------------------------------------

A janela de configurações inclui Input, Output, Character, Oversampling,
Resampler profile, Auto Gain, Level Match, COMPARE, Factory Preset, Diagnostics
e About.

Comece com um volume de reprodução baixo e ajuste gradualmente, começando por
Standard ou por um Factory Preset. Auto Gain e Level Match ajustam o nível; não
são limitadores de segurança.


----------------------------------------------------------------
 6. Desinstalação
----------------------------------------------------------------

DSP para foobar2000:

  1. Abra File > Preferences > Playback > DSP Manager e remova "Tube Simulator"
     de Active DSPs.
  2. Abra File > Preferences > Components, selecione "Tube Simulator DSP" e
     remova-o.
  3. Selecione Apply e reinicie o foobar2000.

VST3:

Exclua a pasta TubeSimulator.vst3 da pasta de plugins VST3 usada pelo host e
faça uma nova varredura dos plugins.

Se restarem configurações ou caches do host, use o gerenciamento de configurações
do próprio host.


----------------------------------------------------------------
 7. Observações de uso
----------------------------------------------------------------

[Nível de reprodução]

Input Drive, Output, Auto Gain, Level Match e COMPARE podem alterar o nível de
pico ou o volume percebido. Comece com um volume baixo e gerencie por conta
própria o nível final, a segurança auditiva e a proteção do equipamento.

[Oversampling e perfis do Resampler]

Fatores mais altos e perfis de maior qualidade usam mais CPU. No VST3, uma
alteração de perfil é refletida na PDC após o próximo prepare ou reinício do host.
A taxa de processamento real fornecida pelo host pode ser verificada em
Diagnostics, em HOST RATE.

[Onde as configurações são armazenadas]

As configurações são armazenadas no perfil do foobar2000 ou no gerenciamento de
projeto/estado do host VST3. As configurações do usuário não fazem parte do
arquivo de lançamento.

[Comportamento no silêncio]

Devido ao processamento do modelo de válvulas e ao contrato de cauda do host, o
silêncio digital não é necessariamente igual a zero matemático.


----------------------------------------------------------------
 8. Licença
----------------------------------------------------------------

Tube Simulator: freeware proprietário

  Gratuito para uso pessoal, profissional e comercial. As condições de
  redistribuição, modificação, engenharia reversa e qualquer outro uso estão
  definidas em EULA_jp.txt / EULA_en.txt.

Software incluído:

  - JUCE 9.0.1 (licença JUCE 9 Starter): Raw Material Software Limited
    Usado para criar a interface do Tube Simulator, a implementação VST3 e a UI
    relacionada. Aplicam-se os termos do JUCE 9 End User Licence Agreement, não
    a licença própria do Tube Simulator.

  - Steinberg VST 3 SDK
    O SDK fornecido na árvore de código-fonte do JUCE 9.0.1 é usado na compilação
    VST3. Consulte third-party-notices.txt para sua licença e os termos das
    marcas VST.

  - foobar2000 SDK (termos próprios do projeto foobar2000)
    Usado para criar o componente do foobar2000. O foobar2000 não faz parte do
    Tube Simulator e não é distribuído com ele.

  Consulte licenses/JUCE_LICENSE.md e licenses/JUCE_EMBEDDED_LICENSES.md para o
  resumo da licença do JUCE e os textos completos dos componentes incorporados.
  Consulte third-party-notices.txt para outros detalhes de licença.


----------------------------------------------------------------
 9. Contato e suporte
----------------------------------------------------------------

  Autor       : moenium
  Site        : https://moenium.net/
  Contato     : contact@moenium.net

Para entrar em contato ou relatar problemas, envie um e-mail para o endereço
acima.

Inclua a versão do Tube Simulator, a versão do host foobar2000 ou VST3, a taxa
de amostragem, Character, Oversampling, Resampler profile e as etapas para
reproduzir o problema. A saída do Diagnostics e os logs do host também são úteis.


----------------------------------------------------------------
 10. Registro de alterações
----------------------------------------------------------------

Consulte o changelog.md incluído para ver as alterações de cada versão.


================================================================
================================================================
