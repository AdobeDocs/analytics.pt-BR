---
title: Cidades
description: A cidade de onde a ocorrência se originou.
translation-type: tm+mt
source-git-commit: fdc77997c8aea07cc7db1d06c5c0c2cd2f2abbd9
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 80%

---


# Cidades

A dimensão &quot;Cidades&quot; informa a cidade de onde a ocorrência se originou. Essa dimensão é útil para ajudar a determinar a origem dos visitantes das cidades mais populares ao visitar seu site. Você poderia usar esses dados para se concentrar na publicidade local nessas cidades, como outdoors ou comerciais.

## Preencher esta dimensão com dados

Essa dimensão faz referência às regras de pesquisa internas da Adobe. O valor de pesquisa se baseia no endereço IP enviado com a ocorrência. A Adobe faz parceria com a [Digital Element](https://www.digitalelement.com/?lang=pt-pt) para manter pesquisas entre o endereço IP e a cidade. Essa dimensão funciona imediatamente em todas as implementações.

>[!TIP]
>
>Se a sua organização seguir normas rigorosas de privacidade em que [ofuscar endereços IP](/help/admin/admin/general-acct-settings-admin.md) não for suficiente, você poderá solicitar a desativação total dos dados de geolocalização. Entre em contato com o Atendimento ao cliente com a ID do conjunto de relatórios e solicite a desativação de &quot;Geografia&quot; para o conjunto de relatórios.

## itens de Dimension

Os itens de Dimension incluem cidades em todo o mundo. Os valores de exemplo incluem `"New York (New York, United States)"`, `"Bangalore (Karnataka, India)"` ou `"London (London, United Kingdom)"`.

Alguns itens de dimensão podem incluir `"AOL"`, um provedor de serviço de acesso telefônico à Internet. Aos assinantes deste serviço é atribuído um ponto de acesso com base no país onde o número da conta está estabelecido. Os usuários da AOL usam o endereço IP desse ponto de acesso. Como essa dimensão se baseia no endereço IP, a localização geográfica do ponto de acesso é usada em vez da localização real do visitante.

## Diferenças entre a localização informada e a real

Como essa dimensão se baseia no endereço IP, alguns cenários podem mostrar uma diferença entre a localização informada e a localização real:

* **Endereços IP que representam proxies corporativos**: esses visitantes podem aparecer como tráfego vindo da rede corporativa do usuário, que pode ser um local diferente se o usuário estiver trabalhando remotamente.
* **Endereços de IP remoto**: o direcionamento por IP móvel funciona em diferentes níveis, dependendo da localização e da rede. Um número de operadoras faz o backhaul do tráfego IP através de pontos de presença centralizados ou regionais.
* **Usuários do ISP satélite**: identificar a localização específica desses usuários é difícil, pois eles normalmente parecem se originar do local do uplink.
* **IPs militares ou governamentais**: representa as pessoas que viajam ao redor do mundo e entram pelo local onde moram, em vez da base ou escritório onde trabalham.
