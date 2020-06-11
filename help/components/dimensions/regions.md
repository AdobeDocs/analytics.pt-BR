---
title: Regiões
description: A região geográfica do visitante.
translation-type: tm+mt
source-git-commit: 52e00470df0f0c6bff84b26c1548e64ff5114fb8
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 7%

---


# Regiões

A dimensão &#39;Regiões&#39; relata a região geográfica do visitante. É uma área geográfica menor que um país, mas maior que uma cidade. Em alguns países, uma região é um estado, ou município. Em outras áreas, é um país constituinte, departamento ou região metropolitana. O uso dessa dimensão é valioso se você quiser informações mais granulares que [Países](countries.md) , mas não tão granulares quanto [Cidades](cities.md).

## Preencher esta dimensão com dados

Essa dimensão faz referência às regras de pesquisa internas da Adobe. O valor de pesquisa se baseia no endereço IP enviado com a ocorrência. A Adobe faz parceria com o [Digital Element](https://www.digitalelement.com/) para manter pesquisas entre o endereço IP e o país. Essa dimensão funciona imediatamente em todas as implementações.

> [!TIP] Se a sua organização seguir normas rigorosas de privacidade onde [ofuscar endereços](/help/admin/admin/general-acct-settings-admin.md) IP não for suficiente, você poderá solicitar a desativação total dos dados de geolocalização. Entre em contato com o Atendimento ao cliente com a ID do conjunto de relatórios e solicite a desativação de &quot;Geografia&quot; para o conjunto de relatórios.

## Valores de dimensão

Os valores de dimensão incluem regiões e o país em que a região reside. Os valores de exemplo incluem `"California (United States)"`, `"Tokyo (Japan)"`ou `"Sao Paulo (Brazil)"`.

## Diferenças entre a localização reportada e a real

Como essa dimensão se baseia no endereço IP, alguns cenários podem mostrar uma diferença entre a localização relatada e a localização real:

* **Endereços IP que representam proxies** corporativos: Esses visitantes podem aparecer como tráfego vindo pela rede corporativa do usuário, que pode ser um local diferente se o usuário estiver trabalhando remotamente.
* **Endereços** IP móveis: A definição de metas de IP móvel funciona em níveis variados, dependendo da localização e da rede. Um número de operadoras faz a conexão retroativa do tráfego de IP por meio de pontos de presença centralizados ou regionais.
* **Usuários** do ISP satélite: Identificar a localização específica desses usuários é difícil, pois eles normalmente parecem ser originários da localização do uplink.
* **IPs** militares e governamentais: Representa o pessoal que viaja pelo globo e entra pelo local de sua casa, em vez da base ou do escritório onde está estacionado no momento.
