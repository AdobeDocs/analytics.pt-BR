---
title: Exportação de dados de classificação via FTP
description: A exportação de FTP oferece mais flexibilidade com downloads de conjuntos de dados, incluindo o download de dados de vários conjuntos de relatórios e o download de arquivos de conjuntos de dados com mais de 50.000 linhas de dados
feature: Classifications
exl-id: 6f97f0b2-1a04-407f-9df9-8715da52037d
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 100%

---

# Exportação de dados de classificação via FTP

A opção FTP oferece mais flexibilidade ao fazer download de conjuntos de dados, incluindo a capacidade de fazer download de dados de vários conjuntos de relatórios, bem como de arquivos de conjuntos de dados com mais de 50.000 linhas de dados. Antes de baixar os dados de classificação via FTP, crie uma conta FTP.

Considere as seguintes questões ao aplicar filtros de dados:

* Você pode usar curingas ao definir um filtro de dados. Use um asterisco `*` para corresponder a zero ou mais caracteres e um ponto de interrogação `?` para corresponder exatamente a um caractere. Use `?*` para corresponder um ou mais caracteres
* Normalmente, quando se aplicam os dois tipos de filtros de dados para um download, apenas as linhas que atendem às duas regras são baixadas. No entanto, aplicam-se as seguintes exceções:
   * Se Linhas com coluna vazia = Todas as colunas, então todas as colunas, exceto a coluna especificada na primeira regra, são verificadas para confirmar se estão vazias. Essa exceção garante que a ferramenta faça o download de todas as linhas que tenham uma coluna que atenda à primeira regra que também tenham todas as outras colunas vazias.
   * Ao fazer o download de linhas de dados com base em colunas vazias, todas as colunas, exceto aquelas especificadas na primeira regra, são verificadas para confirmar se estão vazias.
   * Se a mesma coluna for especificada por ambas as regras de filtro (é quase impossível atender ambos os critérios), somente as linhas que corresponderem à primeira regra serão baixadas.
   * Exportações de FTP têm um limite de 30 colunas.

## Exportar classificações usando FTP

Essas etapas descrevem como exportar (fazer download) classificações no Adobe Analytics usando FTP.

1. Criar uma conta FTP.
1. Acesse [!UICONTROL Administrador] > [!UICONTROL Importador de classificação].
1. Clique na guia **[!UICONTROL Importação de FTP]**.
1. Configure os campos para a exportação de FTP.
1. Clique em **[!UICONTROL Exportar arquivo]**.
1. Salve o conjunto de dados em seu sistema local.

## Descrições de campo

| Elemento | Descrições |
| --- | --- |
| [!UICONTROL Selecione o Conjunto de relatórios] | Selecione o conjunto de relatórios a partir do qual deseja exportar os dados do relatório. |
| [!UICONTROL Conjunto de dados a ser classificado] | No menu suspenso, selecione o conjunto de dados que deseja classificar. |
| [!UICONTROL Selecione o número de linhas] | Especifique quantas linhas de dados serão exportadas.<ul><li>Selecione **[!UICONTROL Tudo]** para fazer download de todos os dados do relatório.</li><li>Selecione **[!UICONTROL Limitar linhas de dados a]** se deseja especificar uma certa quantidade de linhas para baixar.</li></ul> |
| [!UICONTROL Filtrar por data de recebimento] | (Opcional) Filtrar dados pela data de recebimento. Especifique o intervalo de datas referente ao qual deseja fazer o download de dados. |
| [!UICONTROL Aplicar filtro de dados] | (Opcional) Filtrar o conjunto de dados pelos critérios de dados. É possível filtrar o download para incluir linhas de dados com um valor específico ou linhas de dados com valores de colunas não atribuídos (classificação). |
| [!UICONTROL Filtro de datas] | (Opcional) Filtre os dados por dados da campanha. Você pode baixar dados apenas de campanhas ativas ou selecionar campanhas que começam (ou terminam) em um intervalo de datas específico. |
| [!UICONTROL Exportar numérico 2] | É possível importar classificações numéricas 2 para o sistema por meio do importador. As classificações numéricas 2 são úteis para variáveis que mudam ao longo do tempo para itens diferentes, como valores de custo e orçamento para o relatório Canal de Marketing. |
| [!UICONTROL Conta FTP] | Especifique as informações do servidor FTP em que deseja que a Adobe faça download do arquivo de dados, incluindo a porta e nome de host, caminho para o diretório de destino, nome de usuário e senha. |
| [!UICONTROL Notificação] | Especifique o endereço de email para receber notificações sobre esse download do FTP. |
| [!UICONTROL Codificação] | Selecione a codificação de caracteres para o arquivo de dados. O formato de codificação padrão é UTF-8 ou ISO-8859-1, baseado na codificação que foi enviada para classificação. UTF-8 para UTF-16 converte suas classificações codificadas UTF-8 para codificação UTF-16. ISO-8859-1 para UTF-16 converte sua classificações codificadas ISO-8859-1 para codificação UTF-16.<br>**Observação:** ao converter para UTF-16, a codificação de fonte deve ser correspondente à codificação do upload original ou resultados inesperados podem ocorrer. Recomendamos a codificação de todos os arquivos enviados no UTF-8 sem BOM. |
