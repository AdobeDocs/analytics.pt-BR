---
title: Exportação de navegador
description: A exportação do navegador permite exportar seus dados de classificação para um arquivo delimitado por tabulação.
source-git-commit: 8a5c7309b5d4061b2e3241219d9bdb1521294535
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 74%

---


# Exportação de navegador

A exportação do navegador permite exportar seus dados de classificação para um arquivo delimitado por tabulação.

Administração > Importador de classificação

O arquivo do conjunto de dados é um arquivo de dados delimitado por tabulação (extensão de arquivo .tab) que a maioria dos aplicativos de planilha eletrônica suporta.

>[!NOTE]
>As exportações do navegador têm um limite de 30 colunas.

## Descrições dos campos

| Elemento | Descrições |
| --- | --- |
| Selecione o Conjunto de relatórios | Selecione o conjunto de relatórios a partir do qual deseja exportar os dados do relatório. |
| Conjunto de dados a ser classificado | No menu suspenso , selecione o conjunto de dados que deseja classificar. |
| Selecione o número de linhas | Especifique quantas linhas de dados serão exportadas.<ul><li>Selecione **[!UICONTROL Tudo]** para baixar todos os dados de relatório (até 50.000 linhas).</li><li>Selecione **[!UICONTROL Limitar linhas de dados a]** se deseja especificar uma certa quantidade de linhas para baixar.</li></ul>Se você quiser baixar mais de 50.000 linhas de dados, use a opção de download do FTP. |
| Filtrar por data de recebimento | (Opcional) Filtrar dados pela data de recebimento. Especifique o intervalo de datas referente ao qual deseja fazer o download de dados. |
| Aplicar filtro de dados | (Opcional) Filtrar o conjunto de dados pelos critérios de dados. É possível filtrar o download para incluir linhas de dados com um valor específico ou linhas de dados com valores de colunas não atribuídos (classificação). Considere as seguintes questões ao aplicar filtros de dados:<ul><li>Você pode usar curingas ao definir um filtro de dados. Use um asterisco para corresponder a zero ou mais caracteres e um ponto de interrogação `?` para corresponder exatamente a um caractere. Use `?*` para corresponder a um ou mais caracteres.</li><li>Normalmente, quando se aplicam os dois tipos de filtros de dados para um download, apenas as linhas que atendem às duas regras são baixadas. No entanto, aplicam-se as seguintes exceções:<ul><li>Se Linhas com coluna vazia = Todas as colunas, então todas as colunas, exceto a coluna especificada na primeira regra, são verificadas para confirmar se estão vazias. Essa exceção garante que o sistema faça o download de todas as linhas que tenham uma coluna que atenda à primeira regra que também tenham todas as outras colunas vazias.</li><li>Ao fazer o download de linhas de dados com base em colunas vazias, todas as colunas, exceto aquelas especificadas na primeira regra, são verificadas para confirmar se estão vazias.</li><li>Se a mesma coluna for especificada por ambas as regras de filtro (é quase impossível atender ambos os critérios), somente as linhas que corresponderem à primeira regra serão baixadas.</li></ul></ul> |
| Filtro de dados | (Opcional) Filtrar os dados por dados de campanha. É possível fazer o download de dados somente de campanhas ativas, ou selecionar campanhas que começaram (ou terminaram) em um intervalo de datas específico.<br>**Importante**: Essa opção não está disponível para conjuntos de relatórios habilitados para a Nova arquitetura de classificação. |

