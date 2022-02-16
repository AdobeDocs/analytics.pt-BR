---
description: 'A Detecção de pesquisa paga diferencia pesquisas pagas das naturais nos Mecanismos de pesquisa e nos relatórios de Palavras-chave de pesquisa. '
title: Detecção de pesquisa paga
feature: Admin Tools
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
source-git-commit: 2c0aef13bdb88b0a7aa9f100c72c21f66a14c8dd
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 71%

---

# Detecção de pesquisa paga

[!UICONTROL A Detecção de pesquisa paga diferencia pesquisas pagas das naturais nos Mecanismos de pesquisa e nos relatórios de Palavras-chave de pesquisa. ] É possível especificar os mecanismos de pesquisa onde você usa anúncios pagos e especifica uma sequência de caracteres encontrada no URL de uma visita de um anúncio pago.

## Opções de configuração {#section_0C2CFA0AF77B47098BE37CB024665D0D}

A tabela a seguir descreve os campos e opções que usadas para [configurar a detecção de pesquisa paga](/help/admin/admin/paid-search-detection/t-paid-search-detection.md).

| Opção | Descrição |
| --- | --- |
| [!UICONTROL Mecanismo de pesquisa] | Selecione um mecanismo de pesquisa na lista suspensa. Você especifica o mecanismo se usar parâmetros da sequência de consulta diferentes para mecanismos de pesquisa diferentes. Normalmente, o valor `Any` for suficiente. |
| [!UICONTROL Sequência de consulta] | Especifica uma string para uma correspondência que diferencia maiúsculas e minúsculas com qualquer parte do parâmetro da string de consulta, que é a parte do url depois do &quot;?&quot;. <br>**Observação**: [!UICONTROL Detecção de pesquisa paga] diferencia maiúsculas de minúsculas. Por exemplo, uma regra que especifica &quot;PID&quot; como um parâmetro de sequência de consulta não corresponderá a &quot;pid&quot;. Se sua organização utiliza uma mistura de maiúsculas e minúsculas, coloque os valores exatos como regras separadas, para que todos os parâmetros da sequência de consulta desejados possam ser capturados. |
