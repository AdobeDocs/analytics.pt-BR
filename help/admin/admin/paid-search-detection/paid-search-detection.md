---
description: A Detecção de pesquisa paga diferencia pesquisas pagas das naturais nos Mecanismos de pesquisa e nos relatórios de Palavras-chave de pesquisa. É possível especificar os mecanismos de pesquisa onde você usa anúncios pagos e especifica uma sequência de caracteres encontrada no URL de uma visita de um anúncio pago.
title: Detecção de pesquisa paga
feature: Ferramentas administrativas
uuid: 41aadf17-7b8b-49ce-84ca-dc3293660205
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 100%

---

# Detecção de pesquisa paga

A Detecção de pesquisa paga diferencia pesquisas pagas das naturais nos Mecanismos de pesquisa e nos relatórios de Palavras-chave de pesquisa. É possível especificar os mecanismos de pesquisa onde você usa anúncios pagos e especifica uma sequência de caracteres encontrada no URL de uma visita de um anúncio pago.

## Detecção de pesquisa paga - Descrições {#section_0C2CFA0AF77B47098BE37CB024665D0D}

A tabela a seguir descreve os campos e opções que usadas para [configurar a detecção de pesquisa paga](/help/admin/admin/paid-search-detection/t-paid-search-detection.md).

| Elementos | Descrição |
|--- |--- |
| Mecanismo de pesquisa | Selecione um mecanismo de pesquisa na lista suspensa. Você especifica o mecanismo se usar parâmetros da sequência de consulta diferentes para mecanismos de pesquisa diferentes. Normalmente, o valor Qualquer é suficiente. |
| Sequência de consulta | Especifica uma regra que diferencia maiúsculas e minúsculas para conter ou não um valor específico. Esse valor deve ser o parâmetro da sequência de consulta, omitindo o &quot;?&quot;. <br>**Observação:** a detecção de pesquisa paga diferencia maiúsculas de minúsculas. Por exemplo, uma regra que especifica o PID como um parâmetro de cadeia de caracteres de consulta não exibe o pid no relatório. Se sua organização utiliza uma mistura de maiúsculas e minúsculas, coloque os valores exatos como regras separadas, para que todos os parâmetros da sequência de consulta desejados possam ser capturados.</br> |
