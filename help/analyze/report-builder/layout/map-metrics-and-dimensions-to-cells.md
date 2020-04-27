---
description: Antes de começar a mapear itens para a planilha, certifique-se de que sua planilha não esteja protegida. Se o esquema de proteção da sua planilha impedir quaisquer ações do usuário, você não conseguirá selecionar células na planilha. Primeiro, desproteja a planilha e, em seguida, adicione o mapeamento de células.
title: Mapear métricas e dimensões para células
topic: Report builder
uuid: 50893e1c-5f2c-4558-8001-41e70d74d6e7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Mapear métricas e dimensões para células

Antes de começar a mapear itens para a planilha, certifique-se de que sua planilha não esteja protegida. Se o esquema de proteção da sua planilha impedir quaisquer ações do usuário, você não conseguirá selecionar células na planilha. Primeiro, desproteja a planilha e, em seguida, adicione o mapeamento de células.

O número de áreas e células a ser mapeado difere de acordo com a métrica selecionada, a granularidade, o intervalo de datas e os filtros definidos. Por exemplo, se você selecionar [!UICONTROL Site Metric] > [!UICONTROL Traffic Report], definir a [!UICONTROL Week] granularidade e o intervalo de datas para [!UICONTROL Last 2 Weeks], será solicitado que você mapeie três células (ao usar [!UICONTROL Custom Layout]) no [!UICONTROL Request Wizard: Step 2]. A solicitação recupera dados para a semana um e dados para a semana dois, onde cada valor de ponto de dados = o valor de uma visualização de página. Your third cell serves as the row heading, which you can configure using [!UICONTROL Format Options].

Se, por engano, você mapear locais incompatíveis na planilha, o Report Builder emitirá um erro.

As seguintes seções contêm mais informações:

* [Selecionar um intervalo de células ](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [Técnicas para selecionar células ](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [Problemas ao mapear ](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## Selecionar um intervalo de células {#section_1E37FB46DA194FB7A1050B8833A48AC6}

On the [!UICONTROL Request Wizard: Step 2], when you enable [!UICONTROL Custom Layout] for a trended request, you can map the request to a range of cells.

Clique em **[!UICONTROL Range Selector]** ![select_cell_icon.png](assets/select_cell_icon.png)

ao lado do item que você deseja mapear.

* **Todas as células no intervalo:** Requer que você selecione um grupo de células para uma solicitação de [!UICONTROL Custom Layout] estilo.
* **Primeira célula do intervalo:** Permite selecionar a célula superior esquerda do intervalo e exibe a [!UICONTROL Range] orientação para especificar a orientação horizontal ou vertical das células de entrada e saída (coluna ou linha). Use esta opção para que o Report Builder selecione as células para você.
* **Orientação do intervalo:** Permite orientar os intervalos de células como colunas ou linhas.
* **Selecionar o canto superior da célula do intervalo:** Exibe as referências da célula.

## Técnicas para selecionar células {#section_760421C3D7F84D67A639174710C93B22}

You select the data by clicking the **[!UICONTROL Range Selection]** icon  ![select_cell_icon.png](assets/select_cell_icon.png)

e arrastando com um clique sobre o intervalo de células desejado da planilha. Uma seleção contínua é contornada com uma borda preta.

![](assets/twenty_cells.gif)

As linhas selecionadas separadas têm uma borda branca fina ao redor de cada linha.

![](assets/twoXten_cells_highlighted.gif)

To map separate rows in one request, use the [!UICONTROL Control] key, then click and drag the cursor over the desired cells. Isto serviria se sua solicitação exigisse quatro áreas com dez células cada, em vez de uma área contínua com 40 células juntas.

![](assets/map4.png)

Depois de selecionar as células, clique **[!UICONTROL Range Selector]** novamente no formulário [!UICONTROL Range Selection] para retornar ao [!UICONTROL Request Wizard: Step 2].

## Problemas ao mapear {#section_CC1BCF841291447EB3A994EB08F3A099}

Se, por engano, você optar por mapear para uma célula que já tem um mapeamento ativo, você notará que nenhuma referência a células é exibida na caixa de texto ao lado do ícone do seletor de intervalo. Quando você clica em [!UICONTROL OK], o Report Builder exibe o erro, &quot;O intervalo selecionado faz interseção com o intervalo de outra solicitação. Altere sua seleção.&quot;

* If you still need to use the cell, right-click on the desired cell or cells, and select **[!UICONTROL Delete Request]**.

Se quiser evitar essa mensagem, você pode adotar duas abordagens:

* Planeje o formato do relatório adicionando formatação às células que têm solicitações e mapeamentos
* Teste as áreas da planilha que contêm mapeamentos

Para testar as áreas com solicitações incorporadas, você pode:

* Launch the [!UICONTROL Request Manager] and click on individual requests listed in the table. Ao clicar na solicitação, você realça as células da planilha onde a solicitação está mapeada.
* Select cells in the spreadsheet you intend to use for a new mapping and click [!UICONTROL From Sheet]. The [!UICONTROL Request Manager] selects the request in the list which has an output item that intersects the selected cell. Se nenhuma solicitação for selecionada, a célula estará disponível.
* Select cells in the spreadsheet, right-click in the context menu and verify if [!UICONTROL Edit Request] is available. Se estiver, há uma solicitação associada a essas células.
