---
title: Perguntas frequentes sobre fontes de dados
description: Perguntas frequentes sobre fontes de dados.
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 7%

---

# Perguntas frequentes sobre fontes de dados

Perguntas frequentes sobre fontes de dados.

+++Qual é o custo para usar fontes de dados?
As fontes de dados não incorrem em encargos nem contam para o uso de chamadas do servidor. [Fontes de dados de processamento completo](full-processing-eol.md) contado para chamadas de servidor antes de sua desativação.
+++

+++Como as fontes de dados afetam a atribuição e a expiração de eVars?
Se uma transactionID corresponder entre uma fonte de dados e uma ocorrência online, os valores de eVar associados assumirão a mesma atribuição e expiração como se tivessem sido definidos na ocorrência online.

Todos os outros dados carregados por meio de fontes de dados não têm nenhum tipo de atribuição ou expiração.
+++

+++Como as fontes de dados afetam as métricas padrão, como exibições de página, visitas ou visitantes únicos?
Os dados carregados por meio das fontes de dados não afetam [Exibições de página](/help/components/metrics/page-views.md), [Visitas](/help/components/metrics/visits.md)ou [Visitantes únicos](/help/components/metrics/unique-visitors.md) de qualquer maneira. A única métrica padrão que afeta inclui [Ocorrências](/help/components/metrics/occurrences.md).
+++

+++É possível excluir dados que foram importados usando fontes de dados?

**Não.** Os dados carregados em relatórios usando fontes de dados são **permanente**. Não pode ser removido, nem mesmo por Adobe, depois de ter sido importado. O Adobe recomenda fazer upload dos dados das fontes de dados em um conjunto de relatórios de teste antes de fazer upload para um conjunto de relatórios de produção.
+++

+++Quantos dados posso importar de uma vez?

O processamento é interrompido se o tamanho exceder 50 MB, e não reinicia até que o total seja inferior a 50 MB. Certifique-se de que o tamanho total de todos os arquivos no site FTP seja menor que 50 MB.
+++

+++O que acontece se eu passar valores negativos por meio de fontes de dados?

O valor é diminuído de forma correspondente. Algumas organizações usam valores de fonte de dados negativos para tentar corrigir os dados. Valores de fonte de dados negativos podem afetar relatórios de maneiras potencialmente indesejadas ou inesperadas. O Adobe recomenda usar fontes de dados negativas somente como último recurso.
+++

+++As extensões de arquivo fazem distinção entre maiúsculas e minúsculas?
Sim. Arquivos com extensão de `.TXT` ou `.FIN` não são processados. Certifique-se de que as extensões de arquivo estejam todas em minúsculas.
+++

+++Quantas colunas posso adicionar a um arquivo de fonte de dados?
Você pode incluir quantas colunas quiser em um arquivo de fonte de dados, se todas forem colunas válidas. Consulte [Formato de arquivo](file-format.md) para obter uma lista de nomes de variáveis/colunas válidos.
+++

+++Posso usar as fontes de dados sem usar o local de FTP fornecido pelo Adobe?
Você pode usar o [API de fontes de dados](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), que permite enviar chamadas de API diretamente para o Adobe. Essas chamadas de API incluem um `UploadData` , que permite enviar dados por uma carga de objeto JSON.
+++
