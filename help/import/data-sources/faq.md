---
title: Perguntas frequentes sobre fontes de dados
description: Perguntas frequentes sobre fontes de dados.
exl-id: a948dfe9-289f-43e2-a9e7-7990cf609f5c
feature: Data Sources
role: Admin
TQID: 'https://experienceleague.adobe.com/RS75oqFMxi3GsiNkcqTUKAVEvlHVo9bLiR2Nt-cVU74'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: f46a60da-b0b2-4ca3-bd91-271173f4123d
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 430
ht-degree: 9%

---

# Perguntas frequentes sobre fontes de dados

Perguntas frequentes sobre fontes de dados.

+++Qual é o custo de uso das fontes de dados?
As fontes de dados não incorrem em encargos nem são contabilizadas para o uso de chamadas do servidor. [As fontes de dados de processamento completo](full-processing-eol.md) contaram para chamadas de servidor antes de serem desativadas.
+++

+++Como as fontes de dados afetam a atribuição e a expiração das eVars?
As fontes de dados não têm nenhum tipo de atribuição ou expiração.
+++

+++Como as fontes de dados afetam as métricas como exibições de página, visitas ou visitantes únicos?
Os dados carregados pelas fontes de dados não afetam de forma alguma as [Exibições de página](/help/components/metrics/page-views.md), [Visitas](/help/components/metrics/visits.md) ou [Visitantes únicos](/help/components/metrics/unique-visitors.md). A única métrica padrão afetada inclui [Ocorrências](/help/components/metrics/occurrences.md).
+++

+++Os dados carregados por meio de fontes de dados passam por processamento adicional, como regras de processamento?
Não. Dados carregados por meio de fontes de dados:

* Não passa pelas [Regras de processamento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)
* Não passa pelas [Regras de processamento de canal de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)
* Não passa pelas [regras VISTA](/help/technotes/vista.md)
+++

+++Posso excluir dados que foram importados com fontes de dados?
Sim. Você pode excluir estes dados usando a [API de Reparo de Dados](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/). A Adobe recomenda que o upload de dados de fontes de dados seja feito em um conjunto de relatórios de teste, antes de ser feito em um conjunto de relatórios de produção, para reduzir a necessidade de remover os dados.
+++

+++Quantos dados posso importar de uma vez?
O processamento é interrompido se o tamanho exceder 50 MB, e não reinicia até que o total seja inferior a 50 MB. Verifique se o tamanho total de todos os arquivos no site FTP é inferior a 50 MB.
+++

+++O que acontece se eu passar valores negativos por meio das fontes de dados?
O valor é diminuído de forma correspondente. Algumas organizações usam valores de fonte de dados negativos para tentar corrigir dados. Valores de fonte de dados negativos podem afetar os relatórios de maneiras potencialmente indesejadas ou inesperadas. A Adobe recomenda usar valores negativos em fontes de dados somente como último recurso.
+++

+++As extensões de arquivo fazem distinção entre maiúsculas e minúsculas?
Sim. Arquivos com uma extensão de `.TXT` ou `.FIN` não são processados. Verifique se todas as extensões de arquivo estão em minúsculas.
+++

+++Quantas colunas posso adicionar a um arquivo de fonte de dados?
Você poderá incluir quantas colunas desejar em um arquivo de fonte de dados, se todas forem colunas válidas. Consulte [Formato de arquivo](file-format.md) para obter uma lista de nomes de variáveis/colunas válidos.
+++

+++Posso usar fontes de dados sem usar o local FTP fornecido pela Adobe?
Você pode usar a [API das fontes de dados](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), que permite enviar chamadas de API diretamente para a Adobe. Essas chamadas de API incluem um método `UploadData`, que permite enviar dados por uma carga de objeto JSON.
+++
