---
description: Quando você agenda um relatório, pode escolher uma lista de publicação para usar para distribuição.
title: Permitir substituições da lista de publicação
uuid: f2cc9878-ab54-4c6f-8a88-3f3b579955e3
feature: Report Builder
role: User, Admin
exl-id: a7bd6cdb-397a-45ba-88ff-c3b3c7062005
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 95%

---

# Permitir substituições da lista de publicação

Quando você agenda um relatório, pode escolher uma lista de publicação para usar para distribuição.

A publicação de listas é configurada nas ferramentas administrativas do Analytics.

Consulte [Publicação do gerenciador de lista](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/publishing-list.html) na referência do Analytics.

Para ativar esse recurso, navegue até a janela [!UICONTROL Assistente de solicitações: etapa 1].

Se você ativar [!UICONTROL Permitir substituições da lista de publicação], o conjunto de relatórios atribuído a cada destinatário na lista de publicação substituirá o conjunto de relatórios para esta solicitação. Além disso, se a pasta de trabalho contiver vários conjuntos de relatórios, a ID do conjunto de relatórios associada à lista de publicação será usada.

Esta opção não está disponível para conjuntos de relatórios selecionados a partir das células.

>[!NOTE]
>
>Se você enviar o relatório agendado para várias listas de publicação, o relatório será executado uma vez para cada lista. Conjuntos de relatórios variáveis são substituídos pelo conjunto de relatórios atribuído à lista de publicação.
