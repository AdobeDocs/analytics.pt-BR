---
title: Dimensões de pesquisa móvel
description: Dimensões baseadas no endereço IP e agente de usuário do dispositivo.
feature: Dimensions
exl-id: fa460888-513d-4d14-93b1-33d308e0758a
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 100%

---

# Dimensões de pesquisa móvel

*Esta página faz referência às propriedades dos dispositivos móveis que acessam o site. Consulte [Dimensões do ciclo de vida móvel](lifecycle-dimensions.md) ou [Métricas do ciclo de vida móvel](../metrics/lifecycle-metrics.md) para rastrear em um aplicativo móvel.*

As [dimensões](overview.md) de pesquisa móvel fornecem insights sobre as propriedades dos dispositivos móveis que visitam o site. Essas propriedades se baseiam no agente de usuário e no endereço IP da ocorrência. Utilize essas dimensões para entender melhor quais recursos são compatíveis com um dispositivo móvel.

## Preencher essas dimensões com dados

Essas dimensões se referem às regras de pesquisa internas da Adobe. 

* Para a dimensão [!UICONTROL Operadora de celular], a Adobe faz parceria com a [Digital Element](https://www.digitalelement.com/pt-pt/) usando o NetAcuity para manter pesquisas entre o endereço IP e a operadora de celular.
* Para todas as outras dimensões móveis, a Adobe tem parcerias com o [DeviceAtlas](https://deviceatlas.com/) para manter pesquisas entre o agente de usuário e cada respectiva dimensão móvel.

A disponibilidade dessas dimensões depende do tipo de implementação:

* Essas dimensões estão prontas para uso em implementações do AppMeasurement.
* Para implementações do SDK da Web, habilite a [!UICONTROL Pesquisa geográfica] (para a operadora de celular) ou [!UICONTROL Pesquisa de dispositivo] (para todas as outras dimensões) ao [configurar um fluxo de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-BR).

## Descrições de dimensões móveis

>[!NOTE]
>
>Os itens de dimensão rotulados `"None"` são dispositivos não móveis. Se desejar um relatório que inclua apenas dispositivos móveis, arraste a dimensão “Dispositivo móvel” para a área de segmento da tela do Workspace.

* **[!UICONTROL Suporte de áudio para dispositivo móvel]**: determina os formatos de arquivo que o dispositivo pode reproduzir. Os valores de exemplo incluem `"MP3"`, `"AAC"` e `"MIDI Monophonic"`. Os valores nessa dimensão não são mutuamente exclusivos; uma única ocorrência pode atribuir a vários itens de dimensão.
* **[!UICONTROL Operadora de celular]**: o telefone ou o provedor de dados do dispositivo. Os valores de exemplo incluem `"Reliance Jio"`, `"Airtel"`, `"Vodafone"` e `"Verizon"`.
* **[!UICONTROL Intensidade de cor do dispositivo móvel]**: a profundidade de cor do dispositivo móvel, em bits.
* **[!UICONTROL Suporte a cookies para dispositivo móvel]**: determina se o dispositivo móvel aceita cookies. Esta dimensão não indica se o navegador aceita cookies. Os itens de dimensão incluem `"Supported"`, `"Not supported"` e `"Unknown"`.
* **[!UICONTROL Dispositivo móvel]**: o dispositivo móvel que o visitante usa.
* **[!UICONTROL Número do dispositivo móvel]**: determina se o dispositivo móvel transmite seu número. Essa dimensão não fornece o número do dispositivo móvel. Os itens de dimensão incluem `"Supported"`, `"Not supported"` e `"Unknown"`.
* **[!UICONTROL Tipo de dispositivo móvel]**: o tipo do dispositivo móvel. Os valores de exemplo incluem `"Mobile phone"`, `"Tablet"`, `"Media player"` e `"Gaming console"`.
* **[!UICONTROL DRM móvel]**: o tipo de DRM que o dispositivo móvel aceita. Os valores de exemplo incluem `"DRM OMA forward"`, `"DRM OMA combined delivery"` e `"DRM OMA separate delivery"`.
* **[!UICONTROL Suporte a imagens móveis]**: os tipos de imagens compatíveis com o dispositivo móvel. Os valores de exemplo incluem `"PNG"`, `"JPEG"` e `"GIF 87"`. Os valores nessa dimensão não são mutuamente exclusivos; uma única ocorrência pode atribuir a vários itens de dimensão.
* **[!UICONTROL Serviços de informações para dispositivo móvel]**: os tipos de serviços de notícias aceitos pelo dispositivo. Dispositivos mais novos normalmente não relatam essas informações.
* **[!UICONTROL VM Java para dispositivo móvel]**: as versões do Java compatíveis com o dispositivo.
* **[!UICONTROL Decoração de correspondência para dispositivo móvel]**: determina se o dispositivo é compatível com o [Decome](https://en.wikipedia.org/wiki/Decome), um recurso popularizado em dispositivos japoneses.
* **[!UICONTROL Fabricante do dispositivo móvel]**: classifica dispositivos móveis por fabricante. Os valores de exemplo incluem `"Apple"`, `"Samsung"`, `"Huawei"` e `"Motorola"`.
* **[!UICONTROL Comprimento máximo do marcador de página para dispositivo móvel]**: o número máximo de bytes que o dispositivo móvel aceita em URLs marcados. Dispositivos mais novos normalmente não possuem um limite.
* **[!UICONTROL Comprimento máximo do URL do navegador para dispositivo móvel]**: o número máximo de bytes que o dispositivo móvel aceita em URLs. Dispositivos mais novos normalmente não possuem um limite.
* **[!UICONTROL Comprimento máximo do email para dispositivo móvel]**: o número máximo de bytes aceitos pelo dispositivo móvel em um email. Dispositivos mais novos normalmente não possuem um limite.
* **[!UICONTROL Protocolos de rede para dispositivo móvel]**: os tipos de protocolo que o dispositivo aceita ao acessar a Internet. Os valores de exemplo incluem `"EDGE"`, `"GPRS"`, `"UMTS"` e `"LTE"`.
* **[!UICONTROL Sistema operacional para dispositivo móvel (obsoleto)]**: em vez disso, use a dimensão [Sistema operacional](operating-systems.md).
* **[!UICONTROL “Push-to-talk” para dispositivo móvel]**: determina se o dispositivo aceita a função PTT (push-to-talk), o que permite que o dispositivo móvel se comporte de forma semelhante a um rádio bidirecional. Dispositivos mais novos normalmente não relatam esse recurso.
* **[!UICONTROL Altura da tela do dispositivo móvel]**: a altura da tela, em pixels. iPhones sempre relatam `"480"` devido à incapacidade de determinar a versão do dispositivo iPhone. Consulte a seção abaixo sobre como determinar a versão do iPhone.
* **[!UICONTROL Tamanho da tela do dispositivo móvel]**: as dimensões completas do dispositivo móvel em pixels. O tamanho de tela relatado não indica a orientação do dispositivo. Independentemente da orientação da tela, cada dispositivo possui uma resolução de tela fixa no relatório. O tamanho baseia-se na pesquisa que determina qual orientação é mais provável. É possível ver tamanhos como `"768x1024"` e `"1024x768"` no mesmo relatório, onde cada tamanho representa um ou mais dispositivos diferentes.
* **[!UICONTROL Largura da tela do dispositivo móvel]**: a largura da tela, em pixels.
* **[!UICONTROL Suporte de vídeo para dispositivo móvel]**: os formatos de arquivo de vídeo e os codecs aceitos pelo dispositivo móvel. Existem vários itens de dimensão para diferentes codecs de arquivos MP4 e 3GPP. Os valores nessa dimensão não são mutuamente exclusivos; uma única ocorrência pode atribuir a vários itens de dimensão.

## Separação do iPhone por modelo ou versão

Os dispositivos móveis informam a versão do firmware na sequência de agente do usuário, e não a versão do dispositivo. Por exemplo, um iPhone da geração atual contém um agente de usuário idêntico à última geração do iPhone se ele estiver na mesma versão de firmware. Como não há como determinar a versão do dispositivo do iPhone usando o JavaScript, todos os iPhones pertencem à mesma classificação. As dimensões móveis são estritamente baseadas em pesquisas que fazem referência ao agente de usuário e, como resultado, todos os iPhones exibem um tamanho de tela de `320 x 480`.

Se quiser coletar a versão do iPhone, há duas maneiras de contornar essa limitação.

* **Use o SDK móvel**: o SDK móvel contém dimensões que expõem a versão do dispositivo para uso em relatórios. Esse método é mais adequado para aplicativos móveis do que para sites.
* **Use outras variáveis disponíveis por meio do JavaScript**: algumas variáveis, como `screen.height` e `screen.width`, podem ser usadas para descobrir a versão do dispositivo. Por exemplo, você pode usar o seguinte fragmento de código no site:

  ```js
  if (navigator.userAgent.indexOf('iPhone') > -1) {
    s.eVarXX = screen.width + "x" + screen.height;
    }
  ```

  Esse bloco de código detecta primeiro se o dispositivo é um iPhone. Se for um Iphone, o código usará o JavaScript para inserir a resolução da tela em uma eVar. Esse método permite detectar a versão aproximada do dispositivo se as resoluções de tela forem exclusivas.
