---
description: '[!DNL Activity Map] rastreia links com um algoritmo mais robusto que '
seo-description: '[!DNL Activity Map] rastreia links com um algoritmo mais robusto que '
seo-title: Rastreamento de links avançado
solution: Analytics
title: Rastreamento de links avançado
topic: Activity Map
uuid: a72b1652-2e69-41c7-8cf2-d39e9c705302
translation-type: tm+mt
source-git-commit: ae18932eda59c059e2aa635cc30f233b88840031

---


# Rastreamento de links avançado

[!DNL Activity Map] rastreia links com um algoritmo mais robusto que:

* Inclui o rastreamento de regiões da página para evitar casos em que o mesmo link seja confundido em diferentes dispositivos, pois o link é exibido em diferentes posições na página;
* Garante a singularidade do link, o que significa que links distintos não podem ser confundidos por causa de problemas com a LinkID ou pela diferença entre os navegadores.

For more on link tracking in [!DNL Activity Map], go [here](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md).

## How [!DNL Activity Map] link tracking may collect PII Data {#section_AEE57510D17B4C21A7D49D32D21D67B9}

> [!CAUTION] Ao ativar o [!DNL Activity Map] rastreamento, você pode coletar dados de informações de identificação pessoal (PII). Esses dados podem ser usados isoladamente ou com outras informações para identificar, contatar ou localizar uma única pessoa ou para identificar um indivíduo no contexto.

Here are some known cases where PII data might be collected using [!DNL Activity Map] Tracking:

* `Mailto` links. Um link mailto é um tipo de link HTML que ativa o cliente de email padrão no computador para enviar um email.
* `User ID` links que podem aparecer no cabeçalho/rodapé de um site depois que o usuário fizer logon.
* Para instituições financeiras, o número da conta pode ser mostrado como um link. Clicar nele coletará o texto do link.
* Sites de instituições de saúde também podem ter dados de PII mostrados como links. Clicar nesses links coletará o texto do link e, portanto, coletará dados de PII.
