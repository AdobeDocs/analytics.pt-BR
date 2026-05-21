---
description: Saiba como editar configurações de coluna para configurar a formatação de coluna; alguns elementos podem ser condicionais.
title: Configurações de coluna
uuid: 151d66da-04f7-4d0f-985c-4fdd92bc1308
feature: Freeform Tables
role: User, Admin
exl-id: 82034838-b015-4ca2-adb6-736f20a478d8
TQID: https://experienceleague.adobe.com/5yrcNh-n0rOA-PZr5hmZD4ykJCKBE-EId9eVY5rOj54
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: c67272a6-888e-425e-9e97-a87304637eedid: dcae653e-62c6-4cc8-84e6-ee110b848296id: e318d41c-1d01-4c1e-9b18-1f61d435ceeeid: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5520579-b31f-4df7-9281-f0d9f91e2edc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 908
ht-degree: 87%

---

# Configurações de coluna

As [!UICONTROL configurações de coluna] permitem definir a formatação da coluna, e alguns elementos podem ser condicionais.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configurações de linha e coluna em uma tabela de forma livre](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/row-and-column-settings-in-freeform-tables){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]


Para acessar essas [!UICONTROL configurações], selecione ![Configurações de coluna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) no cabeçalho da coluna.

![Configurações de coluna](assets/column-settings.png)


É possível editar as configurações de diversas colunas de uma só vez. Selecione várias colunas e clique em ![Configuração](/help/assets/icons/Setting.svg) em qualquer uma delas. As alterações feitas serão aplicadas a todas as colunas com as células selecionadas.

| Opção | Descrição |
| --- | --- |
| **[!UICONTROL Mostrar total]** | Mostra uma soma da coluna do lado do cliente. Este total **não** elimina a duplicação de métricas como sessões ou pessoas. |
| **[!UICONTROL Exibir total geral]** | Mostra uma soma da coluna do lado do servidor. O total geral remove a duplicação de métricas, como sessões ou pessoas. |
| **[!UICONTROL Mostrar minigráfico]** | Mostra um gráfico de linhas no cabeçalho da coluna. |
| **[!UICONTROL Número]** | Determina se uma célula exibe ou oculta o valor numérico da métrica. Por exemplo, se a métrica for Exibições de página, o valor numérico será o número de exibições de página para o item da linha. |
| **[!UICONTROL Percent]** | Determina se uma célula exibe ou oculta o valor porcentual da métrica. Por exemplo, se a métrica for Exibições de página, o valor porcentual será o número de exibições de página referente ao item da linha dividido pelo total de exibições de página da coluna.  Observação: é possível obter porcentagens maiores que 100% para garantir a precisão. O limite superior pode ser movido para 1.000%, a fim de evitar que a largura das colunas fique muito grande. |
| **[!UICONTROL Mostrar anomalias]** | Determina se a detecção de anomalias é executada nos valores desta coluna. |
| **[!UICONTROL Mostrar previsão]** | Determine se os valores de previsão são exibidos nessa coluna. |
| **[!UICONTROL Quebrar linha do texto de cabeçalho]** | Permite a quebra de linha do texto de cabeçalho em tabelas de forma livre para torná-lo mais legível e facilitar o compartilhamento de tabelas. Essa quebra de linha é útil para renderização de PDF e para métricas com nomes longos. Habilitado por padrão. |
| **[!UICONTROL Interpretar zero como nenhum valor]** | Para células com um valor 0, determina se exibirá um 0 ou uma célula em branco. Isso é útil quando você precisar observar os dados de cada dia do mês e alguns dias estiverem no futuro.  Em vez de mostrar 0 para as datas futuras, células em branco serão exibidas. Os gráficos também respeitam essa configuração (ou seja, os gráficos não mostram linhas ou barras com valores 0). |
| **[!UICONTROL Histórico]** | Determina se uma célula mostra ou oculta todas as formatações de célula, incluindo o gráfico de barras e a formatação condicional. |
| **[!UICONTROL Gráfico de barras]** | Exibe um gráfico de barras horizontal que representa o valor da célula relativo ao total da coluna. |
| **[!UICONTROL Formatação condicional]** | Usar formatação condicional. Consulte a [seção](#conditional-formatting) abaixo. |
| **[!UICONTROL Visualização de célula de tabela]** | Uma visualização de como cada célula é exibida com as opções de formatação atualmente selecionadas aplicadas. |
| **[!UICONTROL Usar modelo de atribuição não padrão]** | Usa um modelo de atribuição não padrão. Consulte a [seção](#use-non-default-attribution-model) abaixo. |

## Formatação condicional {#conditional-formatting}

A formatação condicional aplica formatação a limites superiores, intermediários e inferiores que você pode definir. A aplicação da formatação condicional em tabelas de forma livre também é habilitada automaticamente em detalhamentos, a menos que os limites [!UICONTROL personalizados] estejam selecionados.

![Formatação condicional](./assets/conditional-formatting.png)

| Opções de formatação condicional | Descrição |
| --- | --- |
| **[!UICONTROL Usar limites de porcentagem]** | Altera o intervalo limite para se basear em porcentagens em vez de valores absolutos. O intervalo limite de porcentagem funciona com métricas exclusivamente baseadas em porcentagem (como a Taxa de rejeição) e com métricas que possuem uma contagem e uma porcentagem (como Exibições de página). |
| **[!UICONTROL Geração automática]** | Calcular limites superior/médio/inferior automaticamente de acordo com os dados. O limite superior é o maior valor nesta coluna. O limite inferior é o mais baixo e o ponto médio é a média dos limites superior e inferior. |
| **[!UICONTROL Personalizado]** | Permite atribuir manualmente o **[!UICONTROL Limite superior]**, o **[!UICONTROL Ponto médio]** e o **[!UICONTROL Limite inferior]**. Os limites oferecem a flexibilidade de determinar quando o valor de uma coluna se torna bom, médio ou ruim. |
| **[!UICONTROL Paleta de formatação condicional]** | Aplica um conjunto de cores pré-configurado às células. Dependendo de qual dos quatro esquemas de cores disponíveis você selecionar, cores diferentes serão atribuídas a valores altos, valores de ponto médio e valores baixos. <br> Substituir uma dimensão na tabela redefine os limites da formatação condicional. Substituir uma métrica recalcula os limites da coluna (na qual haja uma métrica no eixo X e uma dimensão no eixo Y). |

## Usar modelo de atribuição não padrão {#use-non-default-attribution-model}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_column_usenondefaultattributionmodel"
>title="Usar modelo de atribuição não padrão"
>abstract="Habilite um modelo de atribuição não padrão para as colunas selecionadas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_column_usenondefaultattributionmodel_disabled"
>title="Usar modelo de atribuição não padrão"
>abstract="O modo de atribuição não padrão não está disponível para esta métrica."

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>Considere o seguinte ao atualizar a atribuição de um componente para um modelo de atribuição não padrão:
>
>* **Ao usar o componente em um relatório com *uma única dimensão*:** a atribuição do componente ignora o modelo de alocação quando um modelo de atribuição não padrão é usado.
>
>* **Ao usar o componente em um relatório com *várias dimensões*:** a atribuição do componente retém o modelo de alocação quando um modelo de atribuição não padrão é usado.
>
>

Para usar um modelo de atribuição não padrão com uma métrica no Analysis Workspace:

1. Clique em **[!UICONTROL Usar modelo de atribuição não padrão]**. Se ele já tiver sido selecionado, use **[!UICONTROL Editar]** para editar o modelo de atribuição. Ou desmarque a opção para retornar ao modelo de atribuição padrão.

   ![As opções de configuração de coluna com destaque para a opção Configurações de dados: usar modelo de atribuição não padrão.](assets/attribution-checkbox.png)

2. Em **[!UICONTROL Modelo de atribuição de coluna]**, selecione um **[!UICONTROL Modelo]** e uma **[!UICONTROL Janela de retrospectiva]**. Essa configuração determina a janela de atribuição de dados que será aplicada a cada conversão.

   ![As opções de Modelo de atribuição de coluna com a opção Linear selecionada.](assets/attribution-select.png)


### Modelos de atribuição

{{attribution-models-details}}


### Container

{{attribution-container}}


### Janela de retrospectiva

{{attribution-lookback-window}}


### Exemplo

{{attribution-example}}

>[!MORELIKETHIS]
>
>* [Gerenciar fontes de dados](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md)


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Colunas dinâmicas](https://video.tv.adobe.com/v/23138?quality=12&learn=on){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]

