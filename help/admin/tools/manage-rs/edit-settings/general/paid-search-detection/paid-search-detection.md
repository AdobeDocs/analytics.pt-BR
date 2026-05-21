---
description: A Detecção de pesquisa paga diferencia pesquisas pagas daquelas naturais nos Mecanismos de pesquisa e nos relatórios de Palavras-chave de pesquisa.
title: Detecção de pesquisa paga
feature: Admin Tools
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
TQID: https://experienceleague.adobe.com/g26-86nQZ-k3kaID-Dq6qbwYkdqLpHDdUEswP-p361Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 87%

---

# Detecção de pesquisa paga

A [!UICONTROL Detecção de pesquisa paga] diferencia pesquisas pagas daquelas naturais nos [!UICONTROL Mecanismos de pesquisa] e nos relatórios de [!UICONTROL Palavras-chave de pesquisa]. É possível especificar os mecanismos de pesquisa onde você usa anúncios pagos e especificar uma sequência de caracteres encontrada no URL de uma visita a partir de um anúncio pago.

## Opções de configuração {#configuration}

A tabela a seguir descreve os campos e opções que são usadas para [configurar a detecção de pesquisa paga](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/t-paid-search-detection.md).

| Opção | Descrição |
| --- | --- |
| [!UICONTROL Mecanismo de pesquisa] | Selecione um mecanismo de pesquisa na lista suspensa. Você especifica o mecanismo se usar diferentes parâmetros de string de consulta para diferentes mecanismos de pesquisa. Normalmente, o valor `Any` é suficiente. |
| [!UICONTROL Sequência de consulta] | Especifica uma sequência para uma correspondência que diferencia maiúsculas de minúsculas com qualquer parte do parâmetro da sequência de consulta, que é a parte do url depois do “?”. <br>**Observação**: a [!UICONTROL Detecção de pesquisa paga] diferencia maiúsculas de minúsculas. Por exemplo, uma regra que especifica “PID” como um parâmetro de sequência de consulta não irá corresponder a “pid”. Se sua organização utiliza uma mistura de maiúsculas e minúsculas, coloque os valores exatos como regras separadas, para que todos os parâmetros da sequência de consulta desejados possam ser capturados. |
