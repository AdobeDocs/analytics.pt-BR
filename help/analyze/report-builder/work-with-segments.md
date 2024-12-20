---
title: Como usar segmentos no Report Builder no Adobe Analytics
description: Descreve como usar segmentos no Report Builder para Adobe Analytics
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 2691fde0-59c6-45a7-80a5-8e5e221adce2
source-git-commit: 2cb8f72a37699aa45135c9d26686f93ee20f20d7
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 4%

---

# Trabalhar com segmentos no Report Builder

Você pode aplicar segmentos ao criar um novo bloco de dados ou ao selecionar a opção **Editar bloco de dados** no painel COMANDOS.

## Aplicar segmentos a um bloco de dados

Para aplicar um segmento a todo o bloco de dados, clique duas vezes em um segmento ou arraste e solte os filtros da lista de componentes na seção Segmentos da Tabela.

## Aplicar segmentos a métricas individuais

Para aplicar segmentos a métricas individuais, arraste e solte um segmento em uma métrica na tabela. Você também pode clicar no ícone **...** à direita de uma métrica no painel Tabela e selecionar **[!UICONTROL Segmentar métrica]**. Para exibir segmentos aplicados, passe o mouse sobre ou selecione uma métrica no painel Tabela. As métricas com segmentos aplicados exibem um ícone de filtro.

![Guia Segmentos exibindo métricas.](./assets/filter_by.png)

## Segmentos de edição rápida

Você pode usar o painel Edição rápida para adicionar, remover ou substituir segmentos de blocos de dados existentes.

Quando você seleciona um intervalo de células na planilha, o link **[!UICONTROL Segmentos]** no painel Edição rápida exibe uma lista de resumo dos segmentos usados pelos blocos de dados nessa seleção.

Para editar segmentos usando o painel Edição rápida

1. Selecione um intervalo de células de um ou vários blocos de dados.

   ![Painel de segmento de Edição Rápida mostrando opções de segmento para conjuntos de relatórios, intervalo de datas e segmentos.](./assets/select_multiple_dbs.png)

1. Clique no link abaixo de **[!UICONTROL Segmentos]** para iniciar o painel Edição rápida - Filtros.

   ![o painel Segmentos que mostra o campo Adicionar Segmentos e as listas Segmentos Aplicados.](./assets/quick_edit_filters.png)

### Adicionar ou remover um segmento

É possível adicionar ou remover segmentos usando as opções Adicionar/Remover.

1. Selecione a guia **[!UICONTROL Adicionar/Remover]** no painel Edição rápida-segmentos.

   Todos os segmentos aplicados aos blocos de dados selecionados são listados no painel Edição rápida-segmentos. Os segmentos aplicados a todos os blocos de dados na seleção são listados sob o cabeçalho **[!UICONTROL Aplicado a todos os blocos de dados selecionados]**. Os segmentos aplicados a alguns, mas não a todos os blocos de dados, estão listados sob o cabeçalho **[!UICONTROL Aplicado a um ou mais blocos de dados selecionados]**.

   Quando vários segmentos estiverem presentes nos blocos de dados selecionados, você poderá pesquisar segmentos específicos usando o campo de pesquisa **[!UICONTROL Adicionar filtro]**.

   ![O campo Adicionar Segmentos.](./assets/add_filter.png)

1. Adicione segmentos selecionando segmentos do menu suspenso **[!UICONTROL Adicionar segmento]**.

   A lista de segmentos pesquisáveis inclui todos os segmentos acessíveis aos conjuntos de relatórios que estão presentes em um ou mais blocos de dados selecionados, bem como todos os segmentos que estão disponíveis globalmente na organização.

   A adição de um segmento aplica o segmento a todos os blocos de dados na seleção.

1. Para remover segmentos, clique no ícone excluir **x** à direita de segmentos na lista **[!UICONTROL Segmentos aplicados]**.

1. Clique em **[!UICONTROL Aplicar]** para salvar as alterações e retornar ao painel do hub.

   Report Builder exibe uma mensagem para confirmar as alterações no segmento aplicado.

### Substituir um segmento

É possível substituir um segmento existente por outro para alterar a forma como os dados são segmentados.

1. Selecione a guia **[!UICONTROL Substituir]** no painel Edição rápida-segmento.

   ![Selecione a guia Substituir.](./assets/replace_filter.png)

1. Use o campo de pesquisa **[!UICONTROL Lista de pesquisa]** para localizar segmentos específicos.

1. Escolha um ou mais segmentos que deseja substituir.

1. Procure um ou mais segmentos no campo Substituir por.

   Selecionar um filtro o adiciona à lista **[!UICONTROL Substituir por]**...

1. Clique em **[!UICONTROL Aplicar]**.

   O Report Builder atualiza a lista de segmentos para refletir a substituição.

### Definir segmentos de bloco de dados a partir da célula

Blocos de dados podem fazer referência a segmentos de uma célula. Vários blocos de dados podem fazer referência à mesma célula para segmentos, permitindo que você alterne facilmente os segmentos para vários blocos de dados de uma vez.

Para aplicar segmentos a partir de uma célula

1. Navegue até a Etapa 2 no processo de criação ou edição do bloco de dados. Consulte [Criar um bloco de dados](./create-a-data-block.md).
1. Clique na guia **[!UICONTROL Segmentos]** para definir filtros.
1. Clique em **[!UICONTROL Criar segmento da célula]**.

   ![Ícone Criar segmento a partir da célula.](./assets/create-filter-from-cell.png)

1. Selecione a célula da qual deseja que os blocos de dados façam referência a um segmento.

1. Adicione a opção de segmento que deseja adicionar à célula, clicando duas vezes no segmento ou arrastando e soltando na seção **[!UICONTROL Segmentos incluídos]**.

   Observação: apenas uma opção pode ser selecionada para a célula em questão de cada vez.

   ![A janela Adicionar segmento da célula mostra os Filtros incluídos.](./assets/select-filters.png)

1. Clique em **[!UICONTROL Aplicar]** para criar a célula de referência.

1. Na guia **[!UICONTROL Segmentos]**, adicione os segmentos de célula de referência recém-criados ao bloco de dados.

   Guia ![Segmentos mostrando o segmento Sheet1!J1(Todos os Dados) adicionado à tabela.](./assets/reference-cell-filter.png)

1. Clique em **[!UICONTROL Concluir]**.

   Agora, essa célula pode ser referenciada por outros blocos de dados em seus segmentos. Para aplicar a célula de referência como um segmento a outros blocos de dados, basta adicionar a referência da célula a seus segmentos na guia Segmentos.

#### Usar a célula de referência para alterar segmentos de blocos de dados

1. Selecione a célula de referência na planilha.

1. Clique no link em **[!UICONTROL Segmentos da Célula]** no menu Edição Rápida.

   ![Segmentos de link de célula mostrando Sheet1!J1 (Todos os Dados)](./assets/filters-from-cell-link.png)

1. Selecione o segmento no menu suspenso.

   ![Menu suspenso de segmentos](./assets/filter-drop-down.png)

1. Clique em **[!UICONTROL Aplicar]**.
