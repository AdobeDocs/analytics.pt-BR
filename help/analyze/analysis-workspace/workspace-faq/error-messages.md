---
description: Lista de mensagens de erro do Adobe Analysis Workspace e dos componentes relacionados
title: Mensagens de erro comuns no Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
source-git-commit: e7e03531454bd56ebe6152edc08765f42ebec728
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 92%

---

# Mensagens de erro comuns

Você pode encontrar erros ao interagir com o Analysis Workspace que também influenciarão o desempenho. Os tipos de erro mais comuns, por que ocorrem e as otimizações que podem ser feitas estão listados abaixo.

| Mensagem de erro | Por que isso ocorre? | Otimização |
| --- | --- | --- |
| [!UICONTROL O conjunto de relatórios está apresentando um volume excessivo de relatórios. Tente novamente mais tarde.] | Sua organização está tentando executar muitas solicitações simultâneas em relação a um conjunto de relatórios específico. Os fatores que contribuem para esse erro são solicitações de API, projetos agendados e usuários simultâneos que fazem solicitações de relatórios. | Espalhe suas solicitações e agendamentos no conjunto de relatórios de forma mais uniforme ao longo do dia. <p>Os administradores podem usar o [Gerenciador de Atividades de Relatórios para identificar e cancelar solicitações](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md) que estão consumindo a capacidade de gerar relatórios. |
| [!UICONTROL O conjunto de relatórios está excedendo sua capacidade de gerar relatórios no momento. Simplifique a solicitação ou tente novamente mais tarde.] | Sua organização está tentando executar muitas solicitações simultâneas em relação a um conjunto de relatórios específico. Os fatores que contribuem para esse erro são solicitações de API, projetos agendados, relatórios agendados, alertas agendados e usuários simultâneos que fazem solicitações de relatórios. | Espalhe suas solicitações e agendamentos no conjunto de relatórios de forma mais uniforme ao longo do dia. |
| [!UICONTROL Ocorreu um erro de sistema. Registre uma solicitação ao Atendimento ao cliente em Ajuda > Enviar tíquete de suporte e inclua o código de erro.] | A Adobe está enfrentando um problema que precisa ser resolvido. | Envie o código de erro ao Atendimento ao cliente. |
| [!UICONTROL Ocorreu um erro inesperado; tente atualizar o projeto novamente. Se o problema persistir, envie essa ID de erro ao Atendimento ao cliente da Adobe para diagnóstico adicional.] | A Adobe está enfrentando um problema que precisa ser resolvido. | Tente atualizar o projeto e, se o problema persistir, envie o código de erro para o Atendimento ao cliente. |
| [!UICONTROL Erro 500: Falha ao carregar a página] | Problemas com a rede local, como [configurações de firewall](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=pt-BR) da empresa, contribuem para esse erro. Além disso, a Adobe pode estar enfrentando um problema que precisa ser resolvido. | Tente fazer logon novamente após alguns minutos. Se o problema persistir, envie o código de ID da instância do EIM para o Atendimento ao cliente. |
| [!UICONTROL Um dos segmentos ou a pesquisa nesta visualização contém uma pesquisa de texto que retornou muitos resultados.] | O critério do segmento ou o filtro de relatório é muito amplo. | Restrinja os critérios de texto de pesquisa e tente a solicitação novamente. |
| [!UICONTROL No momento, esta dimensão não oferece suporte a modelos de atribuição não-padrão.] | A dimensão que você está usando não possui suporte para atribuição não-padrão. | Substitua a dimensão na tabela por uma que seja compatível com [Atribuição](/help/analyze/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Sua solicitação falhou como resultado de muitas colunas ou linhas pré-configuradas.] | Sua tabela tem muitas células de forma livre (linha * colunas). | Remova colunas ou linhas na tabela ou considere dividir a tabela em solicitações separadas. |
