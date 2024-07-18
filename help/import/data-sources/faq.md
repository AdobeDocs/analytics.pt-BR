---
title: Perguntas frequentes sobre fontes de dados
description: Perguntas frequentes sobre fontes de dados.
exl-id: a948dfe9-289f-43e2-a9e7-7990cf609f5c
feature: Data Sources
role: Admin
source-git-commit: f7d07525c97f4aa145dc46198f883a37cde80158
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 5%

---

# Perguntas frequentes sobre fontes de dados

Perguntas frequentes sobre fontes de dados.

+++Qual é o custo de usar fontes de dados?
As fontes de dados não incorrem em encargos nem são contabilizadas para o uso de chamadas do servidor. [As fontes de dados de processamento completo](full-processing-eol.md) contaram para chamadas de servidor antes de serem desativadas.
+++

+++Como as fontes de dados afetam a atribuição e a expiração das eVars?
Se uma transactionID corresponder entre uma fonte de dados e uma ocorrência online, os valores de eVar associados assumirão a mesma atribuição e expiração como se tivessem sido definidos na ocorrência online.

Todos os outros dados carregados por meio de fontes de dados não têm nenhum tipo de atribuição ou expiração.
+++

+++Como as fontes de dados afetam as métricas padrão, como exibições de página, visitas ou visitantes únicos?
Os dados carregados pelas fontes de dados não afetam de forma alguma as [Exibições de página](/help/components/metrics/page-views.md), [Visitas](/help/components/metrics/visits.md) ou [Visitantes únicos](/help/components/metrics/unique-visitors.md). A única métrica padrão afetada inclui [Ocorrências](/help/components/metrics/occurrences.md).
+++

+++É possível excluir dados que foram importados com fontes de dados?

Sim. Você pode excluir estes dados usando a [API de Reparo de Dados](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/). Além disso, a Adobe recomenda que o upload de dados das fontes de dados seja feito em um conjunto de relatórios de teste, antes de fazer upload em um conjunto de relatórios de produção.
+++

+++Quantos dados posso importar de uma vez?

O processamento é interrompido se o tamanho exceder 50 MB, e não reinicia até que o total seja inferior a 50 MB. Verifique se o tamanho total de todos os arquivos no site FTP é inferior a 50 MB.
+++

+++O que acontece se eu passar valores negativos por meio de fontes de dados?

O valor é diminuído de forma correspondente. Algumas organizações usam valores de fonte de dados negativos para tentar corrigir dados. Valores de fonte de dados negativos podem afetar os relatórios de maneiras potencialmente indesejadas ou inesperadas. A Adobe recomenda usar fontes de dados negativas somente como último recurso.
+++

+++As extensões de arquivo fazem distinção entre maiúsculas e minúsculas?
Sim. Arquivos com uma extensão de `.TXT` ou `.FIN` não são processados. Verifique se todas as extensões de arquivo estão em minúsculas.
+++

+++Quantas colunas posso adicionar a um arquivo de fonte de dados?
Você poderá incluir quantas colunas desejar em um arquivo de fonte de dados, se todas forem colunas válidas. Consulte [Formato de arquivo](file-format.md) para obter uma lista de nomes de variáveis/colunas válidos.
+++

+++É possível usar fontes de dados sem usar o local FTP fornecido pelo Adobe?
Você pode usar a [API de fontes de dados](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), que permite enviar chamadas de API diretamente para o Adobe. Essas chamadas de API incluem um método `UploadData`, que permite enviar dados por uma carga de objeto JSON.
+++
