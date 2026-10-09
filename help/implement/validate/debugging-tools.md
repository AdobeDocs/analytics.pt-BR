---
title: Ferramentas de depuração para implementações do Analytics
description: Inspecione os dados que sua implementação envia para o Adobe usando depuradores do Analytics, ferramentas de desenvolvedor do navegador e proxies de depuração HTTP.
keywords: analisador de pacotes, monitor de pacotes, sniffer de pacotes, depurador, charles, NS_BINDING_ABORTED, sendBeacon
feature: Implementation Basics
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/debgxI3FK1fp1Q02GY1-0H40z-L4G2HSmq11Tog97-Y'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e992d880-33bc-4949-a648-aa7d410276cd
    internal-label: Validation
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 1cbafc8cee90cbf213b8cd68768e017ff24d268a
workflow-type: tm+mt
source-wordcount: '991'
ht-degree: 3%
---
# Ferramentas de depuração para implementações do Analytics

As ferramentas de depuração, às vezes chamadas de analisadores de pacotes ou sniffers de pacotes, permitem inspecionar os dados enviados pela implementação para o Adobe. Eles podem ajudar você a confirmar se as solicitações do são acionadas com êxito, inspecionar as variáveis e cargas incluídas nessas solicitações e solucionar problemas de comportamento de implementação inesperado.

>[!NOTE]
>
>As ferramentas listadas nesta página não são abrangentes. Elas representam ferramentas que os clientes do Adobe Analytics consideraram úteis. Com exceção das ferramentas fornecidas pela Adobe, a Adobe não oferece suporte ou solução de problemas para esses produtos. Consulte o editor da ferramenta para obter informações sobre instalação, uso e suporte.

## Escolha uma ferramenta de depuração

As categorias a seguir podem ajudá-lo a selecionar uma ferramenta com base no que você deseja inspecionar.

| Tipo de ferramenta | Útil quando |
| --- | --- |
| **Depuradores de tags e do Analytics** | Você deseja que variáveis do Analytics, tags, camadas de dados ou solicitações de coleção sejam interpretadas e apresentadas em um formato legível. |
| **Ferramentas para desenvolvedores de navegador** | Você está depurando uma implementação da Web e deseja inspecionar as solicitações de rede diretamente sem instalar um aplicativo de depuração separado. |
| **Proxies de depuração de HTTP(S)** | Você deseja inspecionar o tráfego HTTP de navegadores, aplicativos móveis, WebViews, APIs ou outros clientes, ou precisa de recursos além das ferramentas de desenvolvedor do navegador. |

## Analytics e depuradores de tags

O Analytics e os depuradores de tags reconhecem as tecnologias analíticas e interpretam suas solicitações. Essas ferramentas podem facilitar a identificação de variáveis do Adobe Analytics, cargas do Experience Platform Web SDK, tags e informações de implementação relacionadas sem decodificar manualmente as solicitações de rede.

| Ferramenta | Disponibilidade | Útil para | Considerações |
| --- | --- | --- | --- |
| **[Adobe Experience Platform Debugger](https://experienceleague.adobe.com/pt-br/docs/experience-platform/debugger/home)** | Extensão do navegador | Depuração de implementações do Adobe Experience Platform e do CX Enterprise, incluindo Adobe Analytics, tags, camadas de dados e Experience Platform Web SDK | Ferramenta fornecida pela Adobe com foco nas tecnologias Adobe |
| **[Omnibug](https://omnibug.io)** | Navegadores baseados em Chromium e Firefox | Decodificação do Adobe Analytics, Experience Platform Web SDK, tags do Adobe e solicitações de vários outros fornecedores de análise e marketing | Útil para implementações que contêm tecnologias de vários fornecedores |
| **[Depurador do ObservePoint](https://www.observepoint.com/solutions/observepoint-debugger/)** | CHROME e EDGE | Inspeção e decodificação de tags de análise, marketing e medição, incluindo solicitações do Adobe Analytics | Depurador baseado em navegador; o ObservePoint também oferece produtos de validação de implementação automatizada separados |
| **[Adobe Experience Platform Assurance](https://experienceleague.adobe.com/pt-br/docs/experience-platform/assurance/home)** | Aplicativo web no CX Enterprise | Inspeção e validação de eventos de implementações do Mobile SDK e visualização de como o Edge Network processou eventos | ferramenta fornecida pela Adobe; conecte seu aplicativo a uma sessão do Assurance para ver seus eventos |

## Ferramentas de desenvolvedor do navegador

Todo navegador moderno inclui ferramentas de desenvolvedor que podem inspecionar solicitações de rede, de modo que geralmente você não precisa de uma ferramenta separada para depurar uma implementação da Web. Pressione **F12** ou **Ctrl+Shift+I** (Windows e Linux) ou **Cmd+Option+I** (macOS) e selecione a guia **Rede**. No Safari, primeiro habilite os recursos do desenvolvedor nas configurações **Avançadas** do Safari.

## Proxies de depuração HTTP(S)

Os proxies de depuração HTTP interceptam o tráfego HTTP e HTTPS entre um cliente e um servidor. Elas são úteis quando as ferramentas do desenvolvedor do navegador não fornecem visibilidade suficiente ou quando a implementação é executada fora de um navegador da Web tradicional.

A inspeção de HTTPS geralmente requer a configuração do cliente para confiar em um certificado fornecido pelo proxy de depuração. Siga as políticas de segurança de sua organização ao instalar certificados ou interceptar tráfego criptografado.

| Ferramenta | Útil para |
| --- | --- |
| **[Charles](https://www.charlesproxy.com/)** | Inspeção de navegador, aplicativo, dispositivo móvel e outro tráfego HTTP(S) |
| **[Fiddler em todos os locais](https://www.telerik.com/fiddler/fiddler-everywhere)** | Captura e inspeção do tráfego HTTP(S) em aplicativos e dispositivos. Distinto do antigo produto Fiddler Classic. |
| **[Proxyman](https://proxyman.com/)** | Inspeção e modificação do tráfego HTTP(S) de navegadores, aplicativos e dispositivos móveis |
| **[Kit de ferramentas HTTP](https://httptoolkit.com/)** | Inspeção de tráfego de aplicativos, APIs, ambientes de desenvolvimento e dispositivos móveis, com fluxos de trabalho orientados para a depuração de aplicativos e API |
| **[mitmproxy](https://www.mitmproxy.org/)** | Interceptação HTTP(S) com script, inspeção e modificação por meio de interfaces de linha de comando e da Web. Mais adequado para usuários familiarizados com fluxos de trabalho de linha de comando. |

## Localizar solicitações do Adobe Analytics

Para implementações que enviam dados diretamente para o Adobe Analytics, como o AppMeasurement, filtre solicitações de rede para:

```text
/ss/
```

As solicitações de coleção do Adobe Analytics contêm variáveis do Analytics no URL da solicitação ou na carga. Solicitações brutas usam nomes de parâmetro de consulta em vez de nomes de variáveis; por exemplo, eVar1 aparece como `v1` e prop1 aparece como `c1`. Os depuradores do Analytics decodificam esses nomes para você. Para decodificá-los, consulte a [referência da variável](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference) na documentação da API de inserção de dados.

Para obter os códigos de status HTTP retornados pelos servidores de coleta de dados do Analytics, consulte [Códigos de resposta HTTP](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting#http-response-codes) na documentação da API de inserção de dados.

Para implementações que usam o Adobe Experience Platform Web SDK, filtre as solicitações de rede para:

```text
/ee/
```

Selecione a solicitação e inspecione a carga para visualizar os dados enviados para o Adobe Experience Platform Edge Network. O Web SDK envia dados para o Edge Network, que pode então encaminhar dados para o Adobe Analytics e outros serviços configurados. A inspeção da solicitação do cliente verifica o que o navegador enviou para o Edge Network; ela não confirma por si só que os dados foram processados com êxito por cada serviço downstream. Para ver como o Edge Network processou um evento, use o [Adobe Experience Platform Assurance](https://experienceleague.adobe.com/pt-br/docs/experience-platform/assurance/home).

## Solicitações canceladas

Quando uma página sai, o navegador pode cancelar solicitações que ainda estão em andamento. O Firefox rotula essas solicitações `NS_BINDING_ABORTED`; o Chrome e o Edge as rotulam `(canceled)`. Para manter as solicitações visíveis após a navegação, habilite **Preservar log** (Chrome e Edge) ou **Persistir Logs** (Firefox).

Uma solicitação cancelada não significa necessariamente que os dados foram perdidos. O navegador pode ter enviado a solicitação completa e parado de aguardar apenas a resposta. As ferramentas de desenvolvedor do navegador geralmente não podem mostrar a diferença, mas um proxy de depuração HTTP pode.

Solicitações enviadas com `navigator.sendBeacon()` não são canceladas na navegação. A AppMeasurement usa `sendBeacon` para links de saída e sempre que [`useBeacon`](/help/implement/vars/config-vars/usebeacon.md) está habilitado. O Web SDK o usa para eventos enviados com [`documentUnloading`](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/js/commands/sendevent/documentunloading). Se as solicitações de rastreamento de link forem canceladas com frequência, use essas opções.
