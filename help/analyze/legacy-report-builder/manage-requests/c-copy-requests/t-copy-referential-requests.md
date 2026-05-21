---
description: Saiba como copiar solicitações referenciais.
title: Como copiar solicitações referenciais
feature: Report Builder
role: User, Admin
exl-id: 3cd77325-7461-4345-a672-64c03ea1ae5b
TQID: https://experienceleague.adobe.com/A-ef3rd0b7WMBRqBgmxFWpa35x8R7qYF1dMkF5gx5Ec
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 533
ht-degree: 40%

---

# Copiar solicitações referenciais

{{legacy-arb}}

Uma solicitação referencial usa valores de células como entrada para parâmetros, como um filtro de datas ou relacional.

Para propagar ou copiar e colar solicitações referenciais na planilha:

* Você deve criar pelo menos uma solicitação válida na planilha.

* Os dados produzidos pela solicitação devem conter uma célula cujo valor depende de uma solicitação em outra célula (usando um filtro de detalhamento ou correspondência) ou dependente de um filtro que recebe entrada de dados inseridos em uma célula.

Também é possível criar solicitações que fazem referência a filtros de entrada a partir de solicitações em diferentes planilhas, mas não em pastas de trabalho diferentes. Por exemplo, uma solicitação na Planilha 2 pode usar um conjunto de relatórios de uma determinada célula na Planilha 1 e um intervalo de datas de uma célula em uma solicitação na Planilha 2. A nova saída pode ser colocada em uma planilha ou em uma nova planilha na mesma pasta de trabalho. Quando você cola uma solicitação relativa, se um filtro de entrada reside em uma planilha diferente da planilha na qual a saída da solicitação copiada está localizada, o filtro é colado como um filtro absoluto.

>[!NOTE]
>
>Não é possível fazer a saída de uma única solicitação em várias planilhas. Além disso, o sistema não pode colar algumas das solicitações copiadas em novas pastas de trabalho porque as solicitações contêm filtros de entrada de outras planilhas. Os filtros de entrada incluem conjuntos de relatórios de células, intervalos de datas de células, filtros de células e outros parâmetros relacionados.

**Para copiar solicitações referenciais**

1. Selecione as células que contêm solicitações que você deseja copiar, inclusive a célula de entrada ou a célula alvo da referência.
1. Clique com o botão direito do mouse nas células realçadas e selecione **[!UICONTROL Copiar solicitações]** no menu de atalho.

   Após selecionar a área onde as solicitações e células de entrada estão localizadas, o sistema realça as células com esses elementos.
1. Selecione uma célula ou um intervalo de células contíguas para preencher com as solicitações coladas.

   Certifique-se de que a célula ou o intervalo de células selecionado não contenha dados nem solicitações.
1. Clique com o botão direito a única célula ou a primeira célula do topo mais à esquerda do intervalo de células e selecione **[!UICONTROL Colar solicitações]**.

   Ao colar solicitações que incluem uma célula de entrada, as opções em [!UICONTROL Colar solicitações] incluem:

   **Usar Célula de Entrada Absoluta:** Cola uma cópia da(s) solicitação(ões) e da formatação associada às células selecionadas na área de colagem que você realçar. A célula de entrada (a célula a que uma das solicitações originais faz referência) não é colada. Em vez disso, a célula de entrada permanece na mesma posição de antes.

   **Usar Célula de Entrada Relativa:** Cola uma cópia da(s) solicitação(ões) e da formatação associada às células selecionadas na área de colagem selecionada, incluindo uma cópia da célula de entrada. O relacionamento espacial das solicitações com a célula de entrada é o mesmo que nas solicitações originais. Entretanto, enquanto as células recém-coladas agora têm uma cópia das solicitações, inicialmente elas não têm conteúdo. Isso acontece porque quando a célula de entrada é recriada na operação de colagem, nenhum dado é associado à célula de entrada. Para exibir dados para as solicitações recém-coladas, você deve inserir um valor na célula de entrada e, em seguida, atualizar as solicitações.
