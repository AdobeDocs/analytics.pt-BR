---
title: Servidor
description: O nome do servidor.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 1%

---


# Servidor

A dimensão &#39;Servidor&#39; normalmente lista o nome do host do site. Para conjuntos de relatórios que combinam vários domínios ou subdomínios, essa dimensão é importante para ver quais domínios ou subdomínios executam melhor.

Essa dimensão está relacionada às dimensões da seção [Página](page.md) e [Site](site-section.md) . A página é mais granular, o Servidor é menos granular e a seção Site fica entre os dois.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da string [`server` do](/help/implement/validate/query-parameters.md) query em solicitações de imagem. O AppMeasurement coleta esses dados usando a [`server`](/help/implement/vars/page-vars/server.md) variável.

## Itens de dimensão

Os itens de dimensão incluem servidores em seu site. Sua organização determina quais itens de dimensão você deseja usar. Algumas organizações usam `window.location.hostname`, enquanto outras formulam valores personalizados. Qualquer que seja o método usado, verifique se ele é consistente e se você o registra em um documento [de design de](/help/implement/prepare/solution-design.md)solução.
