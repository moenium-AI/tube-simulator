<div align="center">

# Tube Simulator

**Plugin de modelagem de amplificador valvulado para Windows**

[![Plataforma](https://img.shields.io/badge/platform-Windows%20x64-lightgrey)](#requisitos)
[![Host](https://img.shields.io/badge/host-foobar2000%20v2.x%2064--bit-orange)](https://www.foobar2000.org/)
[![Licença](https://img.shields.io/badge/license-proprietary%20freeware-green)](#licença)

[Product site](https://moenium.net/tube-simulator/) · [Manual](https://moenium.net/tube-simulator/manual/1.0/pt-BR/introduction.html) ·
[GitHub Releases](../../releases/latest) · [Changelog](distribution/changelog.md)

[English](README.md) · [日本語](README.ja.md) · [Deutsch](README.de-DE.md) ·
[Español](README.es-ES.md) · [Français](README.fr-FR.md) ·
[Italiano](README.it-IT.md) · [한국어](README.ko-KR.md) · Português ·
[Русский](README.ru-RU.md) · [简体中文](README.zh-CN.md) ·
[繁體中文](README.zh-TW.md)

</div>

---

Tube Simulator é um plugin de áudio para Windows que modela o comportamento
dinâmico de um amplificador valvulado. Ele está disponível como componente DSP
para foobar2000 v2.x de 64 bits e como plugin VST3 para hosts de 64 bits. As duas
versões usam o mesmo mecanismo de processamento em tempo real e a mesma
interface de configuração.

<div align="center">
<img src="screenshots/tubesimulator_screenshot/tubesimulator.png" alt="Janela de configuração do Tube Simulator" width="720">
</div>

## Recursos

- **Quatro Characters:** Standard, Dynamic PSU, OPT Magnetic e Full Reference.
- **Drive e saída:** Input Drive e Output são ajustados separadamente.
- **Ferramentas de nível:** Auto Gain, Level Match e um caminho de audição COMPARE independente.
- **Oversampling:** processamento de fase linear em Auto, 1x, 2x e 4x.
- **Perfis de Resampler:** fase Linear / Minimum com qualidades High, Standard e Light.
- **Latência integrada ao host:** PDC de 302, 263, 218 ou 28 samples conforme o perfil.
- **Diagnóstico:** medidores de entrada/saída, hold, Diagnostics, About e Factory Preset.
- **Dois formatos:** componente DSP para foobar2000 e plugin VST3 de 64 bits.

## Caminho do sinal

A visualização **Signal Path** representa os estágios modelados do amplificador. Os
dois controles de Character selecionam os ramos Dynamic PSU e OPT Magnetic.

| Dynamic PSU | OPT Magnetic | Character |
| --- | --- | --- |
| Desativado | Desativado | Standard |
| Ativado | Desativado | Dynamic PSU |
| Desativado | Ativado | OPT Magnetic |
| Ativado | Ativado | Full Reference |

Input Drive e Character definem o voicing. Output, Auto Gain, Level Match,
COMPARE, Oversampling e Resampler são controles independentes.

## Requisitos

| | |
| --- | --- |
| Sistema operacional | Windows |
| Host | foobar2000 v2.x, **somente 64 bits**, ou um host VST3 de 64 bits |
| CPU | x86-64 (Intel / AMD) |
| Saída | Qualquer dispositivo de áudio que o host consiga abrir |
| Runtime adicional | Nenhum |

foobar2000 de 32 bits e hosts VST de 32 bits não são compatíveis. Taxas de
amostragem, fatores de Oversampling e perfis de Resampler de maior qualidade
usam mais CPU.

## Instalação

### Componente DSP do foobar2000

1. Feche o foobar2000.
2. Clique duas vezes em `foo_dsp_tube_simulator.fb2k-component` ou abra
   **File → Preferences → Components** e escolha **Install…**.
3. Selecione **Apply**.
4. Abra **File → Preferences → Playback → DSP Manager**.
5. Mova **Tube Simulator** para **Active DSPs**.
6. Selecione **Configure selected**.

A instalação do componente, por si só, não o adiciona à cadeia de reprodução.

### Plugin VST3

Copie `VST3/TubeSimulator.vst3` para uma pasta VST3 verificada pelo host e faça uma
nova varredura dos plugins.

### Desinstalação

No foobar2000, remova o Tube Simulator de **Active DSPs** e exclua
**Tube Simulator DSP** em **Preferences → Components**. Para VST3, remova
`TubeSimulator.vst3` da pasta VST3 do host e faça uma nova varredura.

## Primeiros passos

Comece com **Standard** ou um Factory Preset e ajuste Input Drive e Output aos
poucos. Baixe o volume de monitoração antes de alterar Drive, Output, Character ou
Oversampling, pois eles podem mudar os picos e o volume percebido.

Comece com **Standard** ou um Factory Preset e ajuste Input Drive e Output aos
poucos. Use **Level Match** para comparar em um nível mais próximo e **COMPARE**
para ouvir o caminho de referência. Auto Gain e Level Match são ferramentas diferentes.

## Download e verificação

A versão mais recente está disponível em [GitHub Releases](../../releases/latest).
Cada página de versão deve informar o nome do arquivo, os checksums SHA-256/SHA-512
e as observações correspondentes.

No Windows PowerShell, calcule SHA-256 com:

```powershell
Get-FileHash .\TubeSimulator_*.zip -Algorithm SHA256
```

## Documentação

- [Manual online e seletor de idioma](https://moenium.net/tube-simulator/manual/1.0/)
- [Manual em português](https://moenium.net/tube-simulator/manual/1.0/pt-BR/introduction.html)
- [Changelog](distribution/changelog.md)
- [README, EULA e avisos de terceiros](distribution/)
- [Documentos de licença do JUCE](licenses/)

## Feedback e suporte

Relatos de bugs, compatibilidade com hosts e sugestões de tradução são bem-vindos.

**contact@moenium.net**

Inclua a versão do Tube Simulator, o host e sua versão, a taxa de amostragem,
Character, Oversampling, o perfil de Resampler e os passos para reproduzir o
problema. As informações de Diagnostics também são úteis.

## Outros softwares da moenium

Se você procura um DSP multiestágio mais amplo para foobar2000, consulte o
[Alauda](https://github.com/moenium-AI/Alauda).

Alauda e Tube Simulator são produtos separados.

## Apoie o Tube Simulator

O Tube Simulator é gratuito e continuará sendo gratuito. Se ele conquistou um
lugar na sua cadeia de escuta, você pode apoiar seu desenvolvimento pelo Ko-fi.

<p align="center">
  <a href="https://ko-fi.com/moenium">
    <img src="images/kofi_banner.jpg" alt="Apoie o Tube Simulator no Ko-fi" width="600">
  </a>
</p>

## Licença

O Tube Simulator é **freeware proprietário** e pode ser usado gratuitamente para
fins pessoais, profissionais e comerciais.

Redistribuição, modificação, engenharia reversa e outras condições são regidas
pela [EULA_en.txt](distribution/EULA_en.txt) /
[EULA_jp.txt](distribution/EULA_jp.txt) incluída. A EULA japonesa é a versão
autoritativa. Este README é apenas um resumo.

Consulte os [avisos de terceiros](distribution/third-party-notices.txt) para
obter detalhes sobre JUCE, o SDK VST3 e o SDK do foobar2000.

---

Copyright © 2026 moenium · [moenium.net](https://moenium.net/)
