---
title: Rastrear em tipos diferentes de implementação
description: Use diferentes tipos de implementação e rastreie os visitantes facilmente entre eles.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 779ba5b0a1d71467aaaf3872fd707cc323ae8af2
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 59%

---

# Rastrear em tipos diferentes de implementação

A arquitetura principal de uma implementação do Adobe Analytics é consistente em todos os tipos de implementação. O processo envolve definir variáveis e compilá-las em uma solicitação de imagem que é enviada para servidores de coleção de dados da Adobe. Esse conceito significa que você pode alternar perfeitamente entre o AppMeasurement, o SDK da Web e suas respectivas extensões na Coleção de dados da Adobe Experience Platform em diferentes páginas do mesmo site.

A Adobe recomenda manter a consistência na implementação de um site, usando o mesmo tipo de implementação em todas as páginas. No entanto, se partes do site tiverem requisitos diferentes, você poderá usar esta página para ajudar a garantir que os visitantes sejam acompanhados consistentemente entre as páginas.

Se você usar mais de um tipo de implementação (como AppMeasurement e solicitações de imagem codificadas), verifique se as variáveis a seguir estão definidas corretamente e se correspondem umas às outras.

>[!NOTE]
>
>Todos os tipos de implementações devem usar o mesmo tipo de identificação de visitante (ID do Analytics herdada ou Serviço de ID de visitante). A Adobe recomenda usar o Serviço de ID de visitante em todas as implementações, quando possível.

| Variável | AppMeasurement | Extensão do Analytics | Web SDK (Alloy) | Extensão da tag do SDK da web | Solicitação de imagem codificada |
| --- | --- | --- | --- | --- | --- |
| ID do conjunto de relatórios | Argumento de cadeia de caracteres em [`s_gi`](../vars/functions/s-gi.md) | [!UICONTROL Conjuntos de relatórios] na seção [!UICONTROL Gerenciamento de biblioteca] quando [Configurar a extensão](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=pt-BR) | Adicione o Adobe Analytics como um serviço ao [Configurar uma sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=pt-BR) | Adicione o Adobe Analytics como um serviço ao [Configurar uma sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=pt-BR) | Parte do URL `pathname` (após `/b/ss/`) |
| Serviço de ID da Experience Cloud | Implementação [`VisitorAPI.js`](appmeasurement.md) | Usar a [extensão do Experience Cloud ID Service](analytics-extension.md) | [Incluído nativamente](alloy.md) | [Incluído nativamente](web-sdk-extension.md) | Fazer uma [chamada separada para o Serviço de ID](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html?lang=pt-BR) para obter a ID desejada e incluir `mid` na cadeia de caracteres de consulta |
| Domínio do Edge | A variável [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) | [!UICONTROL Servidor de Rastreamento SSL] na seção [!UICONTROL Geral] ao [Configurar a extensão](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=pt-BR) | A propriedade `edgeDomain` ao [Configurar o SDK da Web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=pt-BR) | O campo [!UICONTROL Domínio do Edge] ao [Configurar a extensão](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=pt-BR) | O `hostname` do URL de solicitação de imagem |

Se qualquer uma dessas variáveis não for consistente em cada tipo de implementação, a Adobe poderá considerá-las como visitantes separados. Se os visitantes não forem acompanhados perfeitamente em todos os tipos de implementação do site, o motivo mais comum é que o Serviço de ID está configurado incorretamente. Certifique-se de que cada tipo de implementação obtenha corretamente a mesma Experience Cloud ID (`mid`) em seu site.
