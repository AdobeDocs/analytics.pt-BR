---
description: 'O Activity Map rastreia os links com um algoritmo mais avançado '
title: Rastreamento de links avançado
topic: Activity map
uuid: a72b1652-2e69-41c7-8cf2-d39e9c705302
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Rastreamento de links avançado

O Activity Map rastreia os links com um algoritmo mais avançado:

* Inclui o rastreamento de regiões da página para evitar casos em que o mesmo link seja confundido em diferentes dispositivos, pois o link é exibido em diferentes posições na página;
* Garante a singularidade do link, o que significa que links distintos não podem ser confundidos por causa de problemas com a LinkID ou pela diferença entre os navegadores.

Para obter mais informações sobre o rastreamento de links no Activity Map, clique [aqui](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md).

## Como o Rastreamento de links do Activity Map pode coletar dados de PII {#section_AEE57510D17B4C21A7D49D32D21D67B9}

> [!CAUTION] Ao ativar o rastreamento do Activity Map, você poderá coletar dados de informações pessoalmente identificáveis (PII). Tais dados podem ser usados isoladamente ou junto a outras informações para identificar, contactar ou localizar uma pessoa, ou para identificar um indivíduo em um contexto.

Veja a seguir alguns casos conhecidos nos quais dados de PII podem ser coletados usando o Rastreamento do Activity Map:

* `Mailto` links. Um link mailto é um tipo de link HTML que ativa o cliente de email padrão no computador para enviar um email.
* `User ID` links que podem ser exibidos no cabeçalho/rodapé de um site depois que o usuário fizer logon.
* Para instituições financeiras, o número da conta pode ser mostrado como um link. Clicar nele coletará o texto do link.
* Sites de instituições de saúde também podem ter dados de PII mostrados como links. Clicar nesses links coletará o texto do link e, portanto, coletará dados de PII.
