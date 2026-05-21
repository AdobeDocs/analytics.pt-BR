---
description: Duas importantes considerações ao usar a Expressão personalizada para definir o intervalo de datas
title: Considerações de data personalizada
uuid: a3bb3a63-0f15-4292-ade7-4ea852fe68c8
feature: Report Builder
role: User, Admin
exl-id: 66b817b3-7e9e-4030-92f3-797e730f9661
TQID: https://experienceleague.adobe.com/7PLNffmZnNnQ2X0HgnqYa8R3zWQvFPMSM8sbWocmxH4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 415
ht-degree: 22%

---

# Considerações de data personalizada

{{legacy-arb}}

Duas importantes considerações ao usar a Expressão personalizada para definir o intervalo de datas:

* O dia em que o relatório (A partir de) é executado (ou as solicitações são atualizadas) determina quais dados estão disponíveis.
* A sobreposição das datas inicial e final do relatório afeta o intervalo de datas coberto pelo relatório.

Visto que a disponibilidade dos dados está sujeita tanto ao período do relatório quanto à data em que as solicitações no relatório são atualizadas, certifique-se de executar o relatório no dia apropriado para extrair as informações desejadas. Os exemplos abaixo demonstram essas duas considerações.

Suponha que você faça uma solicitação para [!UICONTROL Exibições de página] usando a granularidade agregada. Na América do Norte, a semana começa no domingo. Para obter relatórios atualizados referentes ao período de domingo a sábado (por exemplo, 23 de novembro a 29 de novembro de 2008), execute o relatório (solicitações de atualização) no domingo (30 de novembro) da semana anterior (23/11 a 29/11).

Use esta expressão personalizada:

*De:* cw-1w *A:* cw-1d

Uma análise da expressão de personalização quando a [!UICONTROL Data Final] inclusiva para a solicitação é 30/11:

*De:* cw-1w

o dia da semana atual começando no domingo, 30 de novembro menos sete dias = o dia da semana passada começando no domingo, 23 de novembro

*Para:* cw-1d

o dia da semana atual começando no domingo, 30 de novembro menos um dia = sábado, 29 de novembro

Depois que a expressão personalizada for mapeada para a planilha, atualize a solicitação usando domingo, 30 de novembro de 2008, como a [!UICONTROL Data final] inclusiva para a solicitação flutuante. Os dados refletirão o período de uma semana.

Se, em vez disso, você atualizar a expressão e especificar Sábado, 29 de novembro como a [!UICONTROL Data final] para a solicitação flutuante, os dados refletirão a semana de 16/11 a 22/11. Isso ocorre porque a data de referência para a atualização da solicitação é um dia anterior.

Estas são as diferenças quando a [!UICONTROL Data final] inclusiva da solicitação é 29/11:

*De:* cw-1w

o dia da semana atual começando no domingo, 23 de novembro menos sete dias = o dia da semana passada começando no domingo, 16 de novembro

*Para:* cw-1d

o dia da semana atual começando no domingo, 23 de novembro menos um dia = sábado, 22 de novembro

Na Europa e em alguns outros países, a semana começa na segunda-feira, e não no domingo. Nesse caso, você pode personalizar o calendário para alterar a data de início. (Consulte [Calendário personalizado](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md).)
