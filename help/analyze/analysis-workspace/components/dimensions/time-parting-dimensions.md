---
description: Saiba mais sobre como as dimensões de separação de tempo capturam o carimbo de data e hora de eventos coletados e os dividem em dimensões mais significativas, como Hora do dia ou Dia da semana.
title: Dimensões de separação de tempo
feature: Dimensions
role: User, Admin
exl-id: 92fbcc1e-1f7f-405a-8ad1-199fb7ba505e
TQID: https://experienceleague.adobe.com/bQVBmv3KhaDZtmUXSOY3UsustpCZKAwJ8rH9Qv49Rfw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 266
ht-degree: 33%

---

# Dimensões de separação de tempo

A divisão de tempo coleta o carimbo de data e hora de ocorrências coletadas e o divide em dimensões mais significativas, como **Hora do dia** ou **Dia da semana**.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimensões de separação de tempo](https://experienceleague.adobe.com/pt-br/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/time-parting-dimensions-in-analysis-workspace){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


As dimensões de separação de tempo são baseadas no fuso horário do conjunto de relatórios ou do conjunto de relatórios virtual. Essas dimensões estão disponíveis no Analysis Workspace e podem ajudar nas seguintes questões:

* Em um intervalo de datas grande, qual é a hora do dia mais popular para os visitantes acessarem meu site ou aplicativo?
* Existem dias da semana, ou horas do dia, em que a conversão é maior em meu site ou aplicativo?
* Como comparar minhas vendas de fim de semana com minhas vendas de dias da semana?
* Uma determinada campanha de marketing gera conversões mais altas de manhã ou à tarde?

>[!NOTE]
>
>As dimensões de separação de tempo só estão disponíveis no Analysis Workspace. Para usar dimensões de separação de tempo em outras soluções do Analysis Workspace, é possível implementar o [plug-in getTimeParting](/help/implement/vars/plugins/gettimeparting.md).

As dimensões de separação de tempo no Analysis Workspace incluem:

| Dimensão | Valores de exemplo |
| --- | --- |
| Hora do dia | 0-23 |
| AM/PM | AM, PM |
| Dia da semana | Segunda-feira, terça-feira, quarta-feira, quinta-feira, sexta-feira, sábado, domingo |
| Final de semana/Dia de semana | Final de semana, Dia de semana |
| Dia do mês | 1-31 |
| Mês do ano | Janeiro-dezembro |
| Dia do ano | 1-366 |
| Trimestre do ano | T1, T2, T3, T4 |
