---
title: Novos envolvimentos
description: O número de vezes que um canal de primeiro toque é definido.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---


# Novos envolvimentos

A métrica &#39;Novos envolvimentos&#39; mostra o número de vezes que um visitante corresponde a um canal de marketing pela primeira vez no período de envolvimento do visitante. Essa métrica é útil quando você deseja comparar qualquer dimensão com um visitante que corresponda a uma regra de processamento de canal de marketing pela primeira vez.

## Como essa métrica é calculada

Durante o processamento de dados, cada ocorrência é executada por meio das regras [de processamento do](../c-marketing-channels/c-rules.md)canal de marketing. Se uma ocorrência corresponder a qualquer regra de processamento de canais de marketing e o visitante ainda não tiver um canal de primeiro toque, a ocorrência será um novo envolvimento. Se uma ocorrência não corresponder a nenhuma regra de processamento de canais de marketing ou se o visitante já tiver um canal de primeiro toque, a ocorrência não será um envolvimento novo.

Os Visitantes podem ter mais de um novo envolvimento se deixarem seu período de envolvimento do visitante expirar.