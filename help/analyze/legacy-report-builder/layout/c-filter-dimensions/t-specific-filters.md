---
description: Filtros que aplicam termos de dimensões específicos.
title: Filtros específicos
uuid: b3a8187a-3d59-4da0-abca-e933664332e3
feature: Report Builder
role: User, Admin
exl-id: e5f2d67c-3add-4d51-8a76-ee3b2a6eef94
TQID: https://experienceleague.adobe.com/yNIeTJwwWtjXkbi47lX1Ve-Rbz6lF1PazD4YxxXa0Ac
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 336
ht-degree: 57%

---

# Filtros específicos

{{legacy-arb}}

Filtros que aplicam termos de dimensões específicos.

Você pode pesquisar por itens de dimensão específicos criando um filtro que corresponda a critérios exatos. Por exemplo, você pode criar o seguinte tipo de filtro: página em [!DNL homepage.htm], [!DNL contact_us.html], [!DNL corporate_info.html].

**Para criar um filtro Específico**

1. Crie ou edite uma solicitação e então acesse o [!UICONTROL Assistente de solicitações: etapa 2].

   ![Captura de tela mostrando o Filtro por opções: Aplicativo, Usuário e Projeto.](/help/admin/tools/assets/filter.png)

1. No [!UICONTROL Assistente de solicitações: etapa 2], clique no link ao lado da dimensão na grade e, em seguida, escolha **[!UICONTROL Filtro]**.

1. Habilitar **[!UICONTROL Específico]**.

   ![Captura de tela da caixa de diálogo Escolher Página com a opção Específica selecionada.](assets/choose_page_specific01.png)

1. Ative uma das seguintes opções Específicas:

   * **De Intervalo de Células:** Permite selecionar dados de células. Você pode selecionar:
      * **Todas as células do intervalo:** Permite mapear cada célula para o intervalo. Texto descritivo explica quantos grupos de células precisam ser selecionados. Para mapear mais de um grupo de células, pressione a tecla ctrl enquanto faz as seleções sucessivas. Se o intervalo que deve ser mapeado contiver apenas uma célula, esta será a única opção disponível
      * **Primeira Célula do Intervalo:** Você só precisa selecionar a célula superior esquerda do intervalo e escolher uma direção para os dados. Além disso, se a solicitação tiver vários períodos, você escolhe a direção dos períodos e escolhe se deseja ignorar um número definido de células entre períodos.
   * **Da Lista:** Permite selecionar dados de uma lista à qual você pode adicionar dados.
1. Se você habilitar **[!UICONTROL A partir da lista]**, selecione quaisquer itens listados disponíveis ou clique em **[!UICONTROL Adicionar]**.

   Ao clicar em **[!UICONTROL Adicionar]**, o formulário [!UICONTROL Selecionar a partir da lista] exibe uma lista de itens de dimensão disponíveis para o intervalo de dados da solicitação atual, limitado aos primeiros 10.000 itens. Você pode pesquisar nesses itens ou clicar em **[!UICONTROL Mais...]** para exibir o [!UICONTROL Formulário Pesquisar], que permite criar uma pesquisa mais detalhada das dimensões.
1. Em [!UICONTROL Selecionar da lista], clique em **[!UICONTROL OK]**.
1. No formulário [!UICONTROL Escolher página], salve seu filtro Específico se desejar e, em seguida, clique em **[!UICONTROL OK]**.
