---
description: Conheça as perguntas frequentes do Report Builder.
title: Perguntas frequentes do Report Builder
feature: Report Builder
role: User, Admin
exl-id: 86604d39-2965-45a5-98ab-3ee4adcb7f97
source-git-commit: 83f199a3bb76147b98aba014b62ea3c02c766ddd
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 90%

---

# Perguntas frequentes sobre o Report Builder

Perguntas frequentes sobre o Report Builder.

## Posso usar a função `TODAY()` ou `DATERANGE()` em pastas de trabalho? {#today}

A função [`TODAY()`](https://support.microsoft.com/pt-BR/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9) no Excel retorna o dia atual. A função [`DATEVALUE()`](https://support.microsoft.com/pt-BR/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252) converte uma sequência de datas em um valor serial. Embora útil para muitos recursos do Excel, a Adobe não recomenda o uso dessas funções como parte das solicitações programadas do Report Builder. O Atendimento ao cliente da Adobe não oferece suporte a solicitações de solução de problemas que usam essas funções.

Os relatórios agendados são processados em servidores que provavelmente não compartilham fusos horários como o conjunto de relatórios. O `TODAY()` que um usuário espera e o `TODAY()` que o servidor de processamento usa geralmente podem ser diferentes. Além disso, a data usada se baseia no início do processamento. Se muitos relatórios forem executados simultaneamente, a data poderá ser alterada entre o momento em que é solicitada e o momento em que é processada devido a atrasos. Esse problema estará presente se a hora agendada estiver próxima à meia-noite.

Os relatórios agendados também são processados em servidores que provavelmente não compartilham a sintaxe de data. Por exemplo, `7/1/YYYY` pode se referir a 1º de julho ou 7 de janeiro, dependendo do país ou da região. Usar a função `DATEVALUE()` nessa data resultaria em valores seriais diferentes, dependendo do computador que a executa.

Como alternativa ao uso dessas funções do Excel, a Adobe recomenda usar intervalos de datas nas solicitações do Report Builder. Na primeira página do assistente de solicitações, selecione **[!UICONTROL Datas predefinidas]** no menu suspenso e, em Datas usadas com frequência, selecione **[!UICONTROL Hoje]** ou outro período desejado. Essa configuração utiliza a hora do conjunto de relatórios no momento em que ele foi executado, e não a hora do servidor que processa a solicitação.

## Qual é o tamanho e a complexidade das minhas pastas de trabalho? {#complexity}

O Report Builder aceita pastas de trabalho até os seguintes limites:

* **Mil solicitações**: uma única pasta de trabalho pode conter até mil solicitações de dados. Se você tem relatórios ou projetos que exigem mais de 1000 solicitações, a Adobe recomenda separá-las em várias pastas de trabalho.
* **Vinte mil solicitações por hora por empresa**: o Report Builder usa a API de relatórios do Analytics para recuperar dados. Cada solicitação individual usa uma chamada de API sempre que é criada ou atualizada. Se sua organização acumular mais de 20.000 chamadas de API em determinada hora, você deverá aguardar até a próxima hora para recuperar os dados novamente.
* **Tempo de processamento de 4 horas**: os relatórios programados expiram após o processamento por mais de 4 horas. Se sua pasta de trabalho contiver muitas solicitações complexas usando grandes conjuntos de dados, o relatório agendado poderá falhar.

## Como saber se tenho acesso ao Report Builder? {#access}

Você precisa receber acesso de Report Builder pelo administrador do Adobe Analytics. O administrador configura perfis de produto no [Adobe Admin Console](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-console/home). Solicite acesso ao seu administrador.
