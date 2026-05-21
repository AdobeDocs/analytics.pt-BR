---
description: Descreve como definir códigos monetários de destino para que o suporte a várias moedas funcione.
title: Suporte a várias moedas
feature: Analytics Basics
exl-id: b67f459c-0636-4eac-af52-51846bb583b5
TQID: https://experienceleague.adobe.com/-t0JAIvbmUmzTCTznOWcjVmvtJbmQNV5MIrbQBvhv6M
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 127
ht-degree: 18%

---

# Suporte a várias moedas

A Adobe oferece vários níveis de conversão de moeda para que sua organização possa alcançar a moeda desejada em muitos relatórios. Ocorre uma conversão em três níveis:

## Nível da página

Você pode usar a variável [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) para definir a moeda desejada em cada página. Se a moeda na página não corresponder à moeda do conjunto de relatórios de destino, o Adobe executará uma conversão de moeda para a moeda do conjunto de relatórios com base na taxa de câmbio do dia. A moeda convertida é registrada.

## Nível do conjunto de relatórios

Todo conjunto de relatórios tem uma **moeda base**. Esta moeda determina o contexto de todas as métricas de moeda (como [Receita](/help/components/metrics/revenue.md)). Todos os dados de moeda armazenados estão na moeda base do conjunto de relatórios.

