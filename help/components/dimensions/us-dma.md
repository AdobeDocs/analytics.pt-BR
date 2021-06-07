---
title: DMA dos EUA
description: A área de mercado designada da ocorrência.
exl-id: 156d5755-2e93-4240-bde3-1d537422b7bf
source-git-commit: 9770f8e04089ff339d912d1787679257c87c7caa
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 100%

---

# DMA dos EUA

A dimensão “DMA dos EUA” informa a área de mercado designada (DMA) do visitante. Tem como base os mercados de mídia compilados pela [Nielsen](https://www.nielsen.com/us/en/intl-campaigns/dma-maps/).

## Preencher esta dimensão com dados

Essa dimensão faz referência às regras de pesquisa internas da Adobe. O valor de pesquisa se baseia no endereço IP enviado com a ocorrência. A Adobe faz parceria com a Nielsen para manter pesquisas entre o endereço IP e o DMA. Essa dimensão funciona imediatamente em todas as implementações.

## Itens de dimensão

Os itens de dimensão incluem o DMA e o código DMA do visitante. O código de 3 dígitos não é um CEP, mas sim o código DMA da Nielsen. Os valores de exemplo incluem `"Dallas-Ft. Worth (623)"`, `"New York (501)"` ou `"Los Angeles (803)"`. O item de dimensão `"No Metro (0)"` inclui todo o tráfego internacional fora dos Estados Unidos.

## Diferenças entre a localização informada e a real

Como essa dimensão se baseia no endereço IP, alguns cenários podem mostrar uma diferença entre a localização informada e a localização real:

* **Endereços IP que representam proxies corporativos**: esses visitantes podem aparecer como tráfego vindo da rede corporativa do usuário, que pode ser um local diferente se o usuário estiver trabalhando remotamente.
* **Endereços de IP remoto**: o direcionamento por IP móvel funciona em diferentes níveis, dependendo da localização e da rede. Um número de operadoras faz o backhaul do tráfego IP através de pontos de presença centralizados ou regionais.
* **Usuários do ISP satélite**: identificar a localização específica desses usuários é difícil, pois eles normalmente parecem se originar do local do uplink.
* **IPs militares ou governamentais**: representa as pessoas que viajam ao redor do mundo e entram pelo local onde moram, em vez da base ou escritório onde trabalham.
