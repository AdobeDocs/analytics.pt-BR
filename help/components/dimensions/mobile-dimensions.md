---
title: Dimensões de pesquisa móvel
description: Dimension com base no endereço IP e no agente de usuário do dispositivo.
feature: Dimensions
exl-id: fa460888-513d-4d14-93b1-33d308e0758a
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 60%

---

# Dimensões de pesquisa móvel

*Esta página faz referência às propriedades dos dispositivos móveis que acessam seu site. Consulte [Dimensões do ciclo de vida móvel](lifecycle-dimensions.md) ou [Métricas de ciclo de vida móvel](../metrics/lifecycle-metrics.md) para rastrear em um aplicativo móvel.*

Pesquisa em dispositivo móvel [dimensões](overview.md) forneça insights sobre as propriedades dos dispositivos móveis que visitam seu site. Essas propriedades se baseiam no agente do usuário e no endereço IP da ocorrência. Você pode usar essas dimensões para ajudar a entender quais recursos um dispositivo móvel aceita.

## Preencher essas dimensões com dados

Essas dimensões se referem às regras de pesquisa internas da Adobe.

* Para o [!UICONTROL Operadora de celular] dimension, parceiros de Adobe com [Elemento digital](https://www.digitalelement.com/pt-pt/) usar NetAcuity para manter pesquisas entre o endereço IP e a operadora de celular.
* Para todas as outras dimensões móveis, a Adobe tem parcerias com [DeviceAtlas](https://deviceatlas.com/) para manter pesquisas entre o agente do usuário e cada respectiva dimensão móvel.

A disponibilidade dessas dimensões depende do tipo de implementação:

* Para implementações do AppMeasurement, essas dimensões funcionam imediatamente.
* Para implementações do SDK da Web, habilite [!UICONTROL Pesquisa geográfica] (para operadora de celular) ou [!UICONTROL Pesquisa de dispositivo] (para todas as outras dimensões) quando [configurar um fluxo de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-BR).

## Descrições de dimensões móveis

>[!NOTE]
>
>Os itens de dimensão rotulados `"None"` são dispositivos não móveis. Se desejar um relatório que inclua apenas dispositivos móveis, arraste a dimensão “Dispositivo móvel” para a área de segmento da tela do Workspace.

* **[!UICONTROL Suporte de áudio para dispositivo móvel]**: determina os formatos de arquivo que o dispositivo pode reproduzir. Os valores de exemplo incluem `"MP3"`, `"AAC"` e `"MIDI Monophonic"`. Os valores nessa dimensão não são mutuamente exclusivos; uma única ocorrência pode atribuir a vários itens de dimensão.
* **[!UICONTROL Operadora de celular]**: O telefone ou o provedor de dados do dispositivo. Os valores de exemplo incluem `"Reliance Jio"`, `"Airtel"`, `"Vodafone"` e `"Verizon"`.
* **[!UICONTROL Intensidade de cor do dispositivo móvel]**: a profundidade de cor do dispositivo móvel, em bits.
* **[!UICONTROL Suporte a cookies para dispositivo móvel]**: determina se o dispositivo móvel aceita cookies. Essa dimensão não indica se o navegador aceita cookies. Os itens de dimensão incluem `"Supported"`, `"Not supported"` e `"Unknown"`.
* **[!UICONTROL Dispositivo móvel]**: o dispositivo móvel que o visitante usa.
* **[!UICONTROL Número do dispositivo móvel]**: determina se o dispositivo móvel transmite seu número. Essa dimensão não fornece o próprio número de celular. Os itens de dimensão incluem `"Supported"`, `"Not supported"` e `"Unknown"`.
* **[!UICONTROL Tipo de dispositivo móvel]**: o tipo do dispositivo móvel. Os valores de exemplo incluem `"Mobile phone"`, `"Tablet"`, `"Media player"` e `"Gaming console"`.
* **[!UICONTROL DRM móvel]**: o tipo de DRM que o dispositivo móvel aceita. Os valores de exemplo incluem `"DRM OMA forward"`, `"DRM OMA combined delivery"` e `"DRM OMA separate delivery"`.
* **[!UICONTROL Suporte a imagem em dispositivo móvel]**: os tipos de imagens que o dispositivo móvel aceita. Os valores de exemplo incluem `"PNG"`, `"JPEG"` e `"GIF 87"`. Os valores nessa dimensão não são mutuamente exclusivos; uma única ocorrência pode atribuir a vários itens de dimensão.
* **[!UICONTROL Serviços de informações para dispositivo móvel]**: os tipos de serviços de notícias aceitos pelo dispositivo. Dispositivos modernos normalmente não relatam essas informações.
* **[!UICONTROL VM Java para dispositivo móvel]**: as versões do Java compatíveis com o dispositivo.
* **[!UICONTROL Decoração de correio para dispositivo móvel]**: determina se o dispositivo aceita [Decome](https://en.wikipedia.org/wiki/Decome), um recurso conhecido em dispositivos japoneses.
* **[!UICONTROL Fabricante remoto]**: classifica os dispositivos móveis por fabricante. Os valores de exemplo incluem `"Apple"`, `"Samsung"`, `"Huawei"` e `"Motorola"`.
* **[!UICONTROL Comprimento máximo do marcador de página para dispositivo móvel]**: o número máximo de bytes que o dispositivo móvel aceita em URLs marcados. Dispositivos modernos normalmente não têm limite.
* **[!UICONTROL Comprimento máximo do URL do navegador para dispositivo móvel]**: o número máximo de bytes que o dispositivo móvel aceita em URLs. Dispositivos modernos normalmente não têm limite.
* **[!UICONTROL Comprimento máximo do e-mail para dispositivo móvel]**: o número máximo de bytes aceitos pelo dispositivo móvel em um e-mail. Dispositivos modernos normalmente não têm limite.
* **[!UICONTROL Protocolos de rede para dispositivo móvel]**: os tipos de protocolo que o dispositivo aceita ao acessar a Internet. Os valores de exemplo incluem `"EDGE"`, `"GPRS"`, `"UMTS"` e `"LTE"`.
* **[!UICONTROL Sistema operacional para dispositivo móvel (obsoleto)]**: em vez disso, use a dimensão [Sistema operacional](operating-systems.md).
* **[!UICONTROL “Push-to-talk” para dispositivo móvel]**: determina se o dispositivo aceita a função PTT (push-to-talk), o que permite que o dispositivo móvel se comporte de forma semelhante a um rádio bidirecional. Dispositivos modernos normalmente não apresentam esse recurso.
* **[!UICONTROL Altura da tela do dispositivo móvel]**: a altura da tela, em pixels. iPhones sempre reportam `"480"` devido à incapacidade de determinar a versão do dispositivo iPhone. Consulte a seção abaixo sobre como determinar a versão do dispositivo iPhone.
* **[!UICONTROL Tamanho da tela do dispositivo móvel]**: as dimensões completas do dispositivo móvel em pixels. O tamanho de tela relatado não indica a orientação do dispositivo. Independentemente da orientação da tela, cada dispositivo possui uma resolução de tela fixa no relatório. O tamanho baseia-se na pesquisa que determina qual orientação é mais provável. É possível ver tamanhos como `"768x1024"` e `"1024x768"` no mesmo relatório, onde cada tamanho representa um ou mais dispositivos diferentes.
* **[!UICONTROL Largura da tela do dispositivo móvel]**: a largura da tela, em pixels.
* **[!UICONTROL Suporte de vídeo para dispositivo móvel]**: os formatos de arquivo de vídeo e os codecs aceitos pelo dispositivo móvel. Existem vários itens de dimensão para diferentes codecs de arquivos MP4 e 3GPP. Os valores nessa dimensão não são mutuamente exclusivos; uma única ocorrência pode atribuir a vários itens de dimensão.

## Separação do iPhone por modelo ou versão

Os dispositivos móveis informam a versão do firmware na sequência de agente do usuário, e não a versão do dispositivo. Por exemplo, um iPhone da geração atual contém um agente de usuário idêntico à última geração do iPhone se ele estiver na mesma versão de firmware. Como não há como determinar a versão do dispositivo do iPhone usando o JavaScript, todos os iPhones pertencem à mesma classificação. As dimensões móveis são estritamente baseadas em pesquisas que fazem referência ao agente de usuário, resultando na exibição de um tamanho de tela de `320 x 480`.

Se você quiser coletar a versão do dispositivo iPhone, há duas maneiras de contornar essa limitação.

* **Usar o SDK móvel**: o SDK móvel contém dimensões que expõem a versão do dispositivo para usar no relatórios. Esse método é mais adequado para aplicativos móveis do que para sites.
* **Use outras variáveis disponíveis por meio do JavaScript**: algumas variáveis, como `screen.height` e `screen.width`, podem ser usadas para descobrir a versão do dispositivo. Por exemplo, você pode usar o seguinte fragmento de código no site:

  ```js
  if (navigator.userAgent.indexOf('iPhone') > -1) {
    s.eVarXX = screen.width + "x" + screen.height;
    }
  ```

  Esse bloco de código detecta primeiro se o dispositivo é um iPhone. Se for um Iphone, o código usará o JavaScript para inserir a resolução da tela em uma eVar. Esse método permite detectar a versão aproximada do dispositivo se as resoluções de tela forem exclusivas.
