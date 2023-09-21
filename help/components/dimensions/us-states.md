---
title: Estados dos Estados Unidos
description: O estado do visitante nos EUA.
feature: Dimensions
exl-id: d4506e59-c1ff-4348-912d-c1ad73278f56
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 85%

---

# Estado dos EUA

O &#39;estado dos EUA&#39; [dimension](overview.md) relata o estado do visitante nos Estados Unidos da América. É semelhante à dimensão [Regiões](regions.md), exceto que essa dimensão é específica dos Estados Unidos. O uso dessa dimensão é valioso se você quiser informações mais granulares que [países](countries.md), mas não tão granulares quanto [cidades](cities.md).

## Preencher esta dimensão com dados

Essa dimensão faz referência às regras de pesquisa internas da Adobe. O valor de pesquisa se baseia no endereço IP enviado com a ocorrência. A Adobe faz parceria com a [Digital Element](https://www.digitalelement.com/) para manter pesquisas entre o endereço IP e o país. Essa dimensão funciona imediatamente em todas as implementações.

## Itens de dimensão

Os itens de dimensão incluem regiões e o país em que a região está. Os valores de exemplo incluem `"California"`, `"Texas"` ou `"Virginia"`. O item de dimensão `"Unspecified"` inclui todo o tráfego internacional fora dos Estados Unidos.

Esta dimensão pode incluir `"AOL"`, um provedor de serviço de acesso telefônico à Internet. Os assinantes deste serviço recebem um ponto de acesso. Os usuários da AOL usam o endereço IP desse ponto de acesso. Como essa dimensão se baseia no endereço IP, a localização geográfica do ponto de acesso é usada em vez da localização real do visitante.

## Diferenças entre a localização informada e a real

Como essa dimensão se baseia no endereço IP, alguns cenários podem mostrar uma diferença entre a localização informada e a localização real:

* **Endereços IP que representam proxies corporativos**: esses visitantes podem aparecer como tráfego vindo da rede corporativa do usuário, que pode ser um local diferente se o usuário estiver trabalhando remotamente.
* **Endereços de IP remoto**: o direcionamento por IP móvel funciona em diferentes níveis, dependendo da localização e da rede. Um número de operadoras faz o backhaul do tráfego IP através de pontos de presença centralizados ou regionais.
* **Usuários do ISP satélite**: identificar a localização específica desses usuários é difícil, pois eles normalmente parecem se originar do local do uplink.
* **IPs militares ou governamentais**: representa as pessoas que viajam ao redor do mundo e entram pelo local onde moram, em vez da base ou escritório onde trabalham.
* **Proxies que obscurecem endereços IP por motivos de privacidade**: serviços como o Retransmissão privada da Apple ocultam o endereço IP verdadeiro, enviando dados aleatoriamente por meio de um intermediário ou proxy. Esse proxy substitui um endereço IP diferente antes de encaminhar para o Adobe.
