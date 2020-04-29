---
description: Crie uma coorte e execute um relatório de análise de coorte no Analysis Workspace.
keywords: Analysis Workspace
title: Executar um relatório de análise de coorte
topic: Reports and analytics
uuid: 5574230f-8f35-43ea-88d6-cb4960ff0bf4
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Configurar um relatório de análise de coorte

Crie uma coorte e execute um relatório de análise de coorte no Analysis Workspace.

1. In Analysis Workspace, click the **[!UICONTROL Visualizations]** icon in the left rail and drag a **[!UICONTROL Cohort Table]** to the canvas.

   ![](assets/cohort-table.png)

1. Defina os valores **[!UICONTROL Inclusion Criteria]**, **[!UICONTROL Return Criteria]**, **[!UICONTROL Cohort Type]** e **[!UICONTROL Settings]** conforme definido na tabela abaixo.

| Elemento | Descrição |
|--- |--- |
| **[!UICONTROL Inclusion Criteria]** | É possível aplicar até 10 segmentos de inclusão e até 3 métricas de inclusão. A métrica especifica o que posiciona um usuário em uma coorte. Por exemplo, se a métrica de inclusão for Pedidos, apenas os usuários que fizeram um pedido durante o período da análise da coorte serão incluídos na coorte inicial.<br>O operador padrão entre métricas é AND, mas você pode alterá-lo para OR. Além disso, é possível adicionar filtros numéricos a essas métricas. Por exemplo: “Visitas >= 1”.</br> |
| **[!UICONTROL Return Criteria]** | É possível aplicar até 10 segmentos de retorno e até 3 métricas de retorno. A métrica indica se o usuário foi retido (retenção) ou não (churn). Por exemplo, se a métrica de retorno for Visualizações de vídeo, apenas os usuários que visualizaram os vídeos durante os períodos subsequentes (após o período em que foram adicionados a um coorte) serão representados como retidos. A métrica Visitas também quantifica a retenção. |
| **[!UICONTROL Granularity]** | A granularidade de tempo Dia, Semana, Mês, Trimestre ou Ano. |
| **[!UICONTROL Type]** | **[!UICONTROL Retention]**(padrão): Um coorte de retenção mede o quão bem seus visitantes retornam à sua propriedade ao longo do tempo. Esse é o coorte padrão que sempre tivemos e indica o comportamento de usuários repetidos e que retornam. Um Coorte de retenção é indicado pela cor verde na tabela.<br>**[!UICONTROL Churn]**: Um coorte de churn (também conhecido como &quot;atrito&quot; ou &quot;fallout&quot;) mede como seus coortes de visitante saem de sua propriedade ao longo do tempo. Abandono = 1 - Retenção. O abandono é uma boa medida para medir a adesão, por mostrar a frequência com que clientes não voltam. É possível usar o abandono para analisar e identificar as áreas de foco e os segmentos de coorte que precisam de mais atenção. A Churn Cohort is indicated by the color red in the table (similar to fallout in our **[!UICONTROL Flow]** visualization).</br> |
| **[!UICONTROL Settings]** | **[!UICONTROL Rolling Calculation]**: Calcule a retenção ou churn com base na coluna anterior em vez da coluna Incluídos (padrão). O Cálculo contínuo altera o método de cálculo para seus períodos de “retorno”. O cálculo normal encontra usuários de maneira independende que atendem ao critério de “retorno” e faziam parte do período de inclusão, mesmo se estavam ou não no coorte do período anterior. Em vez disso, o Cálculo contínuo encontra usuários que atendem ao critério de “retorno” e faziam parte do período anterior. Portanto, o Cálculo contínuo filtra os usuários que continuamente atendem ao critério de “retorno” ao longo do tempo. O critério de retorno é aplicado a cada período até o período selecionado. </br><br>**[!UICONTROL Latency Table]**: Uma tabela de latência mede o tempo decorrido antes e depois da ocorrência do evento de inclusão. A Latência é ideal para ser usada antes e depois da análise. Por exemplo, se você tiver um lançamento de produto ou campanha em breve e deseja monitorar o comportamento previamente, além de acompanhar o desempenho posteriormente, a tabela de Latência mostrará os comportamentos de antes e depois lado a lado para que você veja o impacto direto. As células de pré-inclusão na Tabela de latência são calculadas por usuários que atendem ao critério de “inclusão” no período de inclusão e ao critério de “retorno” em períodos anteriores ao de inclusão. Observe que Tabelas de latência e o Coorte de dimensão personalizado não podem ser usados juntos.</br><br>**[!UICONTROL Custom Dimension Cohort]**: Crie coortes com base na dimensão selecionada, em vez de coortes com base no tempo (padrão). Muitos usuários desejam analisar suas coortes segundo critérios que não sejam o tempo, por isso o novo recurso de Coorte de dimensão personalizada permite ter flexibilidade para criar coortes com base nas dimensões desejadas. Use dimensões como canal de marketing, campanha, produto, página, região ou qualquer outra dimensão no Adobe Analytics para exibir como a retenção é alterada com base nos valores diferentes destas dimensões. A definição de segmento Dimensão de coorte personalizada aplica o item de dimensão somente como parte do período de inclusão, não como parte da definição de retorno.</br><br>Depois de escolher a opção Dimensão de coorte personalizada, você pode arrastar e soltar qualquer dimensão que desejar na área designada. Isso permite comparar itens de dimensão similares entre o mesmo período de tempo. Por exemplo, é possível comparar o desempenho de cidades lado a lado, produtos, campanhas etc. Retornará seus 14 itens de dimensão principais. Entretanto, você pode usar um filtro (acesse-o passando o mouse sobre o lado direito da dimensão que foi arrastada) para exibir somente os itens de dimensão desejados. Um Coorte de dimensão personalizado não pode ser usado com o recurso de Tabela de latência.</br> |

1. Ajuste a **[!UICONTROL Cohort Table Settings]** imagem clicando no ícone de engrenagem.

| Configuração | Descrição | | Mostrar apenas porcentagem| Remove o número e mostra somente a porcentagem. | | Porcentagem arredondada para o inteiro mais próximo | Arredonda o valor percentual para o inteiro mais próximo em vez de mostrar o valor decimal. | | Mostrar linha de porcentagem média | Insere uma nova linha na parte superior da tabela e adiciona a média para os valores dentro de cada coluna. |

## Criar o relatório de análise de coorte

1. Clique em **[!UICONTROL Build]**.

   ![Resultado da etapa](assets/cohort-report.png)

   O relatório mostra os visitantes que fizeram um pedido ( *`Included`* coluna) e que retornaram ao site em visitas subsequentes. A redução nas visitas ao longo do tempo permite que você detecte os problemas e aja conforme o necessário.
1. (Opcional) Crie um segmento a partir de uma seleção.

   Selecione as células (contíguas ou não contíguas) e clique com o botão direito do mouse em > **[!UICONTROL Create Segment From Selection]**.

1. In the [Segment Builder](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md), further edit the segment, then click **[!UICONTROL Save]**.

   The saved segment is available for use in the [!UICONTROL Segment] panel in Analysis Workspace.
1. Nomeie e salve seu projeto de coorte.
1. (Opcional) [Prepare e compartilhe](/help/analyze/analysis-workspace/curate-share/curate.md) os componentes do projeto.

   >[!NOTE]
   >
   >É necessário salvar o projeto antes que a preparação esteja disponível.

