---
description: Documentação que descreve como filtrar e classificar tabelas no Analysis Workspace.
title: Filtrar e classificar tabelas
feature: Freeform Tables
role: User, Admin
exl-id: 15fea9e2-f8d8-4489-9a44-e74a351b8f36
source-git-commit: af0c56a8911c5ea2fb49fb9625c68331a8517d81
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 1%

---

# Filtrar e classificar tabelas

As tabelas de forma livre no Analysis Workspace são a base para a análise interativa de dados. Dessa forma, podem conter milhares de linhas de informação. Filtrar e classificar os dados pode ser uma parte essencial da análise eficiente das informações mais importantes.

## Filtrar tabelas

Os filtros no Analysis Workspace ajudam você a exibir as informações mais importantes.

Para filtrar dados em tabelas de forma livre:

1. Em uma tabela de forma livre, passe o mouse sobre a coluna que contém os dados que deseja filtrar. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Selecione o **Filtro** quando for exibido.

   ![Ícone Filtrar em uma tabela](assets/table-filter-icon.png)

1. No [!UICONTROL **Pesquisar palavra ou frase**] , especifique uma palavra ou frase para a qual deseja filtrar. Somente as linhas que contêm a palavra ou a frase exata especificada são mostradas.

1. (Opcional) Para filtrar por critérios diferentes ou por vários critérios, selecione [!UICONTROL **Mostrar avançado**].

   As opções disponíveis são as seguintes

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Incluir não especificado (nenhum)**] | Selecione essa opção para mostrar dados na tabela que não se enquadram em nenhuma das dimensões da tabela. <!--what is this?--> |
   | [!UICONTROL **Corresponder**] | <p>Choose [!UICONTROL **Se todos os critérios forem atendidos**] para mostrar apenas os dados que atendem a todos os critérios especificados. Essa opção normalmente resulta em dados mais refinados.</p> <p>Choose [!UICONTROL **Se algum critério for atendido**] para mostrar dados que atendem a qualquer um dos critérios de filtro especificados. Essa opção normalmente resulta em dados menos refinados.</p> |
   | [!UICONTROL **Critérios**] | <p>Selecione dentre as seguintes opções de filtro:</p><p>(Selecione [!UICONTROL **Adicionar linha**] para adicionar vários critérios de filtro. A opção selecionada na variável [!UICONTROL **Corresponder**] determina se todos ou qualquer um dos critérios adicionados devem ser atendidos.)</p><ul><li><p>[!UICONTROL **Contém a frase**]: Somente os dados que contêm a frase exata especificada são incluídos nos resultados filtrados. As palavras devem estar na ordem especificada no [!UICONTROL **Pesquisar campo de palavra ou frase**].<p>Essa é a configuração padrão ao fazer uma pesquisa simples.</p></p></li><li><p>[!UICONTROL **Contém qualquer termo**]: Somente os dados que contêm uma ou mais palavras da frase especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Contém todos os termos**]: Somente os dados que contêm todas as palavras da frase especificada são incluídos nos resultados filtrados. As palavras não precisam estar na ordem especificada no [!UICONTROL **Pesquisar campo de palavra ou frase**].</p></li><li><p>[!UICONTROL **Não contém nenhum termo**]: Somente os dados que não contêm nenhuma das palavras da frase especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Não contém a frase**]: Somente os dados que não contêm a frase exata especificada são incluídos nos resultados filtrados. As palavras devem estar na ordem especificada no [!UICONTROL **Pesquisar campo de palavra ou frase**].</p></li><li><p>[!UICONTROL **Igual**]: Somente os dados que correspondem exatamente à frase especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Não é igual**]: Somente os dados que não correspondem exatamente à frase especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Começa com**]: Somente os dados que começam com a palavra ou frase exata especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Termina com**]: Somente os dados que terminam com a palavra ou frase exata especificada são incluídos nos resultados filtrados. </p></li></ul> |
   | [!UICONTROL **Sempre excluir itens**] | Especifique o nome de qualquer item que deseja excluir dos dados filtrados. |

1. Selecionar [!UICONTROL **Aplicar**] para filtrar os dados.

   O **Filtro** ícone ![Ícone de filtro azul da tabela filtrada](assets/table-filter-blue-icon.png) fica azul quando um filtro é aplicado à tabela.

## Classificar tabelas

Você pode classificar os dados de uma tabela de forma livre por qualquer coluna na Analysis Workspace que seja uma métrica.

Um ícone de seta para baixo ![Ícone de seta para baixo na coluna de tabela classificada](assets/table-sort-arrow-icon.png) é visível no cabeçalho da coluna que os dados estão sendo classificados no momento.

Para classificar os dados em uma tabela de forma livre por uma coluna específica:

1. Passe o mouse sobre o título da coluna pela qual deseja classificar os dados.

1. Selecione o ícone de seta para baixo quando ele for exibido.

   ![Ícone de seta para baixo na coluna de tabela classificada](assets/table-sort.png)

   Os dados da tabela são classificados pela coluna selecionada.
