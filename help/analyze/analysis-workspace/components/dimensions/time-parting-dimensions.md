---
description: Saiba mais sobre como as dimensões de separação de tempo capturam o carimbo de data e hora de eventos coletados e os dividem em dimensões mais significativas, como Hora do dia ou Dia da semana.
title: Dimensões de separação de tempo
feature: Dimensions
role: User, Admin
exl-id: 92fbcc1e-1f7f-405a-8ad1-199fb7ba505e
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 74%

---

# Dimensões de separação de tempo

A divisão de tempo coleta o carimbo de data e hora de ocorrências coletadas e o divide em dimensões mais significativas, como **Hora do dia** ou **Dia da semana**.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimensões de separação de tempo](https://video.tv.adobe.com/v/23727?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


As dimensões de separação de tempo são baseadas no fuso horário do conjunto de relatórios ou do conjunto de relatórios virtual. Essas dimensões estão disponíveis no Analysis Workspace e podem ajudar nas seguintes questões:

* Em um intervalo de dados grande, qual é o horário de mais acessos de visitantes ao meu site ou aplicativo?
* Há dias da semana ou horas do dia nas quais a conversão é mais alta no meu site ou aplicativo?
* Como minhas vendas de fim de semana se comparam com as da semana?
* Determinada campanha de marketing gera conversões maiores pela manhã ou à tarde?

>[!NOTE]
>
>As dimensões de separação de tempo só estão disponíveis no Analysis Workspace. Para usar dimensões de separação de tempo em outras soluções do Analysis Workspace, é possível implementar o [plug-in getTimeParting](/help/implement/vars/plugins/gettimeparting.md).

As dimensões de separação de tempo no Analysis Workspace incluem:

| Dimensão | Valores de exemplo |
| --- | --- |
| Hora do dia | 0-23 |
| AM/PM | AM, PM |
| Dia da semana | Segunda-feira, terça-feira, quarta-feira, quinta-feira, sexta-feira, sábado, domingo |
| Final de semana/Dia da semana | Final de semana, Dia da semana |
| Dia do mês | 1-31 |
| Mês do ano | Janeiro - Dezembro |
| Dia do ano | 1-366 |
| Trimestre do ano | T1, T2, T3, T4 |
