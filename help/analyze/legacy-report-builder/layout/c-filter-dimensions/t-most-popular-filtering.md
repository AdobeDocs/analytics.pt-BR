---
description: Filtros de classificação e condicionais que você configura usando lógica booleana com expressões de pesquisa E/OU.
title: Filtragem mais popular
uuid: 558fa592-41be-4e66-8705-81262afe1fc7
feature: Report Builder
role: User, Admin
exl-id: 31587740-6caa-40cb-bb24-d7a15181f642
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 89%

---

# Filtragem mais popular

{{legacy-arb}}

Filtros de classificação e condicionais que você configura usando lógica booleana com expressões de pesquisa E/OU.

Os filtros mais populares são filtros de expressão que você configura usando lógica booleana com condições E/OU, como [!UICONTROL Página não contém &#x200B;]*`<product name>`* com condições ou grupos de condições como [!UICONTROL Inclui tudo], [!UICONTROL Inclui qualquer] ou [!UICONTROL Exclui tudo]. É possível [salvar](/help/analyze/legacy-report-builder/layout/c-filter-dimensions/saved-filters.md) essas expressões para outra solicitação nessa ou em outras pastas de trabalho.

**Para criar um filtro mais popular**

1. Crie ou edite uma solicitação e então acesse o [!UICONTROL Assistente de solicitações: etapa 2].

1. No [!UICONTROL Assistente de solicitações: etapa 2], clique no link ao lado da dimensão na grade e, em seguida, escolha **[!UICONTROL Filtro]**.

   ![Captura de tela mostrando a caixa de diálogo Definir Filtro com opções para Filtrar por Aplicativo, Usuário e Projeto.](/help/admin/admin/assets/filter.png)

1. No formulário [!UICONTROL Escolher página], habilite **[!UICONTROL Mais popular]** e, então, configure as seguintes opções:

   **Classificação inicial:** A classificação inicial de uma dimensão. A classificação padrão de 1 indica o item no topo da lista de dados relatados. Por exemplo, para a dimensão [!UICONTROL Página], a marca inicial 1 indica a página mais solicitada de seu site. Você poderia especificar 10 ou outro valor como a célula de classificação inicial, o que produz um relatório que começa com 10 como a mais alta. As métricas são organizadas em ordem decrescente, de modo que os itens de linha com maior atividade sejam relatados primeiro na lista. Se você precisar de mais de 50.000 nomes de páginas em uma solicitação, mas tiver milhares de páginas sobre as quais emitir relatórios, poderá copiar a solicitação e alterar a classificação inicial para recuperar os dados apropriados em blocos de 50.000.

   **Número de entradas:** (somente [!UICONTROL Layout dinâmico]) Define quantos itens são relatados para uma métrica específica para um intervalo de datas. Algumas métricas podem listar centenas de entradas, enquanto outras podem mostrar apenas algumas. Por exemplo, para a dimensão [!UICONTROL Seção do site], um número de entradas de 25 indica que o relatório mostra as 25 páginas mais visitadas.

   Setas permitem alterar a [!UICONTROL Classificação inicial] e o [!UICONTROL Número de entradas] do primeiro ponto de dados na planilha. Por padrão, a [!UICONTROL Classificação inicial] é definida como 1 e o [!UICONTROL Número de entradas] como 10. Esses valores são ajustáveis com no mínimo 1 e no máximo 50.000 para determinadas métricas. Cada métrica tem seu próprio teto para o [!UICONTROL Número de entradas]. Valores negativos ou zero não são permitidos nesses campos. Se você escolher 15 para a [!UICONTROL Classificação inicial] e 10 para o [!UICONTROL Número de entradas], as solicitações de dados para a métrica retorna as 10 páginas mais visitadas, onde a primeira página mais visitada é a número 15 na lista para o intervalo de datas especificado. Todas as páginas mais solicitadas classificadas de 15ª a 25ª são listadas em ordem decrescente.

   >[!NOTE]
   >
   >Aplicar filtros a solicitações existentes provoca alterações nos dados apresentados. Suponha que você mapeou as dez principais [!UICONTROL Páginas] para as células $A$1 a $A$10, com 1 para a [!UICONTROL Classificação inicial] e 10 para o [!UICONTROL Número de entradas]. Se você alterar esses valores para mostrar 1 para [!UICONTROL Classificação inicial] e somente 3 para [!UICONTROL Número de entradas], os dados que anteriormente preenchiam as células $A$4 a $A$10 não serão mais exibidos.

1. Para criar uma expressão de pesquisa, clique em **[!UICONTROL Adicionar]**.

1. No formulário [!UICONTROL Definir filtro], configure as condições apropriadas para as suas necessidades.


   ![Captura de tela mostrando a caixa de diálogo Definir Filtro.](assets/expressions_define_filter.png)

   O ícone select cell permite localizar uma condição definida no valor de uma célula. ![O ícone de célula selecionada.](assets/select_cell_icon.png)

   O link **Adicionar Condição** permite que você adicione uma condição à expressão. Não há limite para o número de condições que podem ser adicionadas.

1. Clique em **[!UICONTROL OK]**.

   ![Captura de tela da caixa de diálogo Definir Filtro com o botão OK no lado inferior direito.](assets/choose_page_02.png)

1. No formulário [!UICONTROL Escolher página], clique em **[!UICONTROL Salvar]** para salvar a expressão.
1. Clique em **[!UICONTROL OK]**.
