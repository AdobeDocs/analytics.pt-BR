---
title: Servidor
description: O nome do servidor.
exl-id: c2454c0d-497e-46f8-8569-7d0517097cab
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '136'
ht-degree: 100%

---

# Servidor

A dimensão “Servidor&#39;” normalmente lista o hostname do site. Para conjuntos de relatórios que combinam vários domínios ou subdomínios, essa dimensão é útil para analisar quais domínios ou subdomínios têm o melhor desempenho.

Essa dimensão está relacionada às dimensões [Página](page.md) e [Seções do site](site-section.md). A dimensão Página é mais granular, a dimensão Servidor é menos granular e a dimensão Seção do site fica entre as duas.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da [`server` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável [`server`](/help/implement/vars/page-vars/server.md).

## Itens de dimensão

Os itens de dimensão incluem servidores no site. A organização escolhe quais itens de dimensão específicos quer utilizar. Algumas organizações utilizam `window.location.hostname`, enquanto outras formulam valores personalizados. Independentemente do método usado, verifique se ele é consistente e registre-o em um [documento de design de solução](/help/implement/prepare/solution-design.md).
