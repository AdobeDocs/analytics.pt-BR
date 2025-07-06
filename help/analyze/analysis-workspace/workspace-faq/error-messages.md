---
description: Saiba mais sobre erros e solução de problemas do Analysis Workspace.
title: Erros E Solução De Problemas
feature: Workspace Basics
role: User, Admin
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 98%

---

# Erros e solução de problemas

Ao interagir com o Analysis Workspace, você pode encontrar alguns erros que influenciam a funcionalidade ou o desempenho. A lista abaixo mostra os tipos de erro mais comuns, por que ocorrem e as otimizações que podem ser feitas.

## Mensagens de erro

Estas são algumas mensagens de erro comuns que você poderá ver ao usar o Analysis Workspace:

| Mensagem de erro | Por que o erro ocorre? | Otimização |
| --- | --- | --- |
| [!UICONTROL A visualização dos dados está apresentando um volume excessivo de relatórios. Tente novamente mais tarde.] | Sua organização está tentando executar muitas solicitações simultâneas em uma exibição de dados específica. Os fatores que contribuem para esse erro são solicitações de API, projetos agendados, relatórios agendados, alertas agendados e usuários simultâneos que criam solicitações de relatórios. | Distribua as solicitações e os cronogramas na exibição de dados de forma mais uniforme ao longo do dia.<p>Admins podem usar o [Gerenciador de atividades de relatórios para identificar e cancelar solicitações](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md) que estão consumindo a capacidade de gerar relatórios.</p> |
| [!UICONTROL Este relatório é complexo demais. Confira as práticas recomendadas para criar relatórios do Analysis Workspace.] | Sua solicitação de relatório é muito grande e não pode ser executada. Os fatores que contribuem para esse erro são o tempo limite devido à complexidade da solicitação. | Simplifique sua solicitação. Por exemplo, reduza o intervalo de datas, simplifique os critérios de segmento ou remova algumas colunas ou linhas da tabela. Considere também dividir a tabela em solicitações separadas. |
| [!UICONTROL A visualização de dados está excedendo sua capacidade de relatórios no momento. Simplifique a solicitação ou tente novamente mais tarde.] | Sua organização está tentando executar muitas solicitações simultâneas em uma exibição de dados específica. Os fatores que contribuem para esse erro são solicitações de API, projetos agendados e usuários simultâneos que criam solicitações de relatórios. | Distribua as solicitações e os cronogramas na exibição de dados de forma mais uniforme ao longo do dia. |
| [!UICONTROL Ocorreu um erro de sistema. Registre uma solicitação junto ao Atendimento ao cliente em **[!UICONTROL Ajuda > Enviar tíquete de suporte]** e inclua o código de erro.] | A Adobe está enfrentando um problema que precisa ser resolvido. | Envie o código de erro ao Atendimento ao cliente. |
| [!UICONTROL Erro 500: Falha ao carregar a página] | Problemas com a rede local, como [configurações de firewall](/help/technotes/ip-addresses.md) da empresa, contribuem para esse erro. Além disso, a Adobe pode estar enfrentando um problema que precisa ser resolvido. | Tente fazer logon novamente após alguns minutos. Se o problema persistir, envie o código de ID da instância do EIM para o Atendimento ao cliente. |
| [!UICONTROL Sua solicitação falhou como resultado de muitas colunas ou linhas pré-configuradas.] | Sua tabela tem muitas células de forma livre (linha * colunas). | Remova colunas ou linhas na tabela ou considere dividir a tabela em solicitações separadas. |


## Solução de problemas

Ao usar o Analysis Workspace, utilize as informações abaixo para solucionar alguns problemas comuns.

| Problema | Como solucionar problemas |
|---|---|
| Quando arrasto uma métrica, vejo a mensagem *Dados inválidos*. | Dados inválidos significa que a Adobe não pode retornar dados usando a combinação de dimensões e métricas usadas no relatório. Por exemplo, duas métricas empilhadas uma sobre a outra não podem retornar como dados, pois não há como exibir duas métricas desse modo. Em vez disso, coloque as métricas lado a lado. |
| Quando arrasto uma métrica, não vejo nenhum dado real, apenas zeros. | Se você criar um relatório do espaço de trabalho com êxito, mas não houver dados, tente realizar as seguintes verificações:<ul><li>Se você aplicar um segmento no seu relatório, os critérios do segmento podem não corresponder a nenhum dado. Tente remover o segmento ou ajustar a definição do segmento.</li><li>Verifique o intervalo de datas no canto superior direito e verifique se ele está definido conforme o esperado.</li><li>Acesse seu site e use o [Depurador](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=pt-BR) para verificar se os dados estão sendo coletados.</li></ul> |



<!--
# Common error messages

You may encounter errors when interacting with Analysis Workspace that will also influence performance. Listed below are the most common error types, why they occur, and optimizations that can be made.

| Error message | Why does this occur? | Optimization |
| --- | --- | --- |
| [!UICONTROL The report suite is experiencing unusually heavy reporting. Please try again later.] | Your organization is trying to run too many concurrent requests against a specific report suite. Contributors to this error are API requests, scheduled projects, and concurrent users making reporting requests. | Spread your requests and schedules for the report suite more evenly throughout the day. <p>Administrators can use the [Reporting Activity Manager to identify and cancel requests](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md) that are consuming reporting capacity. |
| [!UICONTROL The report suite is currently exceeding its reporting capacity. Please simplify the request or try again later.] |  Your organization is trying to run too many concurrent requests against a specific report suite. Contributors to this error are API requests, scheduled projects, scheduled reports, scheduled alerts, and concurrent users making reporting requests. | Spread your requests and schedules for the report suite more evenly throughout the day. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.] | Adobe is experiencing an issue that needs to be resolved. | Submit the error code to Customer Care. |
| [!UICONTROL An unexpected error has occurred; try refreshing your project again. If the problem persists, please submit this error ID to Adobe Customer Care for further diagnosis.] | Adobe is experiencing an issue that needs to be resolved. | Try refreshing your project and if the problem persists, submit the error code to Customer Care. |
| [!UICONTROL Error 500: Failed to load page] | Issues with your local network, such as company [firewall settings](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html), are a contributing factor to this error. Additionally, Adobe may be experiencing an issue that needs to be resolved. | Try logging in again after several minutes. If the issue persists, submit the EIM instance ID code to Customer Care. |
| [!UICONTROL One of the segments or the search in this visualization contains a text search that returned too many results.] | Your segment criteria or report filter is too broad. | Narrow your search text criteria and try the request again. |
| [!UICONTROL This dimension does not currently support non-default attribution models.] | Non-default attribution is not supported for the dimension that you are using. | Replace the dimension in your table with one that is compatible with [Attribution](/help/analyze/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | Your table has too many freeform cells (row * columns). | Remove columns or rows in your table, or consider splitting the table into separate requests. |
-->