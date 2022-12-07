---
title: Países
description: O país de onde a ocorrência se originou.
feature: Dimensions
exl-id: 47704b08-215d-4d2d-bcd4-1789e308c1c6
source-git-commit: 146d622f370fd7469a8e5f0f2fe68cb31fa91844
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 77%

---

# Países

A dimensão &quot;Países&quot; informa o país de onde a ocorrência se originou. Essa dimensão é útil para ajudar a determinar a origem dos visitantes dos países mais populares ao visitar seu site. Você pode usar esses dados para se concentrar nos esforços de marketing nesses países ou para garantir que a experiência do seu site seja ideal em países que têm idiomas principais diferentes.

## Preencher esta dimensão com dados

Essa dimensão faz referência às regras de pesquisa internas da Adobe. O valor de pesquisa se baseia no endereço IP enviado com a ocorrência. A Adobe faz parceria com a [Digital Element](https://www.digitalelement.com/pt-pt/) para manter pesquisas entre o endereço IP e o país. Essa dimensão funciona imediatamente em todas as implementações.

## Itens de dimensão

Os itens de dimensão incluem países em todo o mundo. Os valores de exemplo incluem `"United States"`, `"United Kingdom"` ou `"India"`.

## Diferenças entre a localização informada e a real

Como essa dimensão se baseia no endereço IP, alguns cenários podem mostrar uma diferença entre a localização informada e a localização real:

* **Endereços IP que representam proxies corporativos**: esses visitantes podem aparecer como tráfego vindo da rede corporativa do usuário, que pode ser um local diferente se o usuário estiver trabalhando remotamente.
* **Endereços de IP remoto**: o direcionamento por IP móvel funciona em diferentes níveis, dependendo da localização e da rede. Um número de operadoras faz o backhaul do tráfego IP através de pontos de presença centralizados ou regionais.
* **Usuários do ISP satélite**: identificar a localização específica desses usuários é difícil, pois eles normalmente parecem se originar do local do uplink.
* **IPs militares ou governamentais**: representa as pessoas que viajam ao redor do mundo e entram pelo local onde moram, em vez da base ou escritório onde trabalham.
* **Proxies que obscurecem endereços IP por motivos de privacidade**: Serviços como Apple Private Relay ocultam o endereço IP real enviando dados aleatoriamente por meio de um intermediário ou proxy. Em seguida, esse proxy substitui um endereço IP diferente antes do encaminhamento para o Adobe.
