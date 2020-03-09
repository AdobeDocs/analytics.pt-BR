---
description: Etapas para criar uma solicitação básica de dados do Report Builder.
title: Criar uma solicitação de dados
topic: Report builder
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Criar uma solicitação de dados do Report Builder

Etapas para criar uma solicitação básica de dados.

1. No Excel, clique em **[!UICONTROL Criar]**.
1. Na janela [!UICONTROL Assistente de solicitações: Etapa 1], selecione um [conjunto de relatórios](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (Opcional) Selecione um segmento para aplicar à solicitação. Quando um ou mais segmentos forem selecionados, aparecerão na parte superior da lista.

   O Report Builder usa os segmentos da mesma maneira que o Adobe Analytics usa. Consulte o [Guia de segmentação do Analytics](https://marketing.adobe.com/resources/help/pt_BR/analytics/segment/). 1. (Opcional) Selecione uma [lista de publicação](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md) a ser usada para distribuição.
1. Selecionar um [tipo de relatório](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).
1. Especifique um [intervalo de datas](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) e uma [granularidade](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md) do relatório.
1. Clique em **[!UICONTROL Próximo]**.
1. Na janela [Layout-Assistente de solicitações: etapa 2](/help/analyze/report-builder/layout/layout.md), especifique um layout:

   | Elemento | Descrição |
   |---|---|
   | Layout dinâmico | Fornece linha, coluna e grade de métricas para o layout, de modo semelhante às tabelas padrão do Excel. Usando este layout, você pode adicionar divisões de solicitações à solicitação original. |
   | Layout personalizado | Oferece a maior parte da funcionalidade do [!UICONTROL Layout dinâmico], mas permite que você escolha onde cada item na grade deve estar localizado na planilha. Este layout proporciona a flexibilidade disponível em versões anteriores do |

1. Na guia [!UICONTROL Métricas], clique duas vezes nas métricas na árvore (ou arraste-as) para adicioná-las à grade [!UICONTROL Métricas].
1. Na guia [!UICONTROL Dimensões], clique duas vezes nas dimensões ou arraste-as para a grade [!UICONTROL Rótulos de linhas].

   As [dimensões](https://marketing.adobe.com/resources/help/pt_BR/reference/dimensions.html) disponíveis na Etapa 2 dependem do relatório básico selecionado na Etapa 1 e da configuração do conjunto do conjunto de relatórios. As dimensões são itens correlacionados, sub-relacionados ou que são uma classificação da métrica original do tipo de relatório selecionado na janela [!UICONTROL Assistente de solicitações: etapa 1]. Para criar uma divisão na solicitação de dados, adicione mais de uma dimensão na Etapa 2.

   Consulte [Adicionar métricas e dimensões](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) para obter mais informações.
