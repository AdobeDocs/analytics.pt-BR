---
title: Países
description: O país de onde a ocorrência se originou.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 96%

---


# Países

A dimensão &quot;Países&quot; informa o país de onde a ocorrência se originou. Essa dimensão é útil para ajudar a determinar a origem dos visitantes dos países mais populares ao visitar seu site. Você pode usar esses dados para se concentrar nos esforços de marketing nesses países ou para garantir que a experiência do seu site seja ideal nos países com idiomas principais diferentes.

## Preencher esta dimensão com dados

Essa dimensão faz referência às regras de pesquisa internas da Adobe. O valor de pesquisa se baseia no endereço IP enviado com a ocorrência. A Adobe faz parceria com a [Digital Element](https://www.digitalelement.com/?lang=pt-pt) para manter pesquisas entre o endereço IP e o país. Essa dimensão funciona imediatamente em todas as implementações.

>[!TIP]
>
>Se a sua organização seguir normas rigorosas de privacidade em que [ofuscar endereços IP](/help/admin/admin/general-acct-settings-admin.md) não for suficiente, você poderá solicitar a desativação total dos dados de geolocalização. Entre em contato com o Atendimento ao cliente com a ID do conjunto de relatórios e solicite a desativação de &quot;Geografia&quot; para o conjunto de relatórios.

## itens de Dimension

Itens de Dimension incluem países em todo o mundo. Os valores de exemplo incluem `"United States"`, `"United Kingdom"` ou `"India"`.

## Diferenças entre a localização informada e a real

Como essa dimensão se baseia no endereço IP, alguns cenários podem mostrar uma diferença entre a localização informada e a localização real:

* **Endereços IP que representam proxies corporativos**: esses visitantes podem aparecer como tráfego vindo da rede corporativa do usuário, que pode ser um local diferente se o usuário estiver trabalhando remotamente.
* **Endereços de IP remoto**: o direcionamento por IP móvel funciona em diferentes níveis, dependendo da localização e da rede. Um número de operadoras faz o backhaul do tráfego IP através de pontos de presença centralizados ou regionais.
* **Usuários do ISP satélite**: identificar a localização específica desses usuários é difícil, pois eles normalmente parecem se originar do local do uplink.
* **IPs militares ou governamentais**: representa as pessoas que viajam ao redor do mundo e entram pelo local onde moram, em vez da base ou escritório onde trabalham.
