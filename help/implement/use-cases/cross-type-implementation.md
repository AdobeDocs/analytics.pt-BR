---
title: Rastrear em tipos diferentes de implementação
description: Use diferentes tipos de implementação e rastreie os visitantes facilmente entre eles.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 100%

---

# Rastrear em tipos diferentes de implementação

A arquitetura principal de uma implementação do Adobe Analytics é consistente em todos os tipos de implementação. O processo envolve definir variáveis e compilá-las em uma solicitação de imagem que é enviada para servidores de coleção de dados da Adobe. Esse conceito significa que você pode alternar perfeitamente entre o AppMeasurement, o SDK da Web e suas respectivas extensões na Coleção de dados da Adobe Experience Platform em diferentes páginas do mesmo site.

A Adobe recomenda manter a consistência na implementação de um site, usando o mesmo tipo de implementação em todas as páginas. No entanto, se partes do site tiverem requisitos diferentes, você poderá usar esta página para ajudar a garantir que os visitantes sejam acompanhados consistentemente entre as páginas.

Se você usar mais de um tipo de implementação (como AppMeasurement e solicitações de imagem codificadas), certifique se de que as seguintes variáveis foram definidas corretamente e se correspondem:

| Variável | AppMeasurement | Extensão do Analytics | SDK da Web | Extensão do SDK da Web | Solicitação de imagem codificada |
| --- | --- | --- | --- | --- | --- |
| ID do conjunto de relatórios | Argumento da string dentro de [`s_gi`](../vars/functions/s-gi.md) | [!UICONTROL Conjuntos de relatórios] na seção [!UICONTROL Gerenciamento de biblioteca] quando [Configurar a extensão](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=pt-BR) | Adicione o Adobe Analytics como um serviço ao [Configurar uma sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=pt-BR) | Adicione o Adobe Analytics como um serviço ao [Configurar uma sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=pt-BR) | Parte do URL `pathname` (após `/b/ss/`) |
| Servidor de rastreamento | As variáveis [`trackingServer`](../vars/config-vars/trackingserver.md) e [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) | [!UICONTROL Servidor de rastreamento] e [!UICONTROL Servidor de rastreamento SSL] na seção [!UICONTROL Geral] ao [Configurar a extensão](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=pt-BR) | A propriedade `edgeDomain` ao [Configurar o SDK da Web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=pt-BR) | O [!UICONTROL Domínio de borda] ao [Configurar a extensão](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=pt-BR) | O `hostname` do URL de solicitação de imagem |
| Serviço de ID da Experience Cloud | Implementar [`VisitorAPI.js`](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=pt-BR) | Use a [extensão do Serviço de ID da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html?lang=pt-BR) | Use a [extensão do Serviço de ID da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html?lang=pt-BR) | Use a [extensão do Serviço de ID da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html?lang=pt-BR) | Faça uma [chamada separada para os servidores do serviço de ID](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html?lang=pt-BR) para obter a ID desejada |

{style="table-layout:auto"}

Se qualquer uma dessas variáveis não for consistente em todos os tipos de implementação, a Adobe os considerará como visitantes separados. Se os visitantes não forem acompanhados perfeitamente em todos os tipos de implementação do site, o motivo mais comum é que o Serviço de ID está configurado incorretamente. Consulte [Métodos de implementação](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-methods.html?lang=pt-BR) no guia do usuário do Serviço de ID para obter mais informações.
