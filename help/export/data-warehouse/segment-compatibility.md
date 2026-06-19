---
title: Compatibilidade de segmentos do Data warehouse
description: Saiba quais definições de segmento são válidas para uso no Data Warehouse.
feature: Data Warehouse
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
TQID: https://experienceleague.adobe.com/7CrArNYD-8ZXVpfO86d1l42ySkTuv8V04PWJFeNWx3s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 456
ht-degree: 9%

---

# Compatibilidade de segmentos do Data warehouse

Nem todos os segmentos criados no construtor de segmentos podem ser usados no Data Warehouse. Use esta página para saber quais definições de segmento são compatíveis com o Data Warehouse, de modo que ele esteja disponível para seleção quando você [criar uma solicitação do Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Um segmento é compatível com o Data Warehouse somente quando **ambos** dos itens a seguir são verdadeiros:

* **Componentes com suporte**: o segmento usa apenas dimensões e métricas compatíveis com o Data Warehouse.
* **Estrutura com suporte**: a estrutura do segmento segue as regras impostas pela Data Warehouse.

Se uma das condições não for atendida, o segmento não aparecerá como uma opção ao criar uma solicitação do Data Warehouse e um erro será exibido se você selecionar um conjunto de relatórios virtual que contenha um segmento incompatível.

## Componentes compatíveis

Como um segmento é avaliado em relação aos mesmos dados que a solicitação à qual é aplicado, **qualquer componente que não tenha suporte em uma solicitação Data Warehouse também não tem suporte em um segmento.** Para obter a lista completa de dimensões e métricas para as quais o Data Warehouse não oferece suporte, consulte [Suporte a componentes no Data Warehouse](component-support.md).

Além da dimensão e das métricas listadas no [Suporte a componentes](component-support.md), as seguintes dimensões estão disponíveis em uma *solicitação* do Data Warehouse, mas **não podem ser usadas dentro de uma definição de segmento**:

* [[!UICONTROL Dia do mês]](/help/components/dimensions/day-of-month.md)
* [[!UICONTROL Dia da semana]](/help/components/dimensions/day-of-week.md)
* [[!UICONTROL Dia do ano]](/help/components/dimensions/day-of-year.md)
* [[!UICONTROL Hora do dia]](/help/components/dimensions/hour-of-day.md)
* [[!UICONTROL Canais de marketing]](/help/components/dimensions/marketing-channel.md) (use o [[!UICONTROL Canal de último contato]](/help/components/dimensions/last-touch-channel.md))
* [[!UICONTROL Mês do ano]](/help/components/dimensions/month-of-year.md)
* [[!UICONTROL Páginas não encontradas]](/help/components/dimensions/pages-not-found.md) (use o [[!UICONTROL erro de tipo de página]](/help/components/dimensions/pages-not-found.md))
* [[!UICONTROL Trimestre do ano]](/help/components/dimensions/quarter-of-year.md)
* [[!UICONTROL Dia da semana/Fim de semana]](/help/components/dimensions/weekday-weekend.md)

## Estrutura compatível

Mesmo quando um segmento usa apenas componentes compatíveis, sua estrutura deve seguir as regras impostas pelo Data Warehouse. As estruturas de segmento são totalmente compatíveis, parcialmente compatíveis ou não:

**Com Suporte**:

* **Empilhamento de segmentos**: vários segmentos podem ser aplicados a uma única solicitação do Data Warehouse.
* **Contêineres aninhados**: com suporte, o escopo fornecido diminui em cada nível (visitante → visita → ocorrência). Não há suporte para contêineres que aumentam no escopo.

**Parcialmente suportado**:

* **Excluir contêineres**: suportado somente no nível superior. O Data Warehouse dá suporte somente a segmentos que podem ser expressos como `A AND NOT B` — ou seja, **incluir esta característica** e **excluir esta característica**. Não há suporte para contêineres de exclusão aninhados em outros contêineres.
* **Lógica AND/OR**: compatível com limitações. Ao usar um contêiner `exclusion` ou `without` em combinação com a lógica E/OU, somente os segmentos que podem ser regravados como `A AND NOT B` são suportados.

**Sem suporte**:

* **Segmentos sequenciais**: não há suporte para segmentos que usam o operador THEN para definir sequências ordenadas de navegação de visitantes.
* **operadores &quot;Igual a qualquer um de&quot; e &quot;Não é igual a nenhum&quot;**: esses operadores não têm suporte em segmentos do Data Warehouse.

## Segmentos usados como dimensões

Quando você usa um segmento como uma dimensão em um relatório do Data Warehouse, o relatório retorna uma coluna contendo `"0"` ou `"1"`:

* **`"0"`**: o item de dimensão não atendeu aos critérios do segmento.
* **`"1"`**: o item de dimensão atendeu aos critérios do segmento.
