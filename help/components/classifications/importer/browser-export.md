---
title: Exportação do navegador
description: A exportação do navegador permite exportar seus dados de classificação para um arquivo delimitado por tabulação.
feature: Classifications
exl-id: f4c709b2-f707-4e3c-82ba-6b43def3e698
source-git-commit: 4eea524bf95c9b6bc9ddc878c8c433bc1e60daee
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 99%

---

# Exportação do navegador (herdado)

{{classification-importer-deprecation}}

A exportação do navegador permite exportar seus dados de classificação para um arquivo delimitado por tabulação.

[!UICONTROL Administração] > [!UICONTROL Importador de classificação]

O arquivo do conjunto de dados é um arquivo de dados delimitado por tabulação (extensão de arquivo.tab) que a maioria dos aplicativos de planilha eletrônica suporta.

>[!NOTE]
>As exportações do navegador têm um limite de 30 colunas.

## Descrições de campo

| Elemento | Descrições |
| --- | --- |
| Selecione o Conjunto de relatórios | Selecione o conjunto de relatórios a partir do qual deseja exportar os dados do relatório. |
| Conjunto de dados a ser classificado | No menu suspenso, selecione o conjunto de dados que deseja classificar. |
| Selecione o número de linhas | Especifique quantas linhas de dados serão exportadas.<ul><li>Selecione **[!UICONTROL Tudo]** para baixar todos os dados de relatório (até 50.000 linhas).</li><li>Selecione **[!UICONTROL Limitar linhas de dados a]** se deseja especificar uma certa quantidade de linhas para baixar.</li></ul>Se quiser baixar mais de 50.000 linhas de dados, use o a opção de download do FTP. |
| Filtrar por data de recebimento | (Opcional) Filtrar dados pela data de recebimento. Especifique o intervalo de datas referente ao qual deseja fazer o download de dados. |
| Aplicar filtro de dados | (Opcional) Filtrar o conjunto de dados pelos critérios de dados. É possível filtrar o download para incluir linhas de dados com um valor específico ou linhas de dados com valores de colunas não atribuídos (classificação). Considere as seguintes questões ao aplicar filtros de dados:<ul><li>Você pode usar curingas ao definir um filtro de dados. Use um asterisco para corresponder a zero ou mais caracteres e um ponto de interrogação `?` para corresponder exatamente a um caractere. Use `?*` para corresponder um ou mais caracteres</li><li>Normalmente, quando se aplicam os dois tipos de filtros de dados para um download, apenas as linhas que atendem às duas regras são baixadas. No entanto, aplicam-se as seguintes exceções:<ul><li>Se Linhas com coluna vazia = Todas as colunas, então todas as colunas, exceto a coluna especificada na primeira regra, são verificadas para confirmar se estão vazias. Essa exceção garante que o sistema faça o download de todas as linhas que tenham uma coluna que atenda à primeira regra que também tenham todas as outras colunas vazias.</li><li>Ao fazer o download de linhas de dados com base em colunas vazias, todas as colunas, exceto aquelas especificadas na primeira regra, são verificadas para confirmar se estão vazias.</li><li>Se a mesma coluna for especificada por ambas as regras de filtro (é quase impossível atender ambos os critérios), somente as linhas que corresponderem à primeira regra serão baixadas.</li></ul></ul> |
| Filtro de dados | (Opcional) Filtrar os dados por dados de campanha. É possível fazer o download de dados somente de campanhas ativas, ou selecionar campanhas que começaram (ou terminaram) em um intervalo de datas específico.<br>**Importante**: essa opção não está disponível para conjuntos de relatórios habilitados para a Nova arquitetura de classificação. |
| Exportar numérico 2 | É possível importar classificações numéricas 2 para o sistema por meio do importador. As classificações numéricas 2 são úteis para variáveis que mudam ao longo do tempo para itens diferentes, como valores de custo e orçamento para o relatório Canal de Marketing. Consulte Classificações numéricas 2 para obter mais informações sobre como fazer upload de dados usando as classificações numéricas 2. |
| Codificação | Selecione a codificação de caracteres para o arquivo de dados. O formato de codificação padrão é UTF-8 ou ISO-8859-1, baseado na codificação que foi enviada para classificação. UTF-8 para UTF-16 converte suas classificações codificadas UTF-8 para codificação UTF-16. ISO-8859-1 para UTF-16 converte sua classificações codificadas ISO-8859-1 para codificação UTF-16.<br>**Observação:** ao converter para UTF-16, a codificação de fonte deve ser correspondente à codificação do upload original ou resultados inesperados podem ocorrer. Recomendamos a codificação de todos os arquivos enviados no UTF-8 sem BOM. |
| Saída com aspas | Especifica a versão 2.1 para o arquivo de classificação. Essa configuração coloca aspas em caracteres especiais para garantir que as exportações funcionem no Excel quando houver uma quebra de linha nos valores da eVar. É possível identificar se um arquivo de classificação tem a versão 2.1 ao abrir o arquivo que foi baixado. Você verá versão 2.1 no cabeçalho. Por exemplo: `## SC SiteCatalyst SAINT Import File v:2.1` |

## Exportar dados de classificação por meio do navegador

1. Clique em [!UICONTROL Administração] > [!UICONTROL Importador de classificação].
1. Clique na guia [!UICONTROL Exportação de navegador.]
1. Especificar os detalhes do conjunto de dados.
1. Clique em [!UICONTROL Exportar arquivo].
1. Salve o conjunto de dados em seu sistema local.
