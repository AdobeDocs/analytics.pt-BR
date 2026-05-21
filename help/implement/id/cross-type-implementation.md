---
title: Rastrear em tipos diferentes de implementação
description: Use diferentes tipos de implementação e rastreie os visitantes facilmente entre eles.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/FM6c33rpXxzy1huu8KE0VBkfe4FGIySczmVMrprFEUY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 444
ht-degree: 61%

---

# Rastrear em tipos diferentes de implementação

A arquitetura principal de uma implementação do Adobe Analytics é consistente em todos os tipos de implementação. O processo envolve definir variáveis e compilá-las em uma solicitação de imagem que é enviada para servidores de coleção de dados da Adobe. Esse conceito significa que você pode alternar perfeitamente entre o AppMeasurement, o SDK da Web e suas respectivas extensões na Coleção de dados da Adobe Experience Platform em diferentes páginas do mesmo site.

A Adobe recomenda manter a consistência na implementação de um site, usando o mesmo tipo de implementação em todas as páginas. No entanto, se partes do site tiverem requisitos diferentes, você poderá usar esta página para ajudar a garantir que os visitantes sejam acompanhados consistentemente entre as páginas.

Se você usar mais de um tipo de implementação (como AppMeasurement e solicitações de imagem codificadas), verifique se as variáveis a seguir estão definidas corretamente e se correspondem umas às outras.

>[!NOTE]
>
>Todos os tipos de implementações devem usar o mesmo tipo de identificação de visitante (ID do Analytics herdada ou Serviço de ID de visitante). A Adobe recomenda usar o Serviço de ID de visitante em todas as implementações, quando possível.

| Variável | Extensão da tag do SDK da web | Web SDK (Alloy) | Extensão do Analytics | AppMeasurement | Solicitação de imagem codificada |
|---|---|---|---|---|---|
| ID do conjunto de relatórios | Adicione o Adobe Analytics como um serviço ao [Configurar uma sequência de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/datastreams/configure) | Adicione o Adobe Analytics como um serviço ao [Configurar uma sequência de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/datastreams/configure) | [!UICONTROL Conjuntos de relatórios] na seção [!UICONTROL Gerenciamento de biblioteca] quando [Configurar a extensão](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/analytics/overview) | Argumento de cadeia de caracteres em [`s_gi`](../vars/functions/s-gi.md) | Parte do URL `pathname` (após `/b/ss/`) |
| Serviço de ID da Experience Cloud | [Incluído nativamente](web-sdk-extension.md) | [Incluído nativamente](alloy.md) | Usar a [extensão do Experience Cloud ID Service](analytics-extension.md) | Implementação [`VisitorAPI.js`](appmeasurement.md) | Fazer uma [chamada separada para o Serviço de ID](https://experienceleague.adobe.com/pt-br/docs/id-service/using/implementation/direct-integration) para obter a ID desejada e incluir `mid` na cadeia de caracteres de consulta |
| Domínio do Edge | O campo [!UICONTROL Domínio do Edge] ao [Configurar a extensão](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) | A propriedade `edgeDomain` ao [Configurar o SDK da Web](https://experienceleague.adobe.com/pt-br/docs/experience-platform/web-sdk/commands/configure/overview) | [!UICONTROL Servidor de Rastreamento SSL] na seção [!UICONTROL Geral] ao [Configurar a extensão](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/analytics/overview) | A variável [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) | O `hostname` do URL de solicitação de imagem |

Se qualquer uma dessas variáveis não for consistente em cada tipo de implementação, a Adobe provavelmente as considerará como visitantes separados. Se os visitantes não forem acompanhados perfeitamente em todos os tipos de implementação do site, o motivo mais comum é que o Serviço de ID está configurado incorretamente. Certifique-se de que cada tipo de implementação obtenha corretamente a mesma Experience Cloud ID (`mid`) em seu site.
