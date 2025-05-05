---
description: Documentação que descreve como filtrar e classificar tabelas no Analysis Workspace.
title: Filtrar e classificar tabelas de forma livre
feature: Freeform Tables
role: User, Admin
exl-id: 15fea9e2-f8d8-4489-9a44-e74a351b8f36
source-git-commit: 1ce002a513860ce15dc8a70825d26795fd93eb1d
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 43%

---

# Filtrar e classificar tabelas de forma livre

As tabelas de forma livre do Analysis Workspace são a base para a análise interativa de dados. Sendo assim, elas podem conter milhares de linhas de informação. Filtrar e classificar os dados pode ser essencial para encontrar as informações mais importantes de maneira eficiente.


## Filtrar tabelas

Os filtros do Analysis Workspace ajudam você a encontrar as informações mais importantes.

>[!NOTE]
>
> Somente itens de dimensão dinâmicos podem ser filtrados conforme descrito nesta seção. Itens de dimensão estáticos não podem ser filtrados. Para obter mais informações, consulte [Itens de dimensão dinâmicos vs estáticos em tabelas de forma livre](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

Você pode usar vários métodos para filtrar linhas de uma tabela de forma livre.

- Excluir linhas específicas de uma tabela
- Aplicar filtros a uma tabela
- Usar filtros de público

Leia como cada método afeta [os totais das tabelas de forma livre](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md).

### Excluir linhas específicas de uma tabela

Você pode excluir rapidamente linhas específicas da tabela sem a necessidade de usar o ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filtro]**.

>[!NOTE]
>
>Ao excluir linhas conforme descrito nesta seção, uma regra [!UICONTROL Sempre excluir itens] é adicionada automaticamente na caixa de diálogo de filtro [!UICONTROL Avançado]. Você pode exibir a regra aplicada selecionando o ícone Filtro ![Filtro](/help/assets/icons/Filter.svg) e Avançado [**[!UICONTROL Mostrar avançado]**](#apply-a-simple-or-advanced-filter-to-a-table).

Para excluir linhas específicas de uma tabela de forma livre:

1. Passe o mouse sobre a linha que deseja excluir e selecione ![Fechar](/help/assets/icons/Close.svg).

   Mantenha pressionada a tecla ***shift*** para selecionar um intervalo de linhas, ou mantenha pressionada a tecla ***cmd*** (no Mac) ou a tecla ***ctrl*** (no Windows) para selecionar várias linhas.

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->


### Aplicar um filtro simples ou avançado a uma tabela

Para filtrar dados em tabelas de forma livre:

1. Passe o mouse sobre a coluna que contém os dados que você deseja filtrar. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Selecione ![Filtro](/help/assets/icons/Filter.svg) **Filtro** quando ele aparecer.

   ![Tabela de forma livre destacando o ícone Filtro.](assets/table-filter-icon.png)

   As seguintes opções estão disponíveis na caixa de diálogo **[!UICONTROL Pesquisar]**:

   ![Filtro simples](assets/filter-simple.png){width="500"}

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Incluir &quot;Nenhum valor&quot;**] | Selecione esta opção para mostrar uma linha **[!UICONTROL Nenhum valor]** na tabela para dados que não têm valor para a dimensão selecionada. Desmarque esta opção para ocultar a linha **[!UICONTROL Nenhum valor]**. |
   | [!UICONTROL **Pesquisar palavra ou frase**] | Especifique uma palavra ou frase pela qual deseja filtrar. Somente as linhas que contêm a palavra ou a frase exata especificada são mostradas. |


1. (Opcional) Para filtrar por critérios diferentes ou por vários critérios, selecione [!UICONTROL **Mostrar avançado**].

   As seguintes opções de filtro avançado estão disponíveis:

   ![Filtro simples](assets/filter-advanced.png){width=500}

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Incluir &quot;Nenhum valor&quot;**] | Selecione esta opção para mostrar uma linha **[!UICONTROL Nenhum valor]** na tabela para dados que não têm valor para a dimensão selecionada. Desmarque esta opção para ocultar a linha **[!UICONTROL Nenhum valor]**. |
   | [!UICONTROL **Corresponder**] | Selecione [!UICONTROL **Se todos os critérios forem atendidos**] para mostrar apenas os dados que atendem a todos os critérios especificados. Essa opção normalmente resulta em dados mais refinados.<br/><br/>Escolha [!UICONTROL **Se algum critério for atendido**] para mostrar dados que atendam a qualquer um dos critérios de filtro especificados. Essa opção normalmente resulta em dados menos refinados. |
   | [!UICONTROL **Critérios**] | Selecione entre as seguintes opções de filtro:<br/><ul><li>[!UICONTROL **Contém a frase**] (padrão): somente os dados que contêm a frase exata especificada por você são incluídos nos resultados filtrados. As palavras devem estar na ordem especificada no campo [!UICONTROL **Pesquisar palavra ou frase**].</li><li>[!UICONTROL **Contém qualquer termo**]: somente os dados que contêm uma ou mais palavras da frase especificada são incluídos nos resultados filtrados. </li><li>[!UICONTROL **Contém todos os termos**]: somente os dados que contêm todas as palavras da frase especificada são incluídos nos resultados filtrados. As palavras não precisam estar na ordem especificada no campo [!UICONTROL **Pesquisar palavra ou frase**].</li><li>[!UICONTROL **Não contém nenhum termo**]: somente os dados que não contêm nenhuma das palavras da frase especificada são incluídos nos resultados filtrados. </li><li>[!UICONTROL **Não contém a frase**]: somente os dados que não contêm a frase exata especificada são incluídos nos resultados filtrados. As palavras devem estar na ordem especificada no campo [!UICONTROL **Pesquisar palavra ou frase**].</li><li>[!UICONTROL **Igual a**]: somente dados que correspondem exatamente à frase especificada são incluídos nos resultados filtrados. </li><li>[!UICONTROL **Não é igual**]: somente os dados que não correspondem exatamente à frase especificada são incluídos nos resultados filtrados. </li><li>[!UICONTROL **Começa com**]: somente os dados que começam com a palavra ou frase exata especificada são incluídos nos resultados filtrados. </li><li>[!UICONTROL **Termina com**]: somente os dados que terminam com a palavra ou frase exata especificada são incluídos nos resultados filtrados. </li></ul>Selecione ![Adicionar](/help/assets/icons/Add.svg) [!UICONTROL **Adicionar linha**] para adicionar vários critérios de filtro. A opção selecionada para [!UICONTROL **Corresponder**] determina **[!UICONTROL Se todos os critérios forem atendidos]** ou **[!UICONTROL Se algum critério for atendido]**. |
   | [!UICONTROL **Sempre excluir itens**] | Especifique o nome de qualquer item que deseja excluir dos dados filtrados. |

1. Selecione **[!UICONTROL Aplicar]** para filtrar os dados. Selecione **[!UICONTROL Limpar]** para limpar todas as entradas. Selecione **[!UICONTROL Cancelar]** para cancelar e fechar a caixa de diálogo. <br/>Um ícone colorido de ![Filtro](/help/assets/icons/FilterColored.svg) **Filtro** indica e exibe detalhes quando um filtro é aplicado à tabela.


## Classificar tabelas

Você pode classificar os dados de uma tabela de forma livre por qualquer coluna no Analysis Workspace que seja uma dimensão ou uma métrica. Uma seta indica como os dados são classificados (**&#x200B;** para decrescente, ou **^** para crescente).

![Classificação](assets/sorting.gif)
