---
description: Além das opções padrão de formatação de células disponíveis através do recurso Formatar > Células (Ctrl+1) do Excel, você pode aplicar formatação limitada a intervalos de células com o Report Builder. Essas opções de formatação dependem da métrica selecionada.
title: Formatar a data
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 98%

---


# Formatar a data

Além das opções padrão de formatação de células disponíveis através do recurso Formatar > Células (Ctrl+1) do Excel, você pode aplicar formatação limitada a intervalos de células com o Report Builder. Essas opções de formatação dependem da métrica selecionada.

Depois de [adicionar dimensões](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) à grade Rótulos de linhas, clique em **[!UICONTROL Formatar]**.

No menu **[!UICONTROL Formatar]**, clique em **[!UICONTROL Formato personalizado]** para aplicar formatos personalizados a datas, semelhantes ao recurso de anexar como prefixo ou sufixo. Por exemplo, você pode inserir texto que sempre ocorre após a data (como D.C., A.C., A.H. etc.). Você pode adicionar texto antes da data, como [!UICONTROL Data de início] e [!UICONTROL Data de início e fim]. Além disso, você pode construir uma expressão de data personalizada a partir de abreviações de dia, mês e ano e usar um separador personalizado entre as partes da data. Todos os formatos de data devem consistir em somente três abreviações entre colchetes.

A tabela a seguir descreve como você pode usar abreviações de datas no campo [!UICONTROL Formato personalizado]:

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
