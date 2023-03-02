---
description: Documentação que descreve como filtrar e classificar tabelas no Analysis Workspace.
title: Filtrar e classificar tabelas
feature: Freeform Tables
role: User, Admin
exl-id: 15fea9e2-f8d8-4489-9a44-e74a351b8f36
source-git-commit: af0c56a8911c5ea2fb49fb9625c68331a8517d81
workflow-type: ht
source-wordcount: '653'
ht-degree: 100%

---

# Filtrar e classificar tabelas

As tabelas de forma livre do Analysis Workspace são a base para a análise interativa de dados. Sendo assim, elas podem conter milhares de linhas de informação. Filtrar e classificar os dados pode ser essencial para encontrar as informações mais importantes de maneira eficiente.

## Filtrar tabelas

Os filtros do Analysis Workspace ajudam você a encontrar as informações mais importantes.

Para filtrar dados em tabelas de forma livre:

1. Em uma tabela de forma livre, passe o mouse sobre a coluna que contém os dados que deseja filtrar. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Selecione o ícone **Filtro** quando for exibido.

   ![Ícone de Filtro em uma tabela](assets/table-filter-icon.png)

1. No campo [!UICONTROL **Pesquisar palavra ou frase**], especifique uma palavra ou frase que deseja filtrar. Somente as linhas que contêm a palavra ou a frase exata especificada são mostradas.

1. (Opcional) Para filtrar por critérios diferentes ou por vários critérios, selecione [!UICONTROL **Mostrar avançado**].

   As opções disponíveis são as seguintes

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Incluir não especificado (nenhum)**] | Selecione essa opção para mostrar dados na tabela que não se enquadram em nenhuma das dimensões da tabela. <!--what is this?--> |
   | [!UICONTROL **Corresponder**] | <p>Selecione [!UICONTROL **Se todos os critérios forem atendidos**] para mostrar apenas os dados que atendem a todos os critérios especificados. Essa opção normalmente resulta em dados mais refinados.</p> <p>Selecione [!UICONTROL **Se algum critério for atendido**] para mostrar dados que atendem a qualquer um dos critérios de filtro especificados. Essa opção normalmente resulta em dados menos refinados.</p> |
   | [!UICONTROL **Critérios**] | <p>Selecione dentre as seguintes opções de filtro:</p><p>(Selecione [!UICONTROL **Adicionar linha**] para adicionar vários critérios de filtro. A opção selecionada na seção [!UICONTROL **Corresponder**] determina se todos ou qualquer um dos critérios adicionados devem ser atendidos.)</p><ul><li><p>[!UICONTROL **Contém a frase**]: somente os dados que contêm a frase exata especificada são incluídos nos resultados filtrados. As palavras devem estar na ordem especificada no campo [!UICONTROL **Pesquisar palavra ou frase**].<p>Essa é a configuração padrão ao fazer uma pesquisa simples.</p></p></li><li><p>[!UICONTROL **Contém qualquer termo**]: somente os dados que contêm uma ou mais palavras da frase especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Contém todos os termos**]: somente os dados que contêm todas as palavras da frase especificada são incluídos nos resultados filtrados. As palavras não precisam estar na ordem especificada no campo [!UICONTROL **Pesquisar palavra ou frase**].</p></li><li><p>[!UICONTROL **Não contém nenhum termo**]: somente os dados que não contêm nenhuma das palavras da frase especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Não contém a frase**]: somente os dados que não contêm a frase exata especificada são incluídos nos resultados filtrados. As palavras devem estar na ordem especificada no campo [!UICONTROL **Pesquisar palavra ou frase**].</p></li><li><p>[!UICONTROL **Igual**]: somente os dados que correspondem exatamente à frase especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Não é igual**]: somente os dados que não correspondem exatamente à frase especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Começa com**]: somente os dados que começam com a palavra ou frase exata especificada são incluídos nos resultados filtrados. </p></li><li><p>[!UICONTROL **Termina com**]: somente os dados que terminam com a palavra ou frase exata especificada são incluídos nos resultados filtrados. </p></li></ul> |
   | [!UICONTROL **Sempre excluir itens**] | Especifique o nome de qualquer item que deseja excluir dos dados filtrados. |

1. Selecione [!UICONTROL **Aplicar**] para filtrar os dados.

   O ícone de **Filtro** ![Ícone de filtro azul da tabela filtrada](assets/table-filter-blue-icon.png) fica azul quando um filtro é aplicado à tabela.

## Classificar tabelas

Você pode classificar os dados de uma tabela de forma livre por qualquer coluna no Analysis Workspace que seja uma métrica.

Um ícone de seta para baixo ![Ícone de seta para baixo na tabela classificada por coluna](assets/table-sort-arrow-icon.png) é visível no cabeçalho da coluna pela qual os dados estão sendo classificados no momento.

Para classificar os dados em uma tabela de forma livre por uma coluna específica:

1. Passe o mouse sobre o título da coluna pela qual deseja classificar os dados.

1. Selecione o ícone de seta para baixo quando ele for exibido.

   ![Ícone de seta para baixo na tabela classificada por coluna](assets/table-sort.png)

   Os dados da tabela são classificados pela coluna selecionada.
