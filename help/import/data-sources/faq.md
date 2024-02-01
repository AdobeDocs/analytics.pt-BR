---
title: Perguntas frequentes sobre fontes de dados
description: Perguntas frequentes sobre fontes de dados.
exl-id: a948dfe9-289f-43e2-a9e7-7990cf609f5c
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 4%

---

# Perguntas frequentes sobre fontes de dados

Perguntas frequentes sobre fontes de dados.

+++Qual é o custo de usar fontes de dados?
As fontes de dados não incorrem em encargos nem são contabilizadas para o uso de chamadas do servidor. [Fontes de dados de processamento completo](full-processing-eol.md) contados para chamadas de servidor antes de sua aposentadoria.
+++

+++Como as fontes de dados afetam a atribuição e a expiração das eVars?
Se uma transactionID corresponder entre uma fonte de dados e uma ocorrência online, os valores de eVar associados assumirão a mesma atribuição e expiração como se tivessem sido definidos na ocorrência online.

Todos os outros dados carregados por meio de fontes de dados não têm nenhum tipo de atribuição ou expiração.
+++

+++Como as fontes de dados afetam as métricas padrão, como exibições de página, visitas ou visitantes únicos?
Os dados carregados por meio de fontes de dados não afetam o [Exibições de página](/help/components/metrics/page-views.md), [Visitas](/help/components/metrics/visits.md)ou [Visitantes únicos](/help/components/metrics/unique-visitors.md) de qualquer forma. A única métrica padrão afetada inclui [Ocorrências](/help/components/metrics/occurrences.md).
+++

+++É possível excluir dados que foram importados com fontes de dados?

**Não.** Os dados carregados em relatórios por meio de fontes de dados são **permanente**. Ele não pode ser removido, nem mesmo pelo Adobe, uma vez que foi importado. A Adobe recomenda que o upload dos dados das fontes de dados seja feito em um conjunto de relatórios de teste, antes de fazer o upload em um conjunto de relatórios de produção.
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
Você poderá incluir quantas colunas desejar em um arquivo de fonte de dados, se todas forem colunas válidas. Consulte [Formato de arquivo](file-format.md) para obter uma lista de nomes válidos de variáveis/colunas.
+++

+++É possível usar fontes de dados sem usar o local FTP fornecido pelo Adobe?
Você pode usar o [API de fontes de dados](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), que permite enviar chamadas de API diretamente para o Adobe. Essas chamadas de API incluem uma `UploadData` , que permite enviar dados por uma carga do objeto JSON.
+++
