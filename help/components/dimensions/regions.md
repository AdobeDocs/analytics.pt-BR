---
title: Regiões
description: A região geográfica do visitante.
feature: Dimensions
exl-id: 95ab4c7e-71e8-490f-88a4-25201331d848
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '342'
ht-degree: 100%

---

# Regiões

A dimensão “Regiões” informa a região geográfica do visitante. É uma área geográfica menor do que um país e maior do que uma cidade. Em alguns países, uma região é um estado, ou município. Em outras áreas, é um país constituinte, departamento ou região metropolitana. O uso dessa dimensão é valioso se você quiser informações mais granulares que [países](countries.md), mas não tão granulares quanto [cidades](cities.md).

## Preencher esta dimensão com dados

Essa dimensão faz referência às regras de pesquisa internas da Adobe. O valor de pesquisa se baseia no endereço IP enviado com a ocorrência. A Adobe faz parceria com a [Digital Element](https://www.digitalelement.com/pt-pt/) para manter pesquisas entre o endereço IP e o país. Essa dimensão funciona imediatamente em todas as implementações.

## Itens de dimensão

Os itens de dimensão incluem regiões e o país em que a região está. Os valores de exemplo incluem `"California (United States)"`, `"Tokyo (Japan)"` ou `"Sao Paulo (Brazil)"`.

Alguns itens de dimensão podem incluir `"AOL"`, um provedor de serviço de acesso telefônico à Internet. Aos assinantes deste serviço é atribuído um ponto de acesso de acordo com o país onde o número da conta está estabelecido. Os usuários da AOL usam o endereço IP desse ponto de acesso. Como essa dimensão se baseia no endereço IP, a localização geográfica do ponto de acesso é usada em vez da localização real do visitante.

## Diferenças entre a localização informada e a real

Como essa dimensão se baseia no endereço IP, alguns cenários podem mostrar uma diferença entre a localização informada e a localização real:

* **Endereços IP que representam proxies corporativos**: esses visitantes podem aparecer como tráfego vindo da rede corporativa do usuário, que pode ser um local diferente se o usuário estiver trabalhando remotamente.
* **Endereços de IP remoto**: o direcionamento por IP móvel funciona em diferentes níveis, dependendo da localização e da rede. Um número de operadoras faz o backhaul do tráfego IP através de pontos de presença centralizados ou regionais.
* **Usuários do ISP satélite**: identificar a localização específica desses usuários é difícil, pois eles normalmente parecem se originar do local do uplink.
* **IPs militares ou governamentais**: representa as pessoas que viajam ao redor do mundo e entram pelo local onde moram, em vez da base ou escritório onde trabalham.
