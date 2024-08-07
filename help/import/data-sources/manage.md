---
title: Gerenciar fontes de dados
description: Navegue pela interface gerenciar origens de dados.
exl-id: 315501fb-26e1-436a-938d-5957ca037cd0
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 7%

---

# Gerenciar fontes de dados

Use o gerenciador de fonte de dados para criar, editar ou desativar fontes de dados. Também é possível usar essa interface para acompanhar o status dos arquivos enviados para os locais FTP de fontes de dados.

**[!UICONTROL Administrador]** > **[!UICONTROL Todos os Administradores]** > **[!UICONTROL Fontes de Dados]**

Use o seletor de conjunto de relatórios no canto superior direito para alternar entre conjuntos de relatórios na organização.

Há três guias principais para esta interface: **[!UICONTROL Gerenciar]**, **[!UICONTROL Criar]** e **[!UICONTROL Log de Arquivos]**.

## Gerenciar

A guia **[!UICONTROL Gerenciar]** lida com todas as fontes de dados criadas por sua organização. Você pode visualizar informações de FTP, fazer edições nas variáveis usadas nos arquivos de modelo ou desativar totalmente as fontes de dados.

![Gerenciar](assets/manage.png)

A fonte de dados mais acima é sempre [!UICONTROL Web Beacon]. Essa fonte de dados é o que você usa para a coleta de dados típica por meio do AppMeasurement. Ele não pode ser editado ou desativado.

Cada fonte de dados tem as seguintes opções:

* **[!UICONTROL Reiniciar Processamento]**: reinicia o processamento da fonte de dados que havia sido interrompido devido a erros. O processamento continua até que o erro seguinte seja encontrado. As Fontes de Dados somente interrompem o processamento do arquivo das Fontes de Dados quando você seleciona **[!UICONTROL Parar o processamento em caso de erros]**.
* **[!UICONTROL Processamento Completo]**: não é mais usado - este botão foi usado apenas para [Fontes de dados de processamento completo](full-processing-eol.md).
* **[!UICONTROL Parar processamento em caso de erros]**: uma caixa de seleção que instrui o servidor de processamento a parar quando encontrar um erro. A fonte de dados não reinicia o processamento até que você selecione **[!UICONTROL Reiniciar o Processamento]**. Quando uma fonte de dados encontra um erro de arquivo, ela o notifica do erro. O Adobe move o arquivo com o erro para uma pasta chamada `files_with_errors` no servidor FTP. Após resolver o problema, reenvie o arquivo para processamento.
* **[!UICONTROL Configurar]**: um link que orienta você pelo assistente de criação de fontes de dados para esta fonte de dados. Este assistente permite renomear a fonte de dados ou reconfigurar as variáveis incluídas automaticamente ao baixar um arquivo de modelo.
* **[!UICONTROL Informações de FTP]**: um link que leva você até a última etapa do assistente de criação de fontes de dados, onde as credenciais de FTP são exibidas.

Depois que uma fonte de dados recebe dados, uma tabela é mostrada contendo várias colunas para os arquivos carregados.

* **[!UICONTROL Arquivos na Fila de Processamento]**: O nome do arquivo.
* **[!UICONTROL Linhas]**: o número total de linhas no arquivo.
* **[!UICONTROL Erros]**: o número de linhas que continham erros e não puderam ser assimiladas.
* **[!UICONTROL Avisos]**: o número de linhas que continham avisos.
* **[!UICONTROL Recebido]**: o carimbo de data/hora no qual o arquivo foi recebido no fuso horário do conjunto de relatórios.
* **[!UICONTROL Status]**: o status do arquivo (`Success` ou `Failed`).

## Criar

A guia **[!UICONTROL Criar]** fornece um ponto de partida para o assistente de criação de fontes de dados.

![Criar](assets/create.png)

A categoria e o tipo de fonte de dados eram mais valiosos em versões anteriores do Adobe Analytics. No entanto, eles ainda têm uso limitado:

* O tipo de fonte de dados é mostrado na guia [Gerenciar](#manage) da própria fonte de dados e na guia [Log de Arquivos](#file-log) de cada arquivo individual.
* Alguns tipos de fontes de dados incluem variáveis automaticamente ao baixar o arquivo de modelo. No entanto, você pode incluir qualquer dimensão ou métrica disponível, desde que ela siga o [Formato de arquivo](file-format.md) estabelecido.

Além desses motivos, todos os tipos e categorias de fonte de dados que você pode escolher são efetivamente idênticos. Escolha a categoria e o tipo que melhor representam sua finalidade para usar fontes de dados.

Com a desativação de [Fontes de dados de processamento completo](full-processing-eol.md), várias categorias e tipos não podem ser selecionados. Se você selecionar um tipo de fonte de dados de processamento completo, o botão **[!UICONTROL Ativar]** ficará esmaecido.

## Log de arquivo

A guia **[!UICONTROL Log de Arquivo]** fornece uma exibição agregada de todos os arquivos de fonte de dados carregados para o conjunto de relatórios especificado.

![Log de arquivos](assets/file-log.png)

Há uma barra de pesquisa disponível que ajuda a localizar uma fonte de dados específica. A tabela mostra as seguintes colunas:

* **[!UICONTROL Nome do Data Source]**: o nome da fonte de dados.
* **[!UICONTROL Tipo]**: o tipo da fonte de dados.
* **[!UICONTROL Nome do arquivo]**: o nome do arquivo que foi carregado.
* **[!UICONTROL Linhas]**: o número total de linhas no arquivo.
* **[!UICONTROL Erros]**: o número de linhas que continham erros.
* **[!UICONTROL Avisos]**: não é mais usado. O número de linhas que continham avisos.
* **[!UICONTROL Recebido]**: a data e a hora em que o Adobe iniciou o processamento do arquivo.
* **[!UICONTROL Status]**: o status do arquivo (`Success` ou `Failed`).
