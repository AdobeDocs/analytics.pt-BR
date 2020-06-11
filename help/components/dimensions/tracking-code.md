---
title: Código de rastreamento
description: O nome do código de rastreamento ou da campanha.
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 3%

---


# Código de rastreamento

A dimensão &#39;Código de rastreamento&#39; lista os nomes dos códigos de rastreamento no site. Normalmente, essa dimensão é coletada usando parâmetros de string de query. Você pode colocar links com diferentes valores de parâmetro de string de query em diferentes lugares na Internet. Esta dimensão relata quais links foram os mais bem-sucedidos ao direcionar o tráfego para o site.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da string [`v0` do](/help/implement/validate/query-parameters.md) query em solicitações de imagem. O AppMeasurement coleta esses dados usando a [`campaign`](/help/implement/vars/page-vars/campaign.md) variável.

## Valores de dimensão

Os valores de dimensão incluem os nomes dos códigos de rastreamento no site. Sua organização determina quais valores de dimensão específicos você deseja usar.
