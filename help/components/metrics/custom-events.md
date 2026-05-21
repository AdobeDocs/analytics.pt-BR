---
title: Eventos personalizados
description: O número de ocorrências em que um evento personalizado existe.
feature: Metrics
exl-id: 9ae3ff53-8634-466a-a9f6-786c1e62c2fa
TQID: https://experienceleague.adobe.com/1D8ONiUuG3T6DqM7HygbBbf0Y4ja5ej1Hfy8-hKo0yg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 223
ht-degree: 91%

---

# Eventos personalizados

*Esta página de ajuda descreve como os eventos personalizados funcionam como uma métrica. Para obter informações sobre como os eventos personalizados funcionam como uma variável de implementação, consulte a [Visão geral dos eventos](/help/implement/vars/page-vars/events/events-overview.md) no guia de usuário Implementar.*

[métricas](overview.md) do evento personalizado mostra o número de ocorrências em que determinado evento personalizado foi definido em uma solicitação de imagem. Essas métricas são vitais para muitas implementações, pois fornecem insight de eventos que são específicos de cada organização.

## Como essa métrica é calculada

Os eventos personalizados são calculados de forma diferente dependendo de seu tipo. Você pode verificar o tipo de evento em [Eventos bem-sucedidos](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md) nas configurações do conjunto de relatórios.

* **Eventos contadores**: a configuração padrão do evento. A maioria dos eventos são eventos contadores. Conta o número de ocorrências nas quais o evento personalizado correspondente `event1` - `event1000` existe na variável [`events`](/help/implement/vars/page-vars/events/events-overview.md).
* **Eventos numéricos**: soma o valor numérico atribuído ao evento na variável `events`.
* **Eventos de moeda**: aplica a conversão de moeda em relação à taxa de câmbio do dia e soma o valor numérico atribuído a cada ocorrência na variável `events`.

O número de eventos disponíveis depende do contrato do Analytics de sua organização. A maioria das organizações com contratos não herdados tem 1000 eventos personalizados disponíveis. Entre em contato com a Equipe de contas da Adobe se não tiver certeza de quantos eventos personalizados estão disponíveis para você.

A Adobe recomenda que você registre como utiliza cada evento no [documento de design de soluções](/help/implement/prepare/solution-design.md) da sua organização.
