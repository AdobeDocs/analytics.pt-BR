---
title: Eventos personalizados
description: O número de ocorrências em que um evento personalizado existe.
feature: Metrics
exl-id: 9ae3ff53-8634-466a-a9f6-786c1e62c2fa
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 83%

---

# Eventos personalizados

*Esta página de ajuda descreve como os eventos personalizados funcionam como uma métrica. Para obter informações sobre como os eventos personalizados funcionam como uma variável de implementação, consulte a [Visão geral dos eventos](/help/implement/vars/page-vars/events/events-overview.md) no guia de usuário Implementar.*

Evento personalizado [métricas](overview.md) mostrar o número de ocorrências em que determinado evento personalizado foi definido em uma solicitação de imagem. Essas métricas são vitais para muitas implementações, pois fornecem insight de eventos que são específicos de cada organização.

## Como essa métrica é calculada

Os eventos personalizados são calculados de forma diferente dependendo de seu tipo. Você pode verificar o tipo de evento em [Eventos bem-sucedidos](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) nas configurações do conjunto de relatórios.

* **Eventos contadores**: a configuração padrão do evento. A maioria dos eventos são eventos contadores. Conta o número de ocorrências nas quais o evento personalizado correspondente `event1` - `event1000` existe na variável [`events`](/help/implement/vars/page-vars/events/events-overview.md).
* **Eventos numéricos**: soma o valor numérico atribuído ao evento na variável `events`.
* **Eventos de moeda**: aplica a conversão de moeda em relação à taxa de câmbio do dia e soma o valor numérico atribuído a cada ocorrência na variável `events`.

O número de eventos disponíveis depende do contrato do Analytics de sua organização. A maioria das organizações com contratos não herdados tem 1000 eventos personalizados disponíveis. Entre em contato com a equipe de conta do Adobe se não tiver certeza de quantos eventos personalizados estão disponíveis para você.

A Adobe recomenda que você registre como utiliza cada evento no [documento de design de soluções](/help/implement/prepare/solution-design.md) da sua organização.
