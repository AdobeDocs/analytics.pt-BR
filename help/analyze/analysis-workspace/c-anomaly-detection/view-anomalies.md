---
description: Entenda como visualizar e analisar anomalias de dados no Analysis Workspace.
title: Exibir anomalias
feature: Anomaly Detection
role: User, Admin
exl-id: 32edc7f4-c9b9-472a-b328-246ea5b54d07
TQID: https://experienceleague.adobe.com/FFrOBGUYdaBiIzutrZNlcKcLD8jUiT2aCpGd252rVlU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: c67272a6-888e-425e-9e97-a87304637eed
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 448
ht-degree: 45%

---

# Exibir anomalias

Você pode exibir anomalias no Analysis Workspace em uma tabela ou em um gráfico de linhas.

## Exibir anomalias em uma tabela {#section_869A87B92B574A38B017A980ED8A29C5}

É possível exibir anomalias em uma Tabela de forma livre da série de tempo.

1. Selecione a ![Configuração](/help/assets/icons/Setting.svg) no cabeçalho da coluna e verifique se a opção **[!UICONTROL Anomalias]** está selecionada na lista de opções. Para obter mais informações, consulte [Configurações de coluna](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. As anomalias são mostradas na tabela como a seguir:

   ![Anomalias detectadas](assets/anomaly-detected.png)

   Um ◥ é exibido no canto superior direito de cada linha em que uma anomalia de dados é detectada.

   A **linha vertical colorida** em cada linha ➋ indica o valor esperado. A **área sombreada colorida** em cada linha ➊ indica o valor real. A forma como a linha (valor esperado) se compara com a área sombreada (valor real) determina se há uma anomalia. (Uma observação é considerada anômala com base nas técnicas estatísticas avançadas descritas em [Técnicas estatísticas usadas na detecção de anomalias](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).)

1. Selecione ◥ no canto superior direito de uma linha para ver os detalhes sobre a anomalia. Mostra a extensão (em percentagem) em que o valor real diverge acima ou abaixo do valor esperado.
1. Selecione [Abrir análise de contribuição](run-contribution-analysis.md) para iniciar a análise de contribuição.

## Exibir anomalias em um gráfico de linhas

Os gráficos de linha são a única visualização que permite visualizar anomalias.

Para exibir anomalias em um gráfico de linhas:

1. Selecione ![Configuração](/help/assets/icons/Setting.svg) no cabeçalho da visualização e certifique-se de que a opção [!UICONTROL **Mostrar anomalias**] esteja selecionada na lista de opções. Para obter mais informações, consulte [Linha](/help/analyze/analysis-workspace/visualizations/line.md).

1. (Opcional) Para permitir que o intervalo de confiança dimensione o gráfico, selecione ![Configuração](/help/assets/icons/Setting.svg) no cabeçalho da visualização e selecione a opção **[!UICONTROL Permitir que anomalias dimensionem o eixo Y]**.

   Essa opção não é selecionada por padrão porque, às vezes, pode tornar o gráfico menos legível.

   As anomalias são mostradas no gráfico de linhas da seguinte maneira:

   ![Visualização de linha detectada por anomalia](assets/anomaly-detected-line.gif)

   Um **ponto branco** aparece na linha sempre que uma anomalia de dados é detectada. (Uma observação é considerada anômala com base nas técnicas estatísticas avançadas descritas em [Técnicas estatísticas usadas na detecção de anomalias](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).)

   A **área sombreada clara** é a faixa de confiança, ou o intervalo esperado, em que os valores devem ocorrer. Qualquer valor que não esteja nesse intervalo esperado é uma anomalia.

   Se você tiver várias métricas no gráfico de linhas, apenas as anomalias serão exibidas e você deverá passar o mouse sobre cada anomalia para ver a faixa de confiança dessa métrica.

   A **linha pontilhada** é o valor esperado exato.

1. Selecione uma anomalia (ponto branco) para exibir as seguintes informações:

   * A data em que a anomalia ocorreu.

   * O valor bruto da anomalia.

   * O valor percentual acima ou abaixo do valor esperado, que é representado pela linha verde sólida.

   * O link **[!UICONTROL Analisar]** para iniciar a Análise de contribuição






