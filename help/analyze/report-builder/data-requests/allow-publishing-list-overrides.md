---
description: Quando você agenda um relatório, pode escolher uma lista de publicação para usar para distribuição.
title: Permitir substituições da lista de publicação
topic: Report builder
uuid: f2cc9878-ab54-4c6f-8a88-3f3b579955e3
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Permitir substituições da lista de publicação

Quando você agenda um relatório, pode escolher uma lista de publicação para usar para distribuição.

A publicação de listas é configurada nas ferramentas administrativas do Analytics.

Consulte [Publicação do gerenciador de lista](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/publishing-list.html) na referência do Analytics.

Para ativar esse recurso, navegue até a [!UICONTROL Request Wizard: Step 1] janela.

If you enable [!UICONTROL Allow Publishing List Override], the report suite assigned to each recipient in the publishing list replaces the report suite for this request. Além disso, se a pasta de trabalho contiver vários conjuntos de relatórios, a ID do conjunto de relatórios associada à lista de publicação será usada.

Esta opção não está disponível para conjuntos de relatórios selecionados a partir das células.

>[!NOTE] Se você enviar o relatório agendado para várias listas de publicação, o relatório será executado uma vez para cada lista. Conjuntos de relatórios variáveis são substituídos pelo conjunto de relatórios atribuído à lista de publicação.

