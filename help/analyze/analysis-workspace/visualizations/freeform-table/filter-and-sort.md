---
description: Documentação que descreve como filtrar e classificar tabelas no Analysis Workspace.
title: Filtrar e classificar tabelas de forma livre
feature: Freeform Tables
role: User, Admin
exl-id: 15fea9e2-f8d8-4489-9a44-e74a351b8f36
source-git-commit: 398d4ae264ce108c16a03cef086ae2614b442a2b
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 72%

---

# Filtrar e classificar tabelas de forma livre

As tabelas de forma livre do Analysis Workspace são a base para a análise interativa de dados. Sendo assim, elas podem conter milhares de linhas de informação. Filtrar e classificar os dados pode ser essencial para encontrar as informações mais importantes de maneira eficiente.

## Filtrar tabelas

Os filtros do Analysis Workspace ajudam você a encontrar as informações mais importantes.

>[!NOTE]
>
> Somente itens de dimensão dinâmicos podem ser filtrados conforme descrito nesta seção. Itens de dimensão estáticos não podem ser filtrados. Para obter mais informações, consulte [Itens de dimensão dinâmicos vs estáticos em tabelas de forma livre](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

## Filtrar linhas da tabela de forma livre

Você pode usar vários métodos para filtrar linhas de uma tabela de forma livre. 

- Clique no X na linha
- Filtros de tabela
- Segmentação

Leia como cada método afeta [os totais das tabelas de forma livre](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md).

### Excluir rapidamente linhas específicas de uma tabela

Você pode excluir rapidamente linhas específicas da tabela sem precisar abrir a caixa de diálogo Filtro.

>[!NOTE]
>
>Quando você exclui linhas conforme descrito nesta seção, uma regra [!UICONTROL **Sempre excluir itens**] é aplicada automaticamente na caixa de diálogo de filtro avançado. (Você pode exibir a regra aplicada selecionando o ícone Filtro e [**[!UICONTROL Mostrar avançado]**](#apply-a-simple-or-advanced-filter-to-a-table).)

Para excluir rapidamente linhas específicas de uma tabela de forma livre:

1. Passe o mouse sobre a linha que deseja excluir e selecione o ícone x.

   Mantenha pressionada a tecla Shift para selecionar um intervalo de linhas, ou mantenha pressionada a tecla Command (no Mac) ou a tecla Ctrl (no Windows) para selecionar várias linhas.

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->

### Aplicar um filtro simples ou avançado a uma tabela

Para filtrar dados em tabelas de forma livre:

1. Passe o mouse sobre a coluna que contém os dados que você deseja filtrar. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Selecione o ícone **Filtro** quando for exibido.

   ![Ícone de Filtro em uma tabela](assets/table-filter-icon.png)

   As opções disponíveis são as seguintes:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Pesquisar palavra ou frase**] | Especifique uma palavra ou frase pela qual deseja filtrar. Somente as linhas que contêm a palavra ou a frase exata especificada são mostradas. |
   | [!UICONTROL **Incluir não especificado (nenhum)**] | Selecione essa opção para mostrar dados na tabela que não se enquadram em nenhuma das dimensões da tabela. <!--what is this?--> |

1. (Opcional) Para filtrar por critérios diferentes ou por vários critérios, selecione [!UICONTROL **Mostrar avançado**].

   As seguintes opções de filtro avançado estão disponíveis:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Incluir não especificado (nenhum)**] | Selecione essa opção para mostrar dados na tabela que não se enquadram em nenhuma das dimensões da tabela. <!--what is this?--> |
   | [!UICONTROL **Corresponder**] | <p>Selecione [!UICONTROL **Se todos os critérios forem atendidos**] para mostrar apenas os dados que atendem a todos os critérios especificados. Essa opção normalmente resulta em dados mais refinados.</p> <p>Selecione [!UICONTROL **Se algum critério for atendido**] para mostrar dados que atendem a qualquer um dos critérios de filtro especificados. Essa opção normalmente resulta em dados menos refinados.</p> |
   | [!UICONTROL **Critérios**] | <p>Selecione dentre as seguintes opções de filtro:</p><p>(Selecione [!UICONTROL **Adicionar linha**] para adicionar vários critérios de filtro. A opção selecionada na seção [!UICONTROL **Corresponder**] determina se todos ou qualquer um dos critérios adicionados devem ser atendidos.)</p><ul><li><p>[!UICONTROL **Contém a frase**]: somente os dados que contêm a frase exata especificada são incluídos nos resultados filtrados. As palavras devem estar na ordem especificada no campo [!UICONTROL **Pesquisar palavra ou frase**].<p>Essa é a configuração padrão ao fazer uma pesquisa simples.</p></p></li><li><p>[!UICONTROL **Contém qualquer termo**]: somente os dados que contêm uma ou mais palavras da frase especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Contém todos os termos**]: somente os dados que contêm todas as palavras da frase especificada são incluídos nos resultados filtrados. As palavras não precisam estar na ordem especificada no campo [!UICONTROL **Pesquisar palavra ou frase**].</p></li><li><p>[!UICONTROL **Não contém nenhum termo**]: somente os dados que não contêm nenhuma das palavras da frase especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Não contém a frase**]: somente os dados que não contêm a frase exata especificada são incluídos nos resultados filtrados. As palavras devem estar na ordem especificada no campo [!UICONTROL **Pesquisar palavra ou frase**].</p></li><li><p>[!UICONTROL **Igual**]: somente os dados que correspondem exatamente à frase especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Não é igual**]: somente os dados que não correspondem exatamente à frase especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Começa com**]: somente os dados que começam com a palavra ou frase exata especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Termina com**]: somente os dados que terminam com a palavra ou frase exata especificada são incluídos nos resultados filtrados. </p></li></ul> |
   | [!UICONTROL **Sempre excluir itens**] | Especifique o nome de qualquer item que deseja excluir dos dados filtrados. |

1. Selecione [!UICONTROL **Aplicar**] para filtrar os dados.

   O ícone de **Filtro** ![Ícone de filtro azul da tabela filtrada](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) fica azul quando um filtro é aplicado à tabela.

### Segmentação

Consulte nossa [Documentação de segmentação](/help/components/segmentation/seg-home.md) para obter mais detalhes.

## Classificar tabelas

Você pode classificar os dados de uma tabela de forma livre por qualquer coluna no Analysis Workspace que seja uma métrica.

Um ícone de seta para baixo ![Ícone de seta para baixo na tabela classificada por coluna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) é visível no cabeçalho da coluna pela qual os dados estão sendo classificados no momento.

Para classificar os dados em uma tabela de forma livre por uma coluna específica:

1. Passe o mouse sobre o título da coluna pela qual deseja classificar os dados.

2. Selecione o ícone de seta para baixo quando ele for exibido.

   ![Ícone de seta para baixo na tabela classificada por coluna](assets/table-sort.png)

   Os dados da tabela são classificados pela coluna selecionada.
