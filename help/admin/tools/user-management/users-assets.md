---
description: Gerenciar usuários do Analytics e seus ativos na Adobe Admin Console.
title: Gerenciar usuários e ativos do Analytics
feature: Admin Tools
exl-id: 849a8279-4850-4458-bdd2-85052a17ee21
role: Admin
TQID: 'https://experienceleague.adobe.com/d8CK9Vf-eaEU6P9386J1eO-JpD5u4l3VoqRcMwvXcW0'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: f73667dc-d296-4875-8975-ac3fdc3adc42id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: d124af73-4061-4b84-9063-ae2b60f2c1f3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 455
ht-degree: 9%

---

# Gerenciar contas de usuário, ativos e expirações herdadas

É possível gerenciar contas de usuário herdadas, o status da migração, os dados de expiração, a transferência de ativos para outros usuários e muito mais, usando **[!UICONTROL Administrador] > [!UICONTROL Todos os administradores] > [!UICONTROL Usuários e administradores do Analytics]**.

A tela Usuários mostra uma lista de usuários atuais do Adobe Analytics, com as seguintes colunas:

| Coluna | Descrição |
|---|---|
| [!UICONTROL ID de usuário] | A ID de usuário que o usuário usa para fazer logon no Adobe Analytics. |
| [!UICONTROL Nome] | O nome do usuário. |
| [!UICONTROL Status da migração] | O status da migração de uma conta de usuário herdada para uma Enterprise ID ou Adobe ID.  O status pode ser Não iniciado, Em fila ou Migrado. |
| [!UICONTROL Email] | O email do usuário. |
| [!UICONTROL Logon herdado] | O status do logon antigo, que pode ser Ativado ou Desativado. |
| [!UICONTROL Data de criação] | Carimbo de data e hora quando a conta de usuário foi criada no Adobe Analytics. |
| [!UICONTROL Último acesso ao Analytics] | Carimbo de data e hora do acesso mais recente da conta de usuário ao Adobe Analytics, |
| [!UICONTROL Expiração] | Data de expiração da conta de usuário ou Nenhum se a conta de usuário não estiver expirando. |

![Usuários](assets/users.png)

- Para procurar um usuário específico, use o campo ![Pesquisar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) *Pesquisar por título*.
- Para filtrar a lista no status da migração, selecione ![Divisa](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL Status da migração]**.
- Para filtrar a lista de status de logon herdado, selecione ![Divisa](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL Logon herdado]**.
- Para alterar a exibição das colunas, selecione ![Configurações de coluna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) e selecione as colunas na janela pop-up.

É possível aplicar várias ações ao selecionar um ou mais usuários na lista:

| Ação | Descrição |
|---|---|
| ![Migrar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Briefcase_18_N.svg) **[!UICONTROL Migrar]** | Você pode migrar um ou mais usuários para Enterprise ID ou Adobe IDs. |
| ![Calendário bloqueado](https://spectrum.adobe.com/static/icons/workflow_18/Smock_CalendarLocked_18_N.svg) **[!UICONTROL Definir expiração]** | É possível definir uma data de expiração para usar o logon herdado do Adobe Analytics para os usuários selecionados.  Selecione a data para usar um pop-up de calendário para especificar a data. Selecione **[!UICONTROL Concluído]** para confirmar a expiração. |
| ![Transferir ativos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Switch_18_N.svg) **[!UICONTROL Transferir ativos]** | Esta ação só está disponível ao selecionar um usuário. Se o usuário tiver ativos que podem ser transferidos, é possível selecionar os itens da conta (como marcadores, painéis e muito mais). Selecione **[!UICONTROL Transferir]** para concluir a transferência.<br/>![Transfere ativos](assets/transfer-assets.png) |
| ![Excluir contas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Excluir contas]** | Uma caixa de diálogo é exibida para confirmar a exclusão das contas selecionadas. Selecione **[!UICONTROL OK]** para excluir as contas. Selecione **[!UICONTROL Cancelar]** para cancelar. |
| ![Exportar para CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) **[!UICONTROL Exportar para CSV]** | Essa ação baixa imediatamente um arquivo contendo uma lista de valores separados por vírgulas dos usuários selecionados com seus detalhes (nome, status de migração, email e muito mais). |

