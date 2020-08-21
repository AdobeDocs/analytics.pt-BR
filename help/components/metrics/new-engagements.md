---
title: Novos engajamentos
description: O número de vezes que um canal de primeiro contato é definido.
translation-type: ht
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: ht
source-wordcount: '148'
ht-degree: 100%

---


# Novos engajamentos

A métrica “Novos engajamentos” mostra o número de vezes que um visitante corresponde a um canal de marketing pela primeira vez durante o período de engajamento do visitante. Essa métrica é útil para comparar qualquer dimensão com um visitante que coincide com uma regra de processamento de canal de marketing pela primeira vez.

## Como essa métrica é calculada

Durante o processamento de dados, cada ocorrência passa pelas [Regras de processamento de canal de marketing](../c-marketing-channels/c-rules.md). Se uma ocorrência corresponder a qualquer regra de processamento de canal de marketing e o visitante ainda não tiver um canal de primeiro contato, a ocorrência será um novo engajamento. Se uma ocorrência não corresponder a nenhuma regra de processamento de canal de marketing ou se o visitante já tiver um canal de primeiro contato, a ocorrência não será um novo engajamento.

Os visitantes podem ter mais que um novo engajamento se deixarem o período de engajamento do visitante expirar.