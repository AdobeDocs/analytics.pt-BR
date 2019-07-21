---
description: Uma solicitação referencial usa valores de células como entrada para parâmetros, como um filtro de datas ou relacional.
seo-description: Uma solicitação referencial usa valores de células como entrada para parâmetros, como um filtro de datas ou relacional.
seo-title: Copiar solicitações referenciais
solution: Analytics
title: Copiar solicitações referenciais
topic: Construtor de relatórios
uuid: b 6 f 64630-868 f -455 b -8682-471 ff 9 fc 596 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Copiar solicitações referenciais

Uma solicitação referencial usa valores de células como entrada para parâmetros, como um filtro de datas ou relacional.

Para propagar ou copiar e colar solicitações referenciais em uma planilha, você precisa ter criado pelo menos uma solicitação válida na planilha. Além disso, os dados produzidos pela solicitação precisam conter uma célula cujo valor dependa de uma solicitação em outra célula (usando um filtro de divisão ou correspondência) ou de um filtro que pega a entrada dos dados inseridos em uma célula.

Também é possível criar solicitações que fazem referência a filtros de entrada a partir de solicitações em diferentes planilhas, mas não em pastas de trabalho diferentes. Por exemplo, uma solicitação na Planilha 2 pode usar um conjunto de relatórios de uma determinada célula na Planilha 1 e um intervalo de datas de uma célula em uma solicitação na Planilha 2. A nova saída pode ser colocada em qualquer uma das duas planilhas ou em uma nova planilha na mesma pasta de trabalho. Quando você cola uma solicitação relativa, se um filtro de entrada residir em uma planilha diferente daquela em que a saída da solicitação copiada está localizada, o filtro será colado como um filtro absoluto.

>[!NOTE]
>
>Não é possível inserir uma única solicitação em várias planilhas. Além disso, o sistema não pode colar algumas das solicitações copiadas em novas pastas de trabalho porque as solicitações contêm filtros de entrada de outras planilhas. Os filtros de entrada incluem conjuntos de relatórios de células, intervalos de datas de células, filtros de células e outros parâmetros relacionados.

**Para copiar solicitações referenciais**

1. Selecione as células que contêm solicitações que você deseja copiar, inclusive a célula de entrada ou a célula alvo da referência.
1. Clique com o botão direito do mouse nas células realçadas e selecione **Copiar solicitações** no menu de atalho.

   Após selecionar a área onde as solicitações e células de entrada estão localizadas, o sistema realça as células com esses elementos.
1. Selecione uma célula ou um intervalo de células contíguas para preencher com as solicitações coladas.

   Certifique-se de que a célula ou o intervalo de células selecionado não contenha dados nem solicitações.
1. Clique com o botão direito a única célula ou a primeira célula do topo mais à esquerda do intervalo de células e selecione **[!UICONTROL Colar solicitações]**.

   Ao colar solicitações que incluem uma célula de entrada, as opções em [!UICONTROL Colar solicitações] incluem:

   **Usar célula de entrada absoluta:** Cola uma cópia da solicitação (ou solicitações) e a formatação associada com as células selecionadas na região de colagem realçada. A célula de entrada (a célula a que uma das solicitações originais faz referência) não é colada. Em vez disso, a célula de entrada permanece na mesma posição de antes.

   **Usar célula de entrada relativa:** Cola uma cópia da solicitação (ou solicitações) e a formatação associada com as células selecionadas na região de colagem realçada, incluindo uma cópia da célula de entrada. O relacionamento espacial das solicitações com a célula de entrada é o mesmo que nas solicitações originais. Entretanto, enquanto as células recém-coladas agora têm uma cópia das solicitações, inicialmente elas não têm conteúdo. Isso acontece porque quando a célula de entrada é recriada na operação de colagem, nenhum dado é associado à célula de entrada. Para exibir dados para a solicitação ou solicitações recém-coladas, você precisa inserir um valor na célula de entrada e, em seguida, atualizar as solicitações.
