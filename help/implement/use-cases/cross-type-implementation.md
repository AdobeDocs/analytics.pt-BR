---
title: Rastrear em tipos diferentes de implementação
description: Use diferentes tipos de implementação e rastreie os visitantes facilmente entre eles.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
source-git-commit: 90914569256cf891cb3cf693843e7cf9ede2f4ce
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 14%

---

# Rastrear em tipos diferentes de implementação

A arquitetura principal de uma implementação do Adobe Analytics é consistente em todos os tipos de implementação. O processo envolve definir e compilá-las em uma solicitação de imagem enviada para servidores de coleta de dados Adobe. Esse conceito significa que você pode alternar facilmente entre o AppMeasurement, o SDK da Web e suas respectivas extensões na Coleta de dados do Adobe Experience Platform em diferentes páginas do mesmo site.

O Adobe recomenda manter a consistência na implementação de um site, usando o mesmo tipo de implementação em todas as páginas. No entanto, se partes do site tiverem requisitos diferentes, você poderá usar esta página para ajudar a garantir que os visitantes sejam acompanhados consistentemente entre páginas.

Se você usar mais de um tipo de implementação (como AppMeasurement e solicitações de imagem codificadas), verifique se as variáveis a seguir estão definidas corretamente e se correspondem:

| Variável | AppMeasurement | Extensão do Analytics | SDK da Web | Extensão do SDK da Web | Solicitação de imagem codificada |
| --- | --- | --- | --- | --- | --- |
| ID do conjunto de relatórios | Argumento da string dentro de [`s_gi`](../vars/functions/s-gi.md) | [!UICONTROL Conjuntos de relatórios] nos termos do [!UICONTROL Gerenciamento de biblioteca] seção quando [Configurar a extensão](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | Adicionar o Adobe Analytics como um serviço ao [Configurar um conjunto de dados](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | Adicionar o Adobe Analytics como um serviço ao [Configurar um conjunto de dados](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | Parte do URL `pathname` (após `/b/ss/`) |
| Servidor de rastreamento | O [`trackingServer`](../vars/config-vars/trackingserver.md) e [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) variables | [!UICONTROL Servidor de rastreamento] e [!UICONTROL Servidor de rastreamento de SSL] nos termos do [!UICONTROL Geral] seção quando [Configurar a extensão](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | O `edgeDomain` propriedade when [Configuração do SDK da Web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=pt-BR) | O [!UICONTROL Domínio de borda] when [Configurar a extensão](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=pt-BR) | O `hostname` do URL da solicitação de imagem |
| Serviço da Experience Cloud ID | Implementar [`VisitorAPI.js`](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=pt-BR) | Use o [Extensão do Adobe Experience Cloud ID Service](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Use o [Extensão do Adobe Experience Cloud ID Service](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Use o [Extensão do Adobe Experience Cloud ID Service](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Faça uma [chamada separada para os servidores do serviço de ID](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html) para obter a ID desejada |

{style=&quot;table-layout:auto&quot;}

Se qualquer uma dessas variáveis não for consistente em cada tipo de implementação, o Adobe as considerará como visitantes separados. Se os visitantes não forem acompanhados com facilidade em todos os tipos de implementação do site, o motivo mais comum é que o Serviço de ID está configurado incorretamente. Consulte [Métodos de implementação](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-methods.html) no guia do usuário do Serviço de ID para obter mais informações.
