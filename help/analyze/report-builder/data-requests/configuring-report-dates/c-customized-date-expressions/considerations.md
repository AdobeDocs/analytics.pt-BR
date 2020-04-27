---
description: 'Duas importantes considerações ao usar a Expressão personalizada para definir o intervalo de datas '
title: Considerações de data personalizada
topic: Report builder
uuid: a3bb3a63-0f15-4292-ade7-4ea852fe68c8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Considerações de data personalizada

Duas importantes considerações ao usar a Expressão personalizada para definir o intervalo de datas:

* A data em que o relatório (a partir de) é executado (ou em que as solicitações são atualizadas) determina quais dados estarão disponíveis.
* A sobreposição das datas inicial e final do relatório afeta o intervalo de datas coberto pelo relatório.

Visto que a disponibilidade dos dados está sujeita tanto ao período do relatório quanto à data em que as solicitações no relatório são atualizadas, certifique-se de executar o relatório no dia apropriado para extrair as informações desejadas. Os exemplos abaixo demonstram ambas essas considerações.

Assume you make a request for [!UICONTROL Page Views] using Aggregated granularity. Na América do Norte, a semana começa no domingo. Para obter relatórios atualizados para o período de domingo a sábado (por exemplo, 23 de novembro a 29 de novembro de 2008), execute o relatório (atualize as solicitações) no domingo (30 de novembro) para a semana anterior (23/11 a 29/11).

Use esta expressão personalizada:

*De:* cw-1w *Para:* cw-1d

An analysis of the customize expression when the inclusive [!UICONTROL End Date] for the request is 11/30:

*De:* cw-1w

o dia da semana corrente começando no domingo, 30 de novembro, menos sete dias = o dia da semana passada começando no domingo, 23 de novembro

*Para:* cw-1d

o dia da semana corrente começando no domingo, 30 de novembro, menos um dia = sábado, 29 de novembro

After the customized expression is mapped to the spreadsheet, refresh the request using Sunday, November 30, 2008 as the inclusive [!UICONTROL End Date] for the floating request. Os dados refletem o período de uma semana.

Se, em vez disso, você atualizar a expressão e especificar sábado, 29 de novembro, como o [!UICONTROL End Date] para a solicitação flutuante, os dados refletirão a semana 16/11 a 22/11. Isso ocorre porque a data de referência para a atualização da solicitação é um dia antes.

Here are the differences when the inclusive [!UICONTROL End Date] for the request is 11/29:

*De:* cw-1w

o dia da semana corrente começando no domingo, 23 de novembro, menos sete dias = o dia da semana passada começando no domingo, 16 de novembro

*Para:* cw-1d

o dia da semana corrente começando no domingo, 23 de novembro, menos um dia = sábado, 22 de novembro

Na Europa e em alguns outros países, a semana começa na segunda-feira, e não no domingo. Nesse caso, você pode personalizar o calendário para alterar a data inicial. (Consulte [Calendário personalizado](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md).)
