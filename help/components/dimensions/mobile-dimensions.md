---
title: Dimensões móveis
description: Dimensões com base na sequência agente-usuário do dispositivo.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 89%

---


# Dimensões móveis

*Esta página faz referência às propriedades dos dispositivos móveis que acessam seu site. Se você deseja rastrear dispositivos em um aplicativo móvel, consulte [Implementar o Analytics para dispositivos móveis](/help/implement/mobile-device-sdk.md) no guia de usuário Implementar.*

As dimensões móveis fornecem insight sobre as propriedades dos dispositivos móveis que visitam o site. Você pode utilizar essas dimensões para entender melhor os recursos compatíveis com um dispositivo móvel.

## Preencher essas dimensões com dados

Essas dimensões se referem às regras de pesquisa internas da Adobe. O valor da pesquisa se baseia no cabeçalho HTTP `User-Agent` enviado com a ocorrência. A Adobe faz parceria com o [DeviceAtlas](https://deviceatlas.com/) para manter pesquisas entre o agente de usuário e as dimensões móveis. Se você utilizar uma biblioteca do AppMeasurement (como por meio do Adobe Experience Platform Launch), todas as dimensões móveis funcionarão imediatamente.

## Descrições de dimensões móveis

>[!NOTE]
>
>Dimension items labeled `"None"` are non-mobile devices. Se desejar um relatório que inclua apenas dispositivos móveis, arraste a dimensão “Dispositivo móvel” para a área de segmento da tela do Workspace.

* **Suporte de áudio para dispositivo móvel**: determina os formatos de arquivo que o dispositivo pode reproduzir. Os valores de exemplo incluem `"MP3"`, `"AAC"` e `"MIDI Monophonic"`. Os valores nesta dimensão não são mutuamente exclusivos; uma única ocorrência pode atribuir a vários itens de dimensão.
* **Operadora** móvel: Se o agente do usuário contiver um dispositivo específico para a operadora, a operadora será um item de dimensão. Os valores de exemplo incluem `"Reliance Jio"`, `"Airtel"`, `"Vodafone"` e `"Verizon"`.
* **Intensidade de cor do dispositivo móvel**: a profundidade de cor do dispositivo móvel, em bits.
* **Suporte a cookies para dispositivo móvel**: determina se o dispositivo móvel aceita cookies. Este relatório não indica se o navegador aceita cookies. Dimension items include `"Supported"`, `"Not supported"`, and `"Unknown"`.
* **Dispositivo móvel**: o dispositivo móvel que o visitante usa.
* **Número do dispositivo móvel**: determina se o dispositivo móvel transmite seu número. Dimension items include `"Supported"`, `"Not supported"`, and `"Unknown"`.
* **Tipo de dispositivo móvel**: o tipo do dispositivo móvel. Os valores de exemplo incluem `"Mobile phone"`, `"Tablet"`, `"Media player"` e `"Gaming console"`.
* **DRM móvel**: o tipo de DRM que o dispositivo móvel aceita. Os valores de exemplo incluem `"DRM OMA forward"`, `"DRM OMA combined delivery"` e `"DRM OMA separate delivery"`.
* **Suporte a imagens para dispositivo móvel**: os tipos de imagens que um dispositivo móvel aceita. Os valores de exemplo incluem `"PNG"`, `"JPEG"` e `"GIF 87"`. Os valores nesta dimensão não são mutuamente exclusivos; uma única ocorrência pode atribuir a vários itens de dimensão.
* **Serviços de informações para dispositivo móvel**: os tipos de serviços de notícias aceitos pelo dispositivo. Dispositivos recentes normalmente não reportam essas informações.
* **VM Java para dispositivo móvel**: as versões do Java compatíveis com o dispositivo.
* **Decoração de correio para dispositivo móvel**: determina se o dispositivo aceita o “Decomail”, um recurso conhecido em dispositivos japoneses.
* **Fabricante do dispositivo móvel**: agrupa dispositivos móveis por fabricante. Os valores de exemplo incluem `"Apple"`, `"Samsung"`, `"Huawei"` e `"Motorola"`.
* **Comprimento máximo do marcador de página para dispositivo móvel**: o número máximo de bytes que o dispositivo móvel aceita em URLs marcados. Dispositivos recentes normalmente não têm limite.
* **Comprimento máximo do URL do navegador para dispositivo móvel**: o número máximo de bytes que o dispositivo móvel aceita em URLs. Dispositivos recentes normalmente não têm limite.
* **Comprimento máximo do e-mail para dispositivo móvel**: o número máximo de bytes aceitos pelo dispositivo móvel em um e-mail. Dispositivos recentes normalmente não têm limite.
* **Protocolos de rede para dispositivo móvel**: os tipos de protocolo que o dispositivo aceita ao acessar a Internet. Os valores de exemplo incluem `"EDGE"`, `"GPRS"`, `"UMTS"` e `"LTE"`.
* **Sistema operacional para dispositivo móvel (obsoleto)**: em vez disso, use a dimensão [Sistema operacional](operating-systems.md).
* **“Push-to-talk” para dispositivo móvel**: determina se o dispositivo aceita a função PTT (push-to-talk), o que permite que o dispositivo móvel se comporte de forma semelhante a um rádio bidirecional. Dispositivos recentes normalmente não apresentam esse recurso.
* **Altura da tela do dispositivo móvel**: a altura da tela, em pixels. Observe que os iPhones sempre reportam `"480"` devido à incapacidade de determinar a versão do iPhone. Consulte a seção abaixo sobre como determinar a versão do iPhone.
* **Tamanho da tela do dispositivo móvel**: as dimensões completas do dispositivo móvel em pixels. O tamanho de tela relatado não indica a orientação do dispositivo. Independentemente da orientação da tela, cada dispositivo possui uma resolução de tela fixa no relatório. O tamanho baseia-se na pesquisa que determina qual orientação é mais provável. É possível ver tamanhos como `"768x1024"` e `"1024x768"` no mesmo relatório, onde cada tamanho representa um ou mais dispositivos diferentes.
* **Largura da tela do dispositivo móvel**: a largura da tela, em pixels.
* **Suporte de vídeo para dispositivo móvel**: os formatos de arquivo de vídeo e os codecs aceitos pelo dispositivo móvel. Existem vários itens de dimensão para diferentes codecs de arquivos MP4 e 3GPP. Os valores nesta dimensão não são mutuamente exclusivos; uma única ocorrência pode atribuir a vários itens de dimensão.

## Separação do iPhone por modelo ou versão

Os dispositivos móveis informam a versão do firmware na sequência de agente do usuário, e não a versão do dispositivo. Por exemplo, um iPhone da geração atual contém um agente de usuário idêntico à última geração do iPhone se ele estiver na mesma versão de firmware. Como não há como determinar a versão do dispositivo do iPhone usando o JavaScript, todos os iPhones pertencem à mesma classificação. As dimensões móveis são estritamente baseadas em pesquisas que fazem referência ao agente de usuário, portanto, você descobrirá que todos os iPhones informam um tamanho de tela de `320 x 480`.

Se você quiser coletar a versão do iPhone, há duas maneiras de contornar essa limitação.

* **Use o iOS SDK**: o SDK móvel contém dimensões que expõem a versão do dispositivo para usar no relatórios. Esse método é mais adequado para aplicativos móveis do que para sites.
* **Use outras variáveis disponíveis por meio do JavaScript**: algumas variáveis, como `screen.height` e `screen.width`, podem ser usadas para descobrir a versão do dispositivo. Por exemplo, você pode usar o seguinte fragmento de código no site:

   ```js
   if (navigator.userAgent.indexOf('iPhone') > -1) {
     s.eVarXX = screen.width + "x" + screen.height;
     }
   ```

   Esse bloco de código detecta primeiro se o dispositivo é um iPhone. Se for um Iphone, o código usará o JavaScript para inserir a resolução da tela em uma eVar. Esse método permite detectar a versão aproximada do dispositivo se as resoluções de tela forem exclusivas.
