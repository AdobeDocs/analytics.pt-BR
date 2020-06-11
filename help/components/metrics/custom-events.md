---
title: Eventos personalizados
description: O número de ocorrências em que um evento personalizado existe.
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 19%

---


# Eventos personalizados

*Esta página de ajuda descreve como os eventos personalizados funcionam como uma métrica. Para obter informações sobre como os eventos personalizados funcionam como uma variável de implementação, consulte a visão geral[dos](/help/implement/vars/page-vars/events/events-overview.md)Eventos no guia Implementar usuário.*

Métricas de evento personalizadas mostram o número de ocorrências em que determinado evento personalizado foi definido em uma solicitação de imagem. Essas métricas são vitais para muitas implementações, pois fornecem informações sobre eventos específicos de cada organização.

## Como essa métrica é calculada

Os eventos personalizados são calculados de forma diferente dependendo de seu tipo. Você pode verificar um tipo de evento em eventos [](../../admin/admin/c-success-events/success-event.md) bem-sucedidos nas configurações do conjunto de relatórios.

* **eventos** contadores: A configuração padrão do evento. A maioria dos eventos são eventos contadores. Conta o número de ocorrências nas quais o evento personalizado correspondente `event1` - `event1000` existe na [`events`](/help/implement/vars/page-vars/events/events-overview.md) variável.
* **eventos** numéricos: Soma o valor numérico atribuído ao evento na `events` variável.
* **eventos** de moeda: Aplica a conversão de moeda em relação à taxa de câmbio do dia e soma o valor numérico atribuído a cada ocorrência na `events` variável.

O número de eventos disponíveis depende do contrato do Analytics de sua organização. A maioria das organizações com contratos não herdados tem 1000 eventos personalizados disponíveis. Entre em contato com o gerente de conta de sua organização se não tiver certeza de quantos eventos personalizados estão disponíveis para você.

A Adobe recomenda gravar como você usa cada evento no documento [de design de](/help/implement/prepare/solution-design.md)solução da sua organização.
