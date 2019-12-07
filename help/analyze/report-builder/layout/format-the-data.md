---
description: Além das opções padrão de formatação de células disponíveis através do recurso Formatar > Células (Ctrl+1) do Excel, você pode aplicar formatação limitada a intervalos de células com o Construtor de relatórios. Essas opções de formatação dependem da métrica selecionada.
title: Formatar a data
topic: Report builder
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Formatar a data

Além das opções padrão de formatação de células disponíveis através do recurso Formatar &gt; Células (Ctrl+1) do Excel, você pode aplicar formatação limitada a intervalos de células com o Construtor de relatórios. Essas opções de formatação dependem da métrica selecionada.

After you [add dimensions](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) to the Row Labels grid, click **[!UICONTROL Format]**.

No menu **[!UICONTROL Formatar]**, clique em **Formato personalizado]para aplicar formatos personalizados a datas, semelhantes ao recurso de anexar como prefixo ou sufixo.[!UICONTROL ** Por exemplo, você pode inserir texto que sempre ocorre após a data (como D.C., A.C., A.H. etc.). Você pode adicionar texto antes da data, como [!UICONTROL Data de início] e [!UICONTROL Data de início e fim]. Além disso, você pode construir uma expressão de data personalizada a partir de abreviações de dia, mês e ano e usar um separador personalizado entre as partes da data. Todos os formatos de data devem consistir em somente três abreviações entre colchetes.

A tabela a seguir descreve como você pode usar abreviações de datas no campo [!UICONTROL Formato personalizado]:

| Abreviação | Significado | Exemplo   usando quarta-feira, 14 de março de 2012 |
|--- |--- |--- |
| MM/dd/yyy | Data numérica completa | 03/14/2012 |
| M | Número do mês | 3 |
| MM | Número do mês com zero à esquerda para meses &lt; 10 | 03 |
| MMM | Nome abreviado do mês | Mar |
| MMMM | Nome completo do mês | Março de |
| D | Nome completo da data | Quarta-feira, 14 de março de 2012 |
| d | Número do dia | 14 |
| dd | Número do dia com zero à esquerda para dias &lt; 10 | 01 - 09 |
| ddd | Nome abreviado do dia | Qua |
| dddd | Nome completo do dia | Quarta-feira |
| yy | Ano expresso com dois dígitos | 10 |
| yyyy | Ano completo expresso com quatro dígitos | 2012 |
