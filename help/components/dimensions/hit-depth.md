---
title: Profundidade da ocorrência
description: O número de hits na visita.
feature: Dimensions
exl-id: 84c27e3f-4228-4455-95bf-0239928337b5
TQID: https://experienceleague.adobe.com/dH1ItdXZTw9vcqvej3VOQDM-J9FFA38f4bq8HTJbKMo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 63%
---
# Profundidade do hit

A [dimensão](overview.md) de &quot;Profundidade da ocorrência&quot; relata a distância que uma determinada ocorrência está de uma visita. Essa dimensão é importante para entender até que ponto os visitantes fazem ações em seu site. A profundidade da ocorrência conta todos os tipos de ocorrências, incluindo visualizações de página ([`t()`](/help/implement/vars/functions/t-method.md)) e ocorrências de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Preencher esta dimensão com dados

O Adobe calcula essa dimensão no lado do servidor a partir da sequência de ocorrências em cada visita. Não há variável a ser definida; isso funciona imediatamente em todas as implementações.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (calculado pela Adobe) |
| **Web SDK / campo XDM** | Nenhum (calculado pela Adobe) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | N/D |

## Itens de dimensão

Os itens de dimensão incluem a string `"Hit Depth"` seguida por um número que representa o número de hits na visita. O item de dimensão `"Hit Depth 1"` representa o primeiro hit da visita, enquanto o item de dimensão `"Hit Depth 8"` representa o 8º hit da visita.

>[!NOTE]
>
>O Adobe Analytics registra carimbos de data e hora somente com precisão de segundo nível. Para ocorrências que compartilham o mesmo carimbo de data e hora em segundo lugar, o Adobe não pode garantir que a ordem refletida no relatório seja a mesma que a ordem em que as ocorrências ocorreram. Se a precisão de nível de milissegundo for uma prioridade para sua organização, considere usar o Customer Journey Analytics.

## Comparação com a profundidade da visita

A profundidade do hit conta todos os tipos de hits, incluindo visualização de página e hits de rastreamento de link. A profundidade da visita somente aumenta para hits de visualização de página, _e_ o item de dimensão [Página](page.md) não é o mesmo que o valor na página anterior. A profundidade da visita também é uma dimensão que se baseia nas visitas, o que significa que é o mesmo valor para todos os hits na visita. A tabela a seguir descreve um exemplo de visita e como ela considera a profundidade do hit + profundidade da visita:

| Sequência de páginas | Profundidade do hit | Conta para a profundidade da visita? | Profundidade da visita |
| --- | --- | --- | --- |
| Página inicial | 1 | Sim | 4 |
| Página do produto | 2 | Sim | 4 |
| Página inicial | 3 | Sim | 4 |
| Clique no link personalizado | 4 | Não (link personalizado) | 4 |
| Clique no link personalizado | 5 | Não (link personalizado) | 4 |
| Página do produto | 6 | Sim | 4 |
| Clique no link personalizado | 7 | Não (link personalizado) | 4 |
| Página do produto | 8 | Não (igual à página anterior) | 4 |
