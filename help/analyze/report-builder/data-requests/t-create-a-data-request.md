---
description: Etapas para criar uma solicitação de dados básica do Construtor de relatórios.
title: Criar uma solicitação de dados
topic: Report builder
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Criar uma solicitação de dados do Construtor de relatórios

Etapas para criar uma solicitação básica de dados.

1. In Excel, click **[!UICONTROL Create]**.
1. In the [!UICONTROL Request Wizard: Step 1] window, select a [report suite](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (Opcional) Selecione um segmento para aplicar à solicitação. Quando um ou mais segmentos forem selecionados, aparecerão na parte superior da lista.

   O Construtor de relatórios usa os segmentos da mesma maneira que o Adobe Analytics usa. Consulte o [Guia de segmentação do Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/segment/). 1. (Opcional) Selecione uma lista [de](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md) publicação a ser usada para distribuição.
1. Select a [report type](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).
1. Especifique um intervalo [de](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) datas e uma [granularidade](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md)de relatório.
1. Clique em **[!UICONTROL Próximo]**.
1. In the [Layout - Request Wizard Step 2](/help/analyze/report-builder/layout/layout.md) window, specify a layout:

   | Elemento | Descrição |
   |---|---|
   | Layout dinâmico | Fornece linha, coluna e grade de métricas para o layout, de modo semelhante às tabelas padrão do Excel. Usando este layout, você pode adicionar divisões de solicitações à solicitação original. |
   | Layout personalizado | Oferece a maior parte da funcionalidade do [!UICONTROL Layout dinâmico], mas permite que você escolha onde cada item na grade deve estar localizado na planilha. Este layout proporciona a flexibilidade disponível em versões anteriores do   |

1. Na guia [!UICONTROL Métricas], clique duas vezes nas métricas na árvore (ou arraste-as) para adicioná-las à grade [!UICONTROL Métricas.]
1. Na guia [!UICONTROL Dimensões], clique duas vezes nas dimensões ou arraste-as para a grade [!UICONTROL Rótulos de linhas.]

   As [dimensões](https://marketing.adobe.com/resources/help/en_US/reference/dimensions.html) disponíveis na Etapa 2 dependem do relatório básico selecionado na Etapa 1 e da configuração do conjunto do conjunto de relatórios. As dimensões são itens correlacionados, sub-relacionados ou que são uma classificação da métrica original do tipo de relatório selecionado na janela [!UICONTROL Assistente de solicitações: etapa 1]. Para criar uma divisão na solicitação de dados, adicione mais de uma dimensão na Etapa 2.

   Consulte [Adicionar métricas e dimensões](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) para obter mais informações.
