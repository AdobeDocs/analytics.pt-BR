---
description: Etapas para criar uma solicitação básica de dados do Report Builder.
title: Criar uma solicitação de dados
feature: Report Builder
role: User, Admin
exl-id: 21d552a0-7a58-4217-ba8a-7c87eb4757f6
TQID: https://experienceleague.adobe.com/w-oiIfs1qFMoQbaN8YrNIn1TRNHeN97lQOlkLeXdLb0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 284
ht-degree: 53%

---

# Criar uma solicitação de dados do Report Builder

{{legacy-arb}}

Etapas para criar uma solicitação básica de dados.

1. No Excel, clique em **[!UICONTROL Criar]**.
1. Na janela [!UICONTROL Assistente de solicitações: Etapa 1], selecione um [conjunto de relatórios](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (Opcional) Selecione um segmento para aplicar à solicitação. Quando um ou mais segmentos forem selecionados, aparecerão na parte superior da lista.

   O Report Builder usa os segmentos da mesma maneira que o Adobe Analytics usa. Consulte o [Guia de segmentação do Analytics](/help/components/segmentation/seg-home.md).
1. Selecionar um [tipo de relatório](/help/analyze/legacy-report-builder/data-requests/c-report-types/select-report-types.md).
1. Especifique um [intervalo de datas](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md) e uma [granularidade](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/granularity.md) do relatório.
1. Clique em **[!UICONTROL Próximo]**.
1. Na janela [Layout-Assistente de solicitações: etapa 2](/help/analyze/legacy-report-builder/layout/layout.md), especifique um layout:

   | Elemento | Descrição |
   |---|---|
   | Layout dinâmico | Fornece uma grade de linha, coluna e métrica para layout, semelhante às tabelas padrão do Excel. Usando este layout, você pode adicionar solicitações de divisão dentro de uma solicitação original. |
   | Layout personalizado | Fornece a maior parte da funcionalidade do [!UICONTROL Layout Dinâmico], mas permite que você escolha onde cada item na grade deve estar localizado na planilha. Este layout proporciona a flexibilidade disponível em versões anteriores do |

1. Na guia [!UICONTROL Métricas], clique duas vezes nas métricas na árvore (ou arraste-as) para adicioná-las à grade [!UICONTROL Métricas].
1. Na guia [!UICONTROL Dimensões], clique duas vezes nas dimensões ou arraste-as para a grade [!UICONTROL Rótulos de linhas].

   As [dimensões](/help/analyze/report-builder/filter-dimensions.md) disponíveis na Etapa 2 dependem do relatório base selecionado na Etapa 1 e da configuração do conjunto de relatórios. As dimensões são itens que se correlacionam, se sub-relacionam ou são uma classificação da métrica do tipo de relatório original selecionada na janela [!UICONTROL Assistente de solicitações: Etapa 1]. Adicionar mais de uma dimensão na Etapa 2 é como você cria um detalhamento em sua solicitação de dados.

   Consulte [Adicionar métricas e dimensões](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) para obter mais informações.
