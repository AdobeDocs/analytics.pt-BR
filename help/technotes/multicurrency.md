---
description: Descreve como definir códigos monetários de destino para que o suporte a várias moedas funcione.
title: Suporte a várias moedas
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
source-git-commit: 99156dd9d898ce0abf214561cb0040c647d7e6ab
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 16%

---

# Suporte a várias moedas

O Adobe oferece vários níveis de conversão de moeda para que sua organização possa alcançar a moeda desejada em muitos relatórios. Ocorre uma conversão em três níveis:

## Nível da página

Você pode usar o [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) para definir a moeda desejada em cada página. Se a moeda na página não corresponder à moeda do conjunto de relatórios de destino, o Adobe executará uma conversão de moeda para a moeda do conjunto de relatórios com base na taxa de câmbio do dia. A moeda convertida é registrada.

## Nível do conjunto de relatórios

Todo conjunto de relatórios tem um **moeda de base**. Essa moeda determina o contexto de todas as métricas de moeda (como [Receita](/help/components/metrics/revenue.md)). Todos os dados de moeda armazenados estão na moeda base do conjunto de relatórios.

