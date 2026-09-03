---
description: Saiba como aplicar formatação padrão e limitada a intervalos de células.
title: Como formatar a data no Report Builder
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
feature: Report Builder
role: User, Admin
exl-id: 9b251b09-9156-40b5-8e1f-fb6594a25c26
TQID: https://experienceleague.adobe.com/8FuosvmSvi-bRNaG5QbwUExuDffOIXbrkuiQLh0NZXM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 271
ht-degree: 38%

---

# Formatar a data

{{legacy-arb}}

Além das opções padrão de formatação de células disponíveis através do recurso Formatar > Células (Ctrl+1) do Excel, você pode aplicar formatação limitada a intervalos de células com o Report Builder. Essas opções de formatação dependem da métrica escolhida.

Depois de [adicionar dimensões](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) à grade Rótulos de linhas, clique em **[!UICONTROL Formatar]**.

No menu **[!UICONTROL Formatar]**, clique em **[!UICONTROL Formato personalizado]** para aplicar formatos personalizados a datas, semelhantes ao recurso de anexar como prefixo ou sufixo. Por exemplo, você pode inserir texto que sempre ocorre após a data (como D.C., A.C., A.H. etc.). Você pode adicionar texto antes da data, como [!UICONTROL Data inicial] e [!UICONTROL Data inicial e final]. Além disso, você pode construir uma expressão de data personalizada a partir de abreviações de dia, mês e ano e usar um separador personalizado entre as partes da data. Todos os formatos de data devem consistir em três abreviações apenas entre parênteses.

A tabela a seguir descreve como usar abreviações de data no campo [!UICONTROL Formato Personalizado]:

| Abreviação | Significado | Exemplo usando quarta-feira, 14 de março de 2012 |
|--- |--- |--- |
| dd/MM/aaaa | Data numérica completa | 14/03/2012 |
| M | Número do mês | 3 |
| MM | Número de meses com preenchimento 0 para meses &lt; 10 | 03 |
| MMM | Nome abreviado do mês | Mar |
| MMMM | Nome longo do mês | Março de |
| D | Nome longo da data | quinta-feira, 14 de março de 2012 |
| d | Número do dia | 14 |
| dd | Número de dias com preenchimento 0 para dias &lt; 10 | 01 - 09 |
| ddd | Nome curto do dia | Qua |
| dddd | Nome longo do dia | Quarta-feira |
| aa | Ano de 2 dígitos | 10 |
| aaaa | Ano completo de 4 dígitos | 2012 |
