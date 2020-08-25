---
title: Perguntas frequentes sobre o Report Builder
description: Perguntas frequentes sobre Report Builder.
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---


# Perguntas frequentes sobre o Report Builder

Perguntas frequentes sobre Report Builder.

## Posso usar a função `TODAY()` ou `DATERANGE()` nas pastas de trabalho?

A [`TODAY()` função](https://support.microsoft.com/en-us/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9) no Excel retorna o dia atual. A [`DATEVALUE()` função](https://support.microsoft.com/en-us/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252) converte uma string de data em um valor serial. Embora útil para muitos recursos no Excel, o Adobe recomenda não usar essas funções como parte das solicitações programadas para Report Builder. O Atendimento ao cliente do Adobe não oferece suporte para solicitações de solução de problemas que usam qualquer uma dessas funções.

Os relatórios agendados são processados em servidores que provavelmente não compartilham fusos horários como o conjunto de relatórios. O `TODAY()` que um usuário espera e `TODAY()` o servidor de processamento usa com frequência pode ser diferente. Além disso, a data usada é baseada no processamento de start. Se muitos relatórios forem executados simultaneamente, a data pode ser alterada entre o momento em que é solicitada e o momento em que o processamento é start devido a atrasos. Esse problema estará presente se a hora agendada estiver próxima à meia-noite.

Os relatórios agendados também são processados em servidores que provavelmente não compartilham a sintaxe de data. Por exemplo, `7/1/YYYY` pode se referir a 1º de julho ou 7 de janeiro, dependendo do seu país ou região. O uso da `DATEVALUE()` função nessa data resultaria em diferentes valores de série, dependendo do computador que a executa.

Como alternativa ao uso dessas funções do Excel, o Adobe recomenda o uso de intervalos de datas em solicitações de Report Builder. Na primeira página do assistente de solicitações, selecione Datas **** predefinidas na lista suspensa e, em Datas usadas frequentemente, selecione **[!UICONTROL Hoje]** ou outro intervalo de datas desejado. Essa configuração leva o tempo do conjunto de relatórios no momento em que foi executado, e não o momento em que o servidor processa a solicitação.

## Quão grande e complexo posso fazer minhas pastas de trabalho?

O Report Builder suporta pastas de trabalho até os seguintes limites:

* **1000 solicitações**: Uma pasta de trabalho pode conter até 1000 solicitações de dados em uma única pasta de trabalho. Se você tiver relatórios ou projetos que exijam mais de 1000 solicitações, o Adobe recomenda separá-las em várias pastas de trabalho.
* **20 mil solicitações por hora por empresa**: O Report Builder usa a API de relatórios do Analytics para recuperar dados. Cada solicitação individual usa uma chamada de API sempre que é criada ou atualizada. Se sua organização acumular mais de 20.000 chamadas de API em uma determinada hora, você deve aguardar até a próxima hora para recuperar os dados novamente.
* **Tempo** de processamento de 4 horas: O tempo limite dos relatórios agendados é atingido após o processamento, passadas 4 horas. Se a sua pasta de trabalho contiver muitas solicitações complexas usando grandes conjuntos de dados, o relatório programado poderá falhar.
