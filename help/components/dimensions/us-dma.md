---
title: DMA dos EUA
description: A área de mercado designada da ocorrência.
feature: Dimensions
exl-id: 156d5755-2e93-4240-bde3-1d537422b7bf
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 64%

---

# DMA dos EUA

A [dimensão](overview.md) de &quot;DMA dos EUA&quot; informa a área de mercado designada (DMA) do visitante. Tem como base os mercados de mídia compilados pela [Nielsen](https://www.nielsen.com/dma-regions/).

## Preencher esta dimensão com dados

Essa dimensão faz referência às regras de pesquisa internas da Adobe. O valor de pesquisa se baseia no endereço IP enviado com a ocorrência. O Adobe faz parceria com a Nielsen para manter pesquisas entre o endereço IP e o DMA.

* Para implementações do AppMeasurement, essa dimensão funciona imediatamente.
* Para implementações do SDK da Web, habilite a [!UICONTROL Pesquisa Geográfica] ao [configurar uma sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-br).

## Itens de dimensão

Os itens de Dimension incluem os códigos DMA e DMA do visitante. O código de 3 dígitos não é um CEP, mas sim o código DMA da Nielsen. Os valores de exemplo incluem `"Dallas-Ft. Worth (623)"`, `"New York (501)"` ou `"Los Angeles (803)"`. O item de dimensão `"No Metro (0)"` inclui todo o tráfego internacional fora dos Estados Unidos.

## Diferenças entre a localização informada e a real

Como essa dimensão se baseia no endereço IP, alguns cenários podem mostrar uma diferença entre a localização informada e a localização real:

* **Endereços IP que representam proxies corporativos**: esses visitantes podem aparecer como tráfego vindo da rede corporativa do usuário, que pode ser um local diferente se o usuário estiver trabalhando remotamente.
* **Endereços de IP remoto**: o direcionamento por IP móvel funciona em diferentes níveis, dependendo da localização e da rede. Algumas operadoras fazem o backhaul do tráfego IP por meio de pontos de presença centralizados ou regionais.
* **Usuários do ISP satélite**: identificar a localização específica desses usuários é difícil, pois eles normalmente parecem se originar do local do uplink.
* **IPs militares ou governamentais**: representa as pessoas que viajam ao redor do mundo e entram pelo local onde moram, em vez da base ou escritório onde trabalham.
* **Proxies que obscurecem endereços IP por motivos de privacidade**: serviços como a Retransmissão Privada da Apple ocultam o endereço IP verdadeiro enviando dados aleatoriamente por meio de um intermediário ou proxy. Esse proxy substitui um endereço IP diferente antes de encaminhar para o Adobe.
