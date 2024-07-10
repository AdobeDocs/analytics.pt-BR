---
description: Gerenciar usuários do Analytics e seus ativos na Adobe Admin Console.
title: Gerenciar usuários e ativos do Analytics
feature: Admin Tools
exl-id: 849a8279-4850-4458-bdd2-85052a17ee21
role: Admin
source-git-commit: 869b44b826de5cb35d13000133092397cb16ccaa
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 2%

---

# Gerenciar contas de usuário, ativos e expirações herdadas

Você pode gerenciar contas de usuário herdadas, o status da migração, os dados de expiração, a transferência de ativos para outros usuários e muito mais usando o **[!UICONTROL Admin] > [!UICONTROL Todos os administradores] >  [!UICONTROL Usuários e administrador do Analytics]**.

A tela Usuários mostra uma lista de usuários atuais do Adobe Analytics, com as seguintes colunas:

| Coluna | Descrição |
|---|---|
| [!UICONTROL ID de usuário] | A ID de usuário que o usuário usa para fazer logon no Adobe Analytics. |
| [!UICONTROL Nome] | O nome do usuário. |
| [!UICONTROL Status da migração] | O status da migração de uma conta de usuário herdada para um Enterprise ID ou Adobe ID.  O status pode ser Não iniciado, Em fila ou Migrado. |
| [!UICONTROL Email] | O email do usuário. |
| [!UICONTROL Logon herdado] | O status do logon antigo, que pode ser Ativado ou Desativado. |
| [!UICONTROL Data de criação] | Carimbo de data e hora quando a conta de usuário foi criada no Adobe Analytics. |
| [!UICONTROL Último acesso ao Analytics] | Carimbo de data e hora do acesso mais recente da conta de usuário ao Adobe Analytics, |
| [!UICONTROL Expiração] | Data de expiração da conta de usuário ou Nenhum se a conta de usuário não estiver expirando. |

![Usuários](assets/users.png)

- Para procurar um usuário específico, use o ![Pesquisar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) *Pesquisar por título* campo.
- Para filtrar a lista no status da migração, selecione ![Divisa](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL Status da migração]**.
- Para filtrar a lista no status de logon herdado, selecione ![Divisa](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL Logon herdado]**.
- Para alterar a exibição de colunas, selecione ![Configurações de coluna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) e selecione as colunas na janela pop-up.

É possível aplicar várias ações ao selecionar um ou mais usuários na lista:

| Ação | Descrição |
|---|---|
| ![Migrar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Briefcase_18_N.svg) **[!UICONTROL Migrar]** | Você pode migrar um ou mais usuários para Enterprise IDs ou Adobe IDs. |
| ![Calendário bloqueado](https://spectrum.adobe.com/static/icons/workflow_18/Smock_CalendarLocked_18_N.svg) **[!UICONTROL Definir expiração]** | É possível definir uma data de expiração para usar o logon herdado do Adobe Analytics para os usuários selecionados.  Selecione a data para usar um pop-up de calendário para especificar a data. Selecionar **[!UICONTROL Concluído]** para confirmar a expiração. |
| ![Transferir ativos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Switch_18_N.svg) **[!UICONTROL Transferir ativos]** | Esta ação só está disponível ao selecionar um usuário. Se o usuário tiver ativos que podem ser transferidos, é possível selecionar os itens da conta (como marcadores, painéis e muito mais). Selecionar **[!UICONTROL Transferir]** para concluir a transferência.<br/>![Transfere ativos](assets/transfer-assets.png) |
| ![Excluir contas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Excluir contas]** | Uma caixa de diálogo é exibida para confirmar a exclusão das contas selecionadas. Selecionar **[!UICONTROL OK]** para excluir as contas. Selecionar **[!UICONTROL Cancelar]** para cancelar. |
| ![Exportar para CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) **[!UICONTROL Exportar para CSV]** | Essa ação baixa imediatamente um arquivo contendo uma lista de valores separados por vírgulas dos usuários selecionados com seus detalhes (nome, status de migração, email e muito mais). |

