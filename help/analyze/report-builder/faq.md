---
title: Perguntas frequentes sobre o Report Builder
description: Perguntas frequentes sobre o Report Builder.
feature: Report Builder
role: Profissional de negócios, Administrador
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 1%

---


# Perguntas frequentes sobre o Report Builder

Perguntas frequentes sobre o Report Builder.

## Posso usar a função `TODAY()` ou `DATERANGE()` em pastas de trabalho?

A função [`TODAY()`](https://support.microsoft.com/en-us/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9) no Excel retorna o dia atual. A função [`DATEVALUE()`](https://support.microsoft.com/en-us/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252) converte uma string de data em um valor serial. Embora seja útil para muitos recursos no Excel, o Adobe recomenda não usar essas funções como parte das solicitações agendadas para o Report Builder. O Atendimento ao cliente do Adobe não oferece suporte a solicitações de solução de problemas que usam qualquer uma dessas funções.

Os relatórios agendados são processados em servidores que provavelmente não compartilham fusos horários como o conjunto de relatórios. O `TODAY()` que um usuário espera e o `TODAY()` que o servidor de processamento usa geralmente podem ser diferentes. Além disso, a data usada é baseada no início do processamento. Se muitos relatórios forem executados simultaneamente, a data poderá ser alterada entre o momento em que é solicitada e o momento em que é processada devido a atrasos. Esse problema está presente se a hora agendada estiver próxima à meia-noite.

Os relatórios agendados também são processados em servidores que provavelmente não compartilham a sintaxe de data. Por exemplo, `7/1/YYYY` pode se referir a 1º de julho ou 7 de janeiro, dependendo do seu país ou região. Usar a função `DATEVALUE()` nessa data resultaria em valores seriais diferentes, dependendo do computador que a executa.

Como alternativa ao uso dessas funções do Excel, o Adobe recomenda usar intervalos de datas nas solicitações de Report Builder. Na primeira página do assistente de solicitações, selecione **[!UICONTROL Datas predefinidas]** na lista suspensa e, em Datas usadas mais comuns, selecione **[!UICONTROL Hoje]** ou outro intervalo de datas desejado. Essa configuração utiliza o tempo do conjunto de relatórios no momento em que ele foi executado, e não o momento do servidor que processa a solicitação.

## Qual é o tamanho e complexidade de minhas pastas de trabalho?

O Report Builder suporta pastas de trabalho até os seguintes limites:

* **1000 pedidos**: Uma pasta de trabalho pode conter até 1000 solicitações de dados em uma única pasta de trabalho. Se você tiver relatórios ou projetos que exigem mais de 1000 solicitações, o Adobe recomenda separá-las em várias pastas de trabalho.
* **20 mil solicitações por hora por empresa**: O Report Builder usa a API de relatórios do Analytics para recuperar dados. Cada solicitação individual usa uma chamada de API sempre que é criada ou atualizada. Se sua organização acumular mais de 20.000 chamadas de API em uma determinada hora, você deverá aguardar até a próxima hora para recuperar os dados novamente.
* **Tempo** de processamento de 4 horas: O tempo limite dos relatórios agendados expira após o processamento das últimas 4 horas. Se sua pasta de trabalho contiver muitas solicitações complexas usando grandes conjuntos de dados, o relatório agendado poderá falhar.
