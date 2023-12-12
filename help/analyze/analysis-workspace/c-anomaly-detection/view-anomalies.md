---
description: É possível exibir anomalias em uma tabela ou em um gráfico de linhas.
title: Exibir anomalias no Analysis Workspace
feature: Anomaly Detection
role: User, Admin
exl-id: 32edc7f4-c9b9-472a-b328-246ea5b54d07
source-git-commit: 984406d00e5a5ae966fff60ec9fcfcb000958696
workflow-type: ht
source-wordcount: '474'
ht-degree: 100%

---

# Exibir anomalias no Analysis Workspace

É possível exibir anomalias em uma tabela ou em um gráfico de linhas.

## Exibir anomalias em uma tabela {#section_869A87B92B574A38B017A980ED8A29C5}

É possível exibir anomalias em uma Tabela de forma livre da série de tempo.

1. Selecione o ícone de configurações de coluna no cabeçalho da coluna e verifique se a opção [!UICONTROL **Anomalias**] está selecionada na lista de opções. Para obter mais informações, consulte [Configurações de coluna](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).

1. Clique fora do menu de configurações para exibir a tabela atualizada.

   ![](assets/anomaly_detected.png)

1. As anomalias são mostradas na tabela como a seguir:

   Um **triângulo cinza escuro** é exibido no canto superior direito de cada linha, onde uma anomalia de dados é detectada.

   A **linha vertical** colorida em cada linha indica o valor esperado. A **área sombreada** colorida em cada linha indica o valor real. A forma como a linha (valor esperado) se compara com a área sombreada (valor real) determina se há uma anomalia. (Uma observação é considerada anômala com base nas técnicas estatísticas avançadas descritas em [Técnicas estatísticas usadas na detecção de anomalias](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).)

1. Selecione o triângulo cinza no canto superior direito de uma linha para exibir detalhes sobre a anomalia. Mostra a extensão (em percentagem) em que o valor real diverge acima ou abaixo do valor esperado.

## Exibir anomalias em um gráfico de linhas {#section_7C1192AFDB4345A8A2CCFB3AE0C47D82}

Os gráficos de linha são a única visualização que permite visualizar anomalias.

Para exibir anomalias em um gráfico de linhas:

1. Selecione o ícone de configurações no cabeçalho da visualização e verifique se a opção [!UICONTROL **Mostrar anomalias**] está selecionada na lista de opções. Para obter mais informações, consulte [Linha](/help/analyze/analysis-workspace/visualizations/line.md).

1. (Opcional) Para permitir que o intervalo de confiança dimensione o gráfico, selecione o ícone de configurações no cabeçalho da visualização e selecione a opção **[!UICONTROL Permitir que as anomalias dimensionem o eixo Y]**.

   Essa opção não é selecionada por padrão porque, às vezes, pode tornar o gráfico menos legível.

1. Clique fora do menu de configurações para exibir o gráfico de linhas atualizado.

   ![](assets/anomaly_linechart.png)

   As anomalias são mostradas no gráfico de linhas da seguinte maneira:

   Um **ponto branco** aparece na linha sempre que uma anomalia de dados é detectada. (Uma observação é considerada anômala com base nas técnicas estatísticas avançadas descritas em [Técnicas estatísticas usadas na detecção de anomalias](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).)

   A **área sombreada clara** é a faixa de confiança, ou o intervalo esperado, em que os valores devem ocorrer. Qualquer valor que não esteja nesse intervalo esperado é uma anomalia.

   Se você tiver várias métricas no gráfico de linhas, apenas as anomalias serão exibidas e você deverá passar o mouse sobre cada anomalia para ver a faixa de confiança dessa métrica.

   A **linha pontilhada** é o valor esperado exato.

1. Clique em uma anomalia (ponto branco) para exibir as seguintes informações:

   * A data de ocorrência da anomalia

   * O valor bruto da anomalia

   * O valor percentual superior ou inferior ao valor esperado, que é representado pela linha sólida verde.

   * O link Analisar para iniciar a Análise de contribuição

     (Consulte [Visão geral da Detecção de anomalias](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) para obter mais informações).





