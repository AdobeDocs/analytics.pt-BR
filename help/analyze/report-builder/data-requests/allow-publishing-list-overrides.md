---
description: Ao agendar um relatório, você pode escolher uma lista de publicação a ser usada para distribuição.
title: Permitir substituições da lista de publicação
topic: Report builder
uuid: f2cc9878-ab54-4c6f-8a88-3f3b579955e3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Permitir substituições da lista de publicação

Ao agendar um relatório, você pode escolher uma lista de publicação a ser usada para distribuição.

As listas de publicação são configuradas nas Ferramentas administrativas do Analytics.

Consulte [Publicação do Gerenciador](https://marketing.adobe.com/resources/help/pt_BR/reference/publishing_list.html) de Listas na Referência do Analytics.

Para ativar esse recurso, navegue até a [!UICONTROL Request Wizard: Step 1] janela.

If you enable [!UICONTROL Allow Publishing List Override], the report suite assigned to each recipient in the publishing list replaces the report suite for this request. Além disso, se a pasta de trabalho contiver vários conjuntos de relatórios, a ID do conjunto de relatórios associada à lista de publicação será usada.

Essa opção não está disponível para conjuntos de relatórios selecionados de células.

>[!NOTE] Se você enviar o relatório agendado para várias listas de publicação, o relatório será executado uma vez para cada lista. Conjuntos de relatórios variáveis são substituídos pelo conjunto de relatórios atribuído à lista de publicação.

