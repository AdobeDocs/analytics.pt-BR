---
title: Cidades
description: A cidade de onde a ocorrência se originou.
exl-id: c04525bb-50d6-4d28-b5dc-335d089e184b
source-git-commit: 9770f8e04089ff339d912d1787679257c87c7caa
workflow-type: ht
source-wordcount: '319'
ht-degree: 100%

---

# Cidades

A dimensão &quot;Cidades&quot; informa a cidade de onde a ocorrência se originou. Essa dimensão é útil para ajudar a determinar a origem dos visitantes das cidades mais populares ao visitar seu site. Você poderia usar esses dados para se concentrar na publicidade local nessas cidades, como outdoors ou comerciais.

## Preencher esta dimensão com dados

Essa dimensão faz referência às regras de pesquisa internas da Adobe. O valor de pesquisa se baseia no endereço IP enviado com a ocorrência. A Adobe faz parceria com a [Digital Element](https://www.digitalelement.com/) para manter pesquisas entre o endereço IP e a cidade. Essa dimensão funciona imediatamente em todas as implementações.

## Itens de dimensão

Os itens de dimensão incluem cidades do mundo todo. Os valores de exemplo incluem `"New York (New York, United States)"`, `"Bangalore (Karnataka, India)"` ou `"London (London, United Kingdom)"`.

Alguns itens de dimensão podem incluir `"AOL"`, um provedor de serviço de acesso telefônico à Internet. Aos assinantes deste serviço é atribuído um ponto de acesso de acordo com o país onde o número da conta está estabelecido. Os usuários da AOL usam o endereço IP desse ponto de acesso. Como essa dimensão se baseia no endereço IP, a localização geográfica do ponto de acesso é usada em vez da localização real do visitante.

## Diferenças entre a localização informada e a real

Como essa dimensão se baseia no endereço IP, alguns cenários podem mostrar uma diferença entre a localização informada e a localização real:

* **Endereços IP que representam proxies corporativos**: esses visitantes podem aparecer como tráfego vindo da rede corporativa do usuário, que pode ser um local diferente se o usuário estiver trabalhando remotamente.
* **Endereços de IP remoto**: o direcionamento por IP móvel funciona em diferentes níveis, dependendo da localização e da rede. Um número de operadoras faz o backhaul do tráfego IP através de pontos de presença centralizados ou regionais.
* **Usuários do ISP satélite**: identificar a localização específica desses usuários é difícil, pois eles normalmente parecem se originar do local do uplink.
* **IPs militares ou governamentais**: representa as pessoas que viajam ao redor do mundo e entram pelo local onde moram, em vez da base ou escritório onde trabalham.
