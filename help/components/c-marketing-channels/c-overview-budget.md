---
description: Saiba como atribuir valores de custo e orçamento aos canais.
subtopic: Marketing channels
title: Custos e orçamentos
topic: Reports and analytics
uuid: 7ba0e968-e565-4d4c-8fc0-39bf25d3e5b1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Custos e orçamentos

Saiba como atribuir valores de custo e orçamento aos canais.

O custo representa o que é gasto no canal. O orçamento representa a quantia disponível destinada.

 Uma forma útil de visualizar seu ROI é criar uma métrica calculada que exibe a receita menos os custos. Ou criar uma regra que exibe o custo total e a análise de custo por envolvimento. Por exemplo, execute um relatório de [!UICONTROL Canal de primeiro toque] mostrando novos envolvimentos, depois acrescente uma métrica de Custo de Primeiro Toque que mostre o custo por novo envolvimento através da criação de uma métrica calculada.

See [Calculated metrics used Marketing Channel reports](/help/components/c-marketing-channels/c-channel-calc-metrics.md).

É possível designar custos e orçamento a canais. Todos os custos recebem um intervalo de tempo durante o qual se aplicam ao relatório. Quando os custos são associados diretamente a um canal, uma métrica de distribuição é escolhida para mostrar a análise de custos entre campanhas dentro de um canal.

Após adicionar itens de custos e orçamento, é possível exportar os dados da tabela para um arquivo CSV. Também é possível importar um arquivo CSV para a página Custos do canal de marketing.

## Adicionar itens de custo e orçamento {#add-cost-and-budget}

Adicione itens de custo e orçamento aos Canais de marketing.

1. Clique em **[!UICONTROL Analytics]** &gt; **[!UICONTROL Administrador]** &gt; **[!UICONTROL Conjuntos de relatórios]**.
1. Na página do [!UICONTROL Gerenciador de conjunto de relatórios], selecione um conjunto de relatórios.
1. Clique em **[!UICONTROL Editar configurações]** &gt; **[!UICONTROL Canais de marketing]** &gt; **[!UICONTROL Custos de canal de marketing]**.
1. Na página [!UICONTROL Custos do canal de marketing]**, clique em[!UICONTROL Adicionar item de custo]** ou **[!UICONTROL Adicionar item de orçamento]**.
1. Clique em **[!UICONTROL Salvar.]**

   Para continuar adicionando itens de custo, clique em **[!UICONTROL Salvar e adicionar outro]**.

1. (Opcional) Para exportar ou importar arquivos CSV, acesse a página de [!UICONTROL Custos de canal de marketing], clique em **[!UICONTROL Exportar arquivo]** ou **[!UICONTROL Importar arquivo]** e, em seguida, siga os prompts.

## Custos de canal de marketing - definições {#mktg-channel-costs}

Definições de campo para Custos de canal de marketing ou orçamentos.

| Campo | Definição |
|--- |--- |
| Nome | O nome do item de custo ou orçamento. (Esse é o valor Chave se estiver usando o SAINT.) |
| Canal | O canal ao qual deseja associar essa quantia. É preciso especificar se o custo ou orçamento se aplica a um canal de Primeiro Toque ou de Último Toque. Considere uma quantia de custo de primeiro toque como um novo envolvimento único. Uma quantia de custo de último toque é para click-throughs. |
| Período | O período que deseja usar para essa quantia. |
| Tipo | O tipo de custo ou orçamento, uma Taxa ou um Custo Único. A Taxa especifica um custo contínuo, como uma quantia por clique. Um Custo Único permite especificar uma quantia de Distribuir Por. Por exemplo, se você distribuir o custo por cliques, será atribuído 60% do custo total ao afiliado com 60% do total de cliques. O valor Distribuído Por é a métrica usada ao analisar classificações numéricas. |
| Exportar arquivo | Permite exportar os dados da tabela em um arquivo CSV. |
| Importar arquivo | importar um arquivo CSV para a página de Custos do canal de marketing. |
