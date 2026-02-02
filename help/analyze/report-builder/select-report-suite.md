---
title: Selecionar Um Conjunto De Relatórios No Report Builder
description: Saiba como selecionar um conjunto de relatórios no Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 96e24d5d-78fb-4e5c-8513-c5fe221d0aeb
source-git-commit: 6f7de360ac24261eabb46c6cfce99449261706de
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 1%

---

# Selecione um conjunto de relatórios

Você pode selecionar um conjunto de relatórios no menu suspenso ou selecionar um conjunto de relatórios em uma célula e atualizar automaticamente seu bloco de dados com um novo conjunto de relatórios.

## Selecionar conjunto de relatórios de uma célula

Selecionar um conjunto de relatórios de uma célula facilita a atualização de blocos de dados usando conjuntos de relatórios diferentes. Em vez de criar relatórios totalmente novos com blocos de dados separados, você pode atualizar blocos de dados com um conjunto de relatórios selecionado de uma célula.

Selecionar um conjunto de relatórios de uma célula é útil quando você tem:

* Vários conjuntos de relatórios que são semelhantes ou idênticos entre si na estrutura.
* Formatos de blocos de dados complicados que incluem componentes e layouts personalizados.

Para selecionar um conjunto de relatórios de uma célula, primeiro crie um bloco de dados e atribua vários conjuntos de relatórios a uma célula fora do bloco de dados. Em seguida, use o **[!UICONTROL Conjunto de relatórios do painel]** para atualizar seus blocos de dados de conjuntos de relatórios diferentes.

1. Criar um bloco de dados. Para obter informações sobre como criar um bloco de dados, consulte [Criar um bloco de dados](/help/analyze/report-builder/create-a-data-block.md).

1. Selecione ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) em **[!UICONTROL Report Suites]**.

1. Selecione uma célula usando ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) fora do bloco de dados.

1. Adicione um ou mais conjuntos de relatórios da **[!UICONTROL Selecione conjuntos de relatórios para adicionar ao conjunto de relatórios da célula]** usando o recurso arrastar e soltar. Como alternativa, você pode selecionar duas vezes um conjunto de relatórios para adicioná-lo à lista **[!UICONTROL Conjuntos de relatórios incluídos]**.

   * Você pode usar a ![Pesquisa](/help/assets/icons/Search.svg) **[!UICONTROL _Selecionar conjuntos de relatórios_]** para procurar conjuntos de relatórios.
   * Use ![MaisPequeno](/help/assets/icons/MoreSmall.svg) para abrir um menu de contexto e mover conjuntos de relatórios para cima ou para baixo na lista **[!UICONTROL Conjuntos de relatórios incluídos]**.
   * Use ![CrossSize75](/help/assets/icons/CrossSize75.svg) para excluir um conjunto de relatórios da lista **[!UICONTROL Conjuntos de relatórios incluídos]**.

   ![Selecionar conjunto de relatórios de uma célula](assets/dataviews-from-a-cell.png){zoomable="yes"}

1. Selecione **[!UICONTROL Aplicar]** para aplicar os conjuntos de relatórios selecionados à célula selecionada.


## Alterar o conjunto de relatórios de uma célula

1. Selecione o local da célula do conjunto de relatórios em sua planilha.
1. No hub do Report Builder, selecione o link **[!UICONTROL Conjuntos de relatórios da célula]** em **[!UICONTROL Edição rápida]**.
1. Selecione um conjunto de relatórios no menu suspenso **[!UICONTROL Conjunto de relatórios]**.

   ![Alterar conjunto de relatórios de uma célula](assets/change-data-view-from-cell.png){zoomable="yes"}
1. Opcional, selecione **[!UICONTROL Atualizar bloco(s) de dados após a alteração]**.

1. Selecione **[!UICONTROL Aplicar]**. O Report Builder atualiza o bloco de dados com base no conjunto de relatórios selecionado.
