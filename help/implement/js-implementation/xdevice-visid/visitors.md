---
description: O Analytics conta cada ID de visitante efetivo exclusivo como visitante único.
keywords: Implementação do Analytics
seo-description: O Analytics conta cada ID de visitante efetivo exclusivo como visitante único.
seo-title: Visitantes
solution: Analytics
subtopic: Visitantes
title: Visitantes
topic: Desenvolvedor e implementação
uuid: 16cfdb64-a3c6-4056-97da-3227cddcf1cd
translation-type: ht
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Visitantes

>[!IMPORTANT]
>
>Esse método de identificação de visitantes entre dispositivos não é mais recomendado. Consulte a [Documentação de cooperação do dispositivo da Adobe Experience Cloud](https://marketing.adobe.com/resources/help/pt_BR/mcdc/).

O Analytics conta cada ID de visitante efetivo exclusivo como visitante único.

Se você observar a [tabela anterior](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA), isso ocorreu 3 vezes: nos hits 1, 9 e 10. Isso acontece porque a [!UICONTROL ID de visitante] efetiva é a mesma para ambas as chamadas de servidor, e ocorre embora as visitas possam estar a várias horas de diferença e em dispositivos diferentes.

Esse procedimento pode aumentar o número de visitantes exclusivos que você vê quando a identificação de visitantes entre dispositivos está ativada. O visitante pode ser contado duas vezes na mesma visita: uma para a visita inicial e novamente depois que o usuário é autenticado.

Quando um visitante acessa seu site, o cookie `s_vi`é populado e armazenado. No servidor de coleta de dados, um novo perfil de visitante é criado para essa ID do visitante e a [!UICONTROL ID de visitante] efetiva do perfil é definida para corresponder ao cookie.

Quando a identificação do visitante entre dispositivos está ativada, se uma variável [!UICONTROL visitor ID] for fornecida em uma ocorrência subsequente (por exemplo, depois da autenticação), a [!UICONTROL ID de visitante] efetiva é atualizada para corresponder ao valor personalizado. Isso faz com que a [!UICONTROL ID de visitante] efetiva seja alterada diretamente depois da autenticação, o que resulta em várias contagens de visitantes.

![](assets/visitors.png)

Depois da associação inicial, as contagens de visitantes retornam ao normal, pois o visitante é associado por meio do cookie da [!UICONTROL ID de visitante]. Se posteriormente o visitante exibir seu site e se autenticar, a contagem de visitantes não será aumentada, pois a [!UICONTROL ID de visitante] efetiva não é alterada após a autenticação.

![](assets/visitors_2.png)

