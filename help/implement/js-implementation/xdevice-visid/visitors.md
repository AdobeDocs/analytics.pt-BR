---
description: O Analytics conta cada ID de visitante efetivo exclusivo como visitante único.
keywords: Implementação do Analytics
seo-description: O Analytics conta cada ID de visitante efetivo exclusivo como visitante único.
seo-title: Visitantes
solution: Analytics
subtopic: Visitantes
title: Visitantes
topic: Desenvolvedor e implementação
uuid: 16 cfdb 64-a 3 c 6-4056-97 da -3227 cddcf 1 cd
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Visitantes

>[!IMPORTANT]
>
>Não é mais recomendado este método de identificação de visitantes em dispositivos. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

O Analytics conta cada ID de visitante efetivo exclusivo como visitante único.

If you look at the [previous table](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA), this occurred 3 times: at hits 1, 9, and 10. Isso acontece porque a [!UICONTROL ID de visitante] efetiva é a mesma para ambas as chamadas de servidor, e ocorre embora as visitas possam estar a várias horas de diferença e em dispositivos diferentes.

Esse procedimento pode aumentar o número de visitantes exclusivos que você vê quando a identificação de visitantes entre dispositivos está ativada. O visitante pode ser contado duas vezes na mesma visita: uma para a visita inicial e novamente depois que o usuário é autenticado.

Quando um visitante acessa seu site, o cookie `s_vi` é populado e armazenado. No servidor de coleta de dados, um novo perfil de visitante é criado para essa ID do visitante e a [!UICONTROL ID de visitante] efetiva do perfil é definida para corresponder ao cookie.

Quando a identificação do visitante entre dispositivos está ativada, se uma variável [!UICONTROL visitor ID] for fornecida em uma ocorrência subsequente (por exemplo, depois da autenticação), a [!UICONTROL ID de visitante] efetiva é atualizada para corresponder ao valor personalizado. Isso faz com que a [!UICONTROL ID de visitante] efetiva seja alterada diretamente depois da autenticação, o que resulta em várias contagens de visitantes.

![](assets/visitors.png)

Depois da associação inicial, as contagens de visitantes retornam ao normal, pois o visitante é associado por meio do cookie da [!UICONTROL ID de visitante]. Se posteriormente o visitante exibir seu site e se autenticar, a contagem de visitantes não será aumentada, pois a [!UICONTROL ID de visitante] efetiva não é alterada após a autenticação.

![](assets/visitors_2.png)

