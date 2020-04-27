---
description: Além das opções padrão de formatação de células disponíveis através do recurso Formatar > Células (Ctrl+1) do Excel, você pode aplicar formatação limitada a intervalos de células com o Report Builder. Essas opções de formatação dependem da métrica selecionada.
title: Formatar a data
topic: Report builder
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Formatar a data

Além das opções padrão de formatação de células disponíveis através do recurso Formatar > Células (Ctrl+1) do Excel, você pode aplicar formatação limitada a intervalos de células com o Report Builder. Essas opções de formatação dependem da métrica selecionada.

After you [add dimensions](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) to the Row Labels grid, click **[!UICONTROL Format]**.

In the **[!UICONTROL Format]** menu, click **[!UICONTROL Custom Format]** to apply customized formats for dates similar to the prepend and postpend feature. Por exemplo, você pode inserir texto que sempre ocorre após a data (como D.C., A.C., A.H. etc.). É possível adicionar texto antes da data, como [!UICONTROL Start Date] e [!UICONTROL Start and End Date]. Além disso, você pode construir uma expressão de data personalizada a partir de abreviações de dia, mês e ano e usar um separador personalizado entre as partes da data. Todos os formatos de data devem consistir em somente três abreviações entre colchetes.

The following table describes how you can use date abbreviations in the [!UICONTROL Custom Format] field:

| Abreviação | Significado | Exemplo   usando quarta-feira, 14 de março de 2012 |
|--- |--- |--- |
| dd/MM/aaaa | Data numérica completa | 14/03/2012 |
| M | Número do mês | 3 |
| MM | Número do mês com zero à esquerda para meses &lt; 10 | 03 |
| MMM | Nome abreviado do mês | Mar |
| MMMM | Nome completo do mês | Março de |
| D | Nome completo da data | Quarta-feira, 14 de março de 2012 |
| d | Número do dia | 14 |
| dd | Número do dia com zero à esquerda para dias &lt; 10 | 01 - 09 |
| ddd | Nome abreviado do dia | Qua |
| dddd | Nome completo do dia | Quarta-feira |
| aa | Ano expresso com dois dígitos | 10 |
| aaaa | Ano completo expresso com quatro dígitos | 2012 |
