---
description: A Detecção de pesquisa paga diferencia pesquisas pagas daquelas naturais nos Mecanismos de pesquisa e nos relatórios de Palavras-chave de pesquisa.
title: Detecção de pesquisa paga
feature: Admin Tools
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Detecção de pesquisa paga

A [!UICONTROL Detecção de pesquisa paga] diferencia pesquisas pagas daquelas naturais nos [!UICONTROL Mecanismos de pesquisa] e nos relatórios de [!UICONTROL Palavras-chave de pesquisa]. É possível especificar os mecanismos de pesquisa onde você usa anúncios pagos e especificar uma sequência de caracteres encontrada no URL de uma visita a partir de um anúncio pago.

## Opções de configuração {#section_0C2CFA0AF77B47098BE37CB024665D0D}

A tabela a seguir descreve os campos e opções que são usadas para [configurar a detecção de pesquisa paga](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/t-paid-search-detection.md).

| Opção | Descrição |
| --- | --- |
| [!UICONTROL Mecanismo de pesquisa] | Selecione um mecanismo de pesquisa na lista suspensa. Você especifica o mecanismo se usar parâmetros da sequência de consulta diferentes para mecanismos de pesquisa diferentes. Normalmente, o valor `Any` é suficiente. |
| [!UICONTROL Sequência de consulta] | Especifica uma sequência para uma correspondência que diferencia maiúsculas de minúsculas com qualquer parte do parâmetro da sequência de consulta, que é a parte do url depois do “?”. <br>**Observação**: a [!UICONTROL Detecção de pesquisa paga] diferencia maiúsculas de minúsculas. Por exemplo, uma regra que especifica “PID” como um parâmetro de sequência de consulta não irá corresponder a “pid”. Se sua organização utiliza uma mistura de maiúsculas e minúsculas, coloque os valores exatos como regras separadas, para que todos os parâmetros da sequência de consulta desejados possam ser capturados. |
