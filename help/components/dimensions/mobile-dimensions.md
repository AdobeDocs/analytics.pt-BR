---
title: Dimensões móveis
description: Dimensões com base na sequência agente-usuário do dispositivo.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 4%

---


# Dimensões móveis

*Esta página faz referência às propriedades de dispositivos móveis que acessam seu site. Se desejar rastrear dispositivos em um aplicativo móvel, consulte[Implementar o Analytics para dispositivos](/help/implement/mobile-device-sdk.md)móveis no guia Implementar usuário.*

As dimensões móveis fornecem informações sobre as propriedades de dispositivos móveis que visitam site. Você pode usar essas dimensões para ajudar a entender os recursos suportados por um dispositivo móvel.

## Preencher essas dimensões com dados

Essas dimensões fazem referência às regras de pesquisa internas da Adobe. O valor de pesquisa se baseia no cabeçalho `User-Agent` HTTP enviado com a ocorrência. A Adobe faz parceria com o [DeviceAtlas](https://deviceatlas.com/) para manter pesquisas entre o agente do usuário e as dimensões móveis. Se você usar uma biblioteca do AppMeasurement (por exemplo, por meio do Adobe Experience Platform Launch), todas as dimensões móveis funcionarão imediatamente.

## Descrições de dimensões móveis

>[!NOTE]
>
>Os valores de dimensão rotulados `"None"` são dispositivos não móveis. Se desejar um relatório que inclua apenas dispositivos móveis, arraste a dimensão &#39;Dispositivo móvel&#39; para a área de segmento da tela do Workspace.

* **Suporte** para áudio móvel: Determina os formatos de arquivo que o dispositivo pode reproduzir. Os valores de exemplo incluem `"MP3"`, `"AAC"`e `"MIDI Monophonic"`. Os valores nesta dimensão não são mutuamente exclusivos; uma única ocorrência pode atribuir a vários valores de dimensão.
* **Operadora** móvel: Se o agente do usuário contiver um dispositivo específico para a operadora, a operadora será um valor de dimensão. Os valores de exemplo incluem `"Reliance Jio"`, `"Airtel"`, `"Vodafone"`e `"Verizon"`.
* **Intensidade** de cor móvel: A intensidade de cor do dispositivo móvel, em bits.
* **Suporte** a cookies móveis: Determina se o dispositivo móvel suporta cookies. Este relatório não indica se o navegador aceita cookies. Os valores de dimensão incluem `"Supported"`, `"Not supported"`e `"Unknown"`.
* **Dispositivo** móvel: O dispositivo móvel que o visitante usa.
* **Número** do dispositivo móvel: Determina se o dispositivo móvel transmite seu número. Os valores de dimensão incluem `"Supported"`, `"Not supported"`e `"Unknown"`.
* **Tipo** de dispositivo móvel: O tipo de dispositivo móvel. Os valores de exemplo incluem `"Mobile phone"`, `"Tablet"`, `"Media player"`e `"Gaming console"`.
* **DRM** móvel: O tipo de DRM que o dispositivo móvel suporta. Os valores de exemplo incluem `"DRM OMA forward"`, `"DRM OMA combined delivery"`e `"DRM OMA separate delivery"`.
* **Suporte** a imagens móveis: Os tipos de imagens que um dispositivo móvel suporta. Os valores de exemplo incluem `"PNG"`, `"JPEG"`e `"GIF 87"`. Os valores nesta dimensão não são mutuamente exclusivos; uma única ocorrência pode atribuir a vários valores de dimensão.
* **serviços de informação** para portáteis: Os tipos de serviços de notícias suportados pelo dispositivo. Dispositivos recentes normalmente não reportam essas informações.
* **VM** Java móvel: As versões do Java suportadas pelo dispositivo.
* **decoração** de correio móvel: Determina se o dispositivo suporta Decomail (Decomail), um recurso conhecido em dispositivos japoneses.
* **Fabricante** móvel: Agrupa dispositivos móveis por fabricante. Os valores de exemplo incluem `"Apple"`, `"Samsung"`, `"Huawei"`e `"Motorola"`.
* **Comprimento** máximo do marcador móvel: O número máximo de bytes que o dispositivo móvel suporta em URLs marcados. Dispositivos recentes normalmente não têm limite.
* **Duração** máxima do URL do navegador móvel: O número máximo de bytes que o dispositivo móvel suporta em URLs. Dispositivos recentes normalmente não têm limite.
* **Duração** máxima do email móvel: O número máximo de bytes suportados pelo dispositivo móvel em um email. Dispositivos recentes normalmente não têm limite.
* **Protocolos** de rede móvel: Os tipos de protocolo que o dispositivo suporta ao acessar a Internet. Os valores de exemplo incluem `"EDGE"`, `"GPRS"`, `"UMTS"`e `"LTE"`.
* **Sistema operacional móvel (obsoleto)**: Em vez disso, use a dimensão do sistema [](operating-systems.md) operacional.
* **Aperte móvel para falar**: Determina se o dispositivo suporta PTT (Pressione para falar), o que permite que o dispositivo móvel se comporte de forma semelhante a um rádio bidirecional. Dispositivos recentes normalmente não relatam esse recurso.
* **Altura** da tela móvel: A altura da tela, em pixels. Observe que os iPhones sempre reportam `"480"` devido à incapacidade de determinar a versão do dispositivo iPhone. Consulte a seção abaixo sobre como determinar a versão do dispositivo iPhone.
* **Tamanho** da tela móvel: As dimensões completas do dispositivo móvel em pixels. O tamanho de tela relatado não indica a orientação do dispositivo. Independentemente da orientação da tela, cada dispositivo possui uma resolução de tela fixa no relatório. O tamanho baseia-se na pesquisa que determina qual orientação é mais provável. You can see sizes such as `"768x1024"` and `"1024x768"` in the same report with each size representing one or more different devices.
* **Largura** da tela móvel: A largura da tela, em pixels.
* **Suporte** a vídeo móvel: Os formatos de arquivo de vídeo e os codecs suportados pelo dispositivo móvel. Existem vários valores de dimensão para diferentes codecs de arquivos MP4 e 3GPP. Os valores nesta dimensão não são mutuamente exclusivos; uma única ocorrência pode atribuir a vários valores de dimensão.

## Separação do iPhone por modelo ou versão

Os dispositivos móveis relatam a versão do firmware na sequência do agente do usuário, não a versão do dispositivo. Por exemplo, um iPhone de geração atual contém um agente de usuário idêntico à última geração do iPhone se ele estiver na mesma versão de firmware. Como não há como determinar a versão do dispositivo do iPhone usando JavaScript, todos os iPhones pertencem ao mesmo bucket. As dimensões móveis são estritamente baseadas em pesquisas que fazem referência ao agente do usuário, portanto, você descobrirá que todos os iPhones relatam um tamanho de tela móvel de `320 x 480`.

Se você quiser coletar a versão do dispositivo iPhone, há duas maneiras de contornar essa limitação.

* **Use o iOS SDK**: O SDK móvel contém dimensões que expõem a versão do dispositivo para uso no relatórios. Esse método é mais ideal para aplicativos móveis do que para sites.
* **Use outras variáveis disponíveis por meio do JavaScript**: Algumas variáveis, como `screen.height` e `screen.width`, podem ser usadas para inferir a versão do dispositivo. Por exemplo, você pode usar o seguinte snippet de código no seu site:

   ```js
   if (navigator.userAgent.indexOf('iPhone') > -1) {
     s.eVarXX = screen.width + "x" + screen.height;
     }
   ```

   Este bloco de código detecta primeiro se o dispositivo é um iPhone. Se estiver, o código usa JavaScript para inserir a resolução da tela em uma eVar. Esse método permite que você detecte aproximadamente a versão do dispositivo se as resoluções de tela forem exclusivas.
