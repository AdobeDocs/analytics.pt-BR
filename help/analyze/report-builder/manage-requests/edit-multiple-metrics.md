---
description: Saiba como adicionar, remover ou substituir métricas em uma solicitação preexistente ou em um grupo de solicitações.
title: Como editar métricas em várias solicitações
feature: Report Builder
role: User, Admin
exl-id: e537b67a-aa07-4acd-a476-7497426e2f7d
source-git-commit: 66b7de0b008364e47253d319785c204ca479ab26
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 31%

---

# Editar métricas em várias solicitações

Adicionar, remover ou substituir métricas em uma solicitação pré-existente ou em um grupo de solicitações.

## Adicionar métricas {#section_3FBDA9668039404895059618D70FCBCD}

Ao adicionar métricas, considere as seguintes diretrizes:

* Métricas podem ser adicionadas somente a solicitações de Layout dinâmico.
Se algumas das solicitações selecionadas forem Layouts personalizados, as métricas não serão adicionadas. Se o layout for personalizado, o Report Builder não saberá onde colocar a nova métrica na planilha.
* Se você selecionar somente solicitações de Layout personalizado, a variável **[!UICONTROL Adicionar métricas]** opção não está disponível.
* A adição de métricas aumenta o tamanho de uma solicitação e pode fazer com que seja sobreposta a outra solicitação. Verifique se a solicitação tem espaço suficiente para adicionar métricas.
* Se a métrica adicionada já estiver presente em uma das solicitações selecionadas, ela não será adicionada a essa solicitação.

Para adicionar uma ou mais métricas

1. Selecione uma ou mais solicitações no Excel e clique com o botão direito do mouse para selecionar **[!UICONTROL Editar métricas]**. (Ou clique em **[!UICONTROL Gerenciar]** > **[!UICONTROL Editar várias]** > `<choose metric>` > **[!UICONTROL Editar grupo]** para selecionar o grupo de solicitações a serem modificadas.)
1. Selecione **[!UICONTROL Adicionar métricas]** e selecione as métricas a serem adicionadas.

   ![Captura de tela mostrando a opção Editar solicitação, Adicionar métricas selecionada.](assets/add_metric.png)

1. Atualize a solicitação para ver os dados reais. Os dados offline serão exibidos até você atualizar os dados.

## Substituir métricas

Ao substituir métricas, considere as seguintes diretrizes:

* Somente substituições 1:1 são permitidas. 1:muitos ou muitos:1 não são permitidos.
* Se a métrica selecionada não estiver presente em uma das solicitações selecionadas, a solicitação será deixada inalterada.
* A nova métrica é colocada no mesmo local que a métrica substituída.

   * **Em um Layout Dinâmico**, se uma solicitação de layout dinâmico apresentar data, visita, visitantes, dados únicos diários e *visitantes* é substituída por *receita*, o layout de solicitação atualizado será: data, visita, receita e único diário.
   * **Em um layout personalizado**, se a variável *visitantes* métrica foi gerada na célula F11, o layout da solicitação atualizado mostrará *receita* na mesma célula F11.

* Se a métrica substituída tiver uma operação aplicada (média, texto pré-pendente, texto pós-pendente, micrográfico), essas operações também serão aplicadas à nova métrica.

Para substituir uma métrica

1. Selecione uma ou mais solicitações no Excel e clique com o botão direito do mouse para selecionar **[!UICONTROL Editar métricas]**. Como alternativa, você pode clicar em **[!UICONTROL Gerenciar]** > **[!UICONTROL Editar vários]** > **`<choose metric>`** > **[!UICONTROL Editar grupo]** para selecionar o grupo de solicitações a serem modificadas.

1. Selecione **[!UICONTROL Substituir métrica]**.

   ![Captura de tela da tela Editar grupo com a opção Substituir métrica selecionada.](assets/replace_metric.png)

1. Selecione a métrica que deseja substituir e a métrica de substituição.
1. Atualize a solicitação. Os dados offline serão exibidos até você atualizar os dados.

## Remover métricas {#section_D3CD5BAC7670416593B633B2B8423C60}

Ao remover métricas, considere as seguintes diretrizes:

* Se alguma das métricas selecionadas para remoção não estiver presente em uma das solicitações selecionadas, a solicitação será deixada inalterada.
* Em um layout de tabela dinâmica, a remoção de uma métrica faz com que o layout mude para métricas localizadas após a métrica removida. Por exemplo, se uma solicitação de layout de tabela dinâmica gerar datas, visitas, visitantes e dados exclusivos diários e você remover *visitas*, o layout atualizado da solicitação mostrará: data, visitantes e número único diário.

Para remover métricas

1. Selecione uma ou mais solicitações no Excel e clique com o botão direito do mouse para selecionar **[!UICONTROL Editar métricas]**. Como alternativa, clique em **[!UICONTROL Gerenciar]** > **[!UICONTROL Editar vários]** > **`<choose metric>`** > **[!UICONTROL Editar grupo]** para selecionar o grupo de solicitações a serem modificadas.

1. Selecione **[!UICONTROL Remover métrica(s)]**.

   ![Captura de tela mostrando a opção Editar grupo e Remover métricas selecionada.](assets/remove_metric.png)

1. Selecione uma ou mais métricas para remover da solicitação.
1. Atualize a solicitação. Serão exibidos dados offline até que você atualize.
