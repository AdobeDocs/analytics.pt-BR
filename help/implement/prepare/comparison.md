---
title: Comparar métodos de implementação
description: Veja as vantagens de cada método de envio de dados para o Adobe Analytics.
exl-id: 19353255-6356-4426-a2ef-5a2672a00eca
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: c476a1a19ae514f75fce8bd8e6d447d85de67a84
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 39%

---

# Comparar métodos de implementação

Veja a comparação entre cada método de implementação do Adobe Analytics. Você pode usar essas tabelas para ajudar sua organização a determinar a maneira mais ideal de enviar dados para o Adobe. Clique em cada coluna para obter informações mais específicas.

## Web

| | [AppMeasurement](/help/implement/js/overview.md) | [Extensão do Adobe Analytics](/help/implement/launch/overview.md) | [Web SDK](/help/implement/aep-edge/web-sdk/overview.md#web-sdk) | [Extensão SDK da Web](/help/implement/aep-edge/web-sdk/overview.md#web-sdk-extension) |
| --- | --- | --- | --- | --- |
| Requisitos de implementação | Referencie `AppMeasurement.js` em cada página, defina variáveis e envie dados usando `s.t()` para o Adobe Analytics | Carregador de tag de referência em cada página, use a interface da Coleção de dados para definir variáveis e enviar dados para a Adobe Analytics | Referencie `Alloy.js` em cada página, use `alloy("sendEvent",{})` para compor objetos XDM e enviar os dados desejados usando o Edge Network para o Adobe Analytics | Carregador de tag de referência em cada página, use a interface da Coleção de dados para compor objetos XDM e enviar os dados desejados usando o Edge Network para a Adobe Analytics |
| Destino dos dados | Enviado diretamente para o Adobe Analytics | Enviado diretamente para o Adobe Analytics | Enviado para a Adobe Experience Platform Edge, que encaminha dados para o Adobe Analytics | Enviado para a Adobe Experience Platform Edge, que encaminha dados para o Adobe Analytics |
| Dificuldade em fazer ajustes de implementação | Requer acesso ao código do site para cada alteração de implementação | Alterar o código do site uma vez para instalar a tag loader; todas as atualizações de implementação adicionais podem ser feitas na interface da Coleção de dados | Requer acesso ao código do site para cada alteração de implementação | Alterar o código do site uma vez para instalar a tag loader; todas as atualizações de implementação adicionais podem ser feitas na interface da Coleção de dados |
| Como o A4T é tratado | As chamadas do A4T são incluídas nas ocorrências enviadas para a Adobe | As chamadas do A4T são incluídas nas ocorrências enviadas para a Adobe | Chamadas do A4T são enviadas como ocorrências separadas | Chamadas do A4T são enviadas como ocorrências separadas |
| Dados de contexto | Usar `s.contextData`. | Usar `s.contextData` em blocos de código personalizado | Todos os campos não mapeados são enviados automaticamente como `a.x.*` variáveis de dados de contexto. | Todos os campos não mapeados são enviados automaticamente como `a.x.*` variáveis de dados de contexto. |

{style="table-layout:auto"}

## Mobile e outros

>[!CAUTION]
>
>O suporte à versão 4 dos SDKs móveis terminou em 31 de agosto de 2021. Consulte [Perguntas frequentes sobre o fim da vida útil do Adobe Mobile Services](https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html) para obter mais informações.


| | [SDK móvel](/help/implement/aep-edge/mobile-sdk/overview.md) | [API de servidor](/help/implement/aep-edge/server-api/overview.md) |
| --- | --- | --- |
| Requisitos de implementação | Referencie o carregador de tags no aplicativo e, em seguida, use chamadas diretas de API ou regras na interface da coleção de dados para compor objetos XDM e enviar os dados desejados usando o Edge Network para a Adobe Analytics | Use as APIs do servidor de Edge Network para compor objetos XDM e enviar os dados desejados usando o Edge Network para o Adobe Analytics |
| Destino dos dados | Enviado para a Adobe Experience Platform Edge, que encaminha dados para o Adobe Analytics | Enviado para a Adobe Experience Platform Edge, que encaminha dados para o Adobe Analytics |
| Dificuldade em fazer ajustes de implementação | Altere o código do aplicativo em que as chamadas diretas à API são feitas ou faça alterações na interface da Coleção de dados | Requer acesso ao código do aplicativo para cada alteração de implementação |
| Como o A4T é tratado | Chamadas do A4T são enviadas como ocorrências separadas | Chamadas do A4T são enviadas como ocorrências separadas |
| Dados de contexto | Todos os campos não mapeados são enviados automaticamente como `a.x.*` variáveis de dados de contexto. | Todos os campos não mapeados são enviados automaticamente como `a.x.*` variáveis de dados de contexto |

{style="table-layout:auto"}
