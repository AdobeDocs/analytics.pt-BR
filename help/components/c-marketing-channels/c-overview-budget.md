---
description: Saiba como atribuir valores de custo e orçamento a canais.
seo-description: Saiba como atribuir valores de custo e orçamento a canais.
seo-title: Custos e orçamentos
solution: Analytics
subtopic: Canais de marketing
title: Custos e orçamentos
topic: Reports and Analytics
uuid: 7 ba 0 e 968-e 565-4 d 4 c -8 fc 0-39 bf 25 d 3 e 5 b 1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Custos e orçamentos

Saiba como atribuir valores de custo e orçamento a canais.

## Costs and budgets {#topic_7CCFD3B54440433FBA0E4EE127F58B0C}

Saiba como atribuir valores de custo e orçamento a canais.

O custo representa o que é gasto no canal. O orçamento representa a quantia disponível destinada.

 Uma forma útil de visualizar seu ROI é criar uma métrica calculada que exibe a receita menos os custos. Ou criar uma regra que exibe o custo total e a análise de custo por envolvimento. Por exemplo, execute um relatório de  [!UICONTROL Canal de primeiro toque] mostrando novos envolvimentos, depois acrescente uma métrica de Custo de Primeiro Toque que mostre o custo por novo envolvimento através da criação de uma métrica calculada.

Consulte [Métricas calculadas usadas nos relatórios do Canal de marketing](../../components/c-marketing-channels/c-channel-calc-metrics.md#topic_4521D324A79E43EF99E69FCDE1E92F74).

É possível designar custos e orçamento a canais. Todos os custos recebem um intervalo de tempo durante o qual se aplicam ao relatório. Quando os custos são associados diretamente a um canal, uma métrica de distribuição é escolhida para mostrar a análise de custos entre campanhas dentro de um canal.

Após adicionar itens de custos e orçamento, é possível exportar os dados da tabela para um arquivo CSV. Também é possível importar um arquivo CSV para a página Custos do canal de marketing.

## Adicionar itens de custo e orçamento {#task_9238A033994440748960DE21593E6388}

Adicione itens de custo e orçamento aos Canais de marketing.

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. Na página do [!UICONTROL Gerenciador de conjunto de relatórios], selecione um conjunto de relatórios.
1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Costs]**.
1. Na página [!UICONTROL Custos do canal de marketing]**, clique em[!UICONTROL Adicionar item de custo]** ou **[!UICONTROL Adicionar item de orçamento]**.
1. Clique em **[!UICONTROL Salvar.]**

   Para continuar adicionando itens de custo, clique em **[!UICONTROL Salvar e adicionar outro]**.

1. (Optional) To export or import CSV files, access the [!UICONTROL Marketing Channel Costs] page, click **[!UICONTROL Export File]** or **[!UICONTROL Import File]**, then follow the prompts.

## Marketing Channel costs - definitions {#reference_0B193210E10A4B6B84A385A781FD9515}

Definições de campo para Custos de canal de marketing ou orçamentos.



| Campo | Definição |
|--- |--- |
| Nome | O nome do item de custo ou orçamento. (Esse é o valor Chave se estiver usando o SAINT.) |
| Canal | O canal ao qual deseja associar essa quantia. É preciso especificar se o custo ou orçamento se aplica a um canal de Primeiro Toque ou de Último Toque. Considere uma quantia de custo de primeiro toque como um novo envolvimento único. Uma quantia de custo de último toque é para click-throughs. |
| Período | O período que deseja usar para essa quantia. |
| Tipo | O tipo de custo ou orçamento, uma Taxa ou um Custo Único. A Taxa especifica um custo contínuo, como uma quantia por clique. Um Custo Único permite especificar uma quantia de Distribuir Por. Por exemplo, se você distribuir o custo por cliques, será atribuído 60% do custo total ao afiliado com 60% do total de cliques. O valor Distribuído Por é a métrica usada ao analisar classificações numéricas. |
| Exportar arquivo | Permite exportar os dados da tabela em um arquivo CSV. |
| Importar arquivo | importar um arquivo CSV para a página de Custos do canal de marketing. |
