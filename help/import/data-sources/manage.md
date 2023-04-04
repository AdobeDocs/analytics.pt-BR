---
title: Gerenciar fontes de dados
description: Navegue pela interface gerenciar fontes de dados.
source-git-commit: e32a7c85e2f0629c04bcd7ed0fa80ec1593bb6e8
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 2%

---

# Gerenciar fontes de dados

Use o gerenciador de fonte de dados para criar, editar ou desativar fontes de dados. Também é possível usar essa interface para rastrear o status de arquivos carregados em locais FTP de fontes de dados.

**[!UICONTROL Administrador]** > **[!UICONTROL Todos os administradores]** > **[!UICONTROL Fontes de dados]**

Use o seletor do conjunto de relatórios na parte superior direita para alternar entre conjuntos de relatórios na organização.

Há três guias principais para essa interface; **[!UICONTROL Gerenciar]**, **[!UICONTROL Criar]** e **[!UICONTROL Log de arquivo]**.

## Gerenciar

O **[!UICONTROL Gerenciar]** A guia manipula todas as fontes de dados criadas pela sua organização. Você pode exibir informações de FTP, fazer edições em variáveis usadas em arquivos de modelo ou desativar totalmente as fontes de dados.

![Gerenciar](assets/manage.png)

A fonte de dados mais alta é sempre [!UICONTROL Web beacon]. Essa fonte de dados é o que você usa para a coleta de dados típica por meio do AppMeasurement. Ele não pode ser editado ou desativado.

Cada fonte de dados tem as seguintes opções:

* **[!UICONTROL Reiniciar Processamento]**: Reinicia o processamento da fonte de dados que havia sido interrompido por erros. O processamento continua até que o erro seguinte seja encontrado. As Fontes de dados somente interrompem o processamento do arquivo das Fontes de dados quando você seleciona **[!UICONTROL Parar o processamento em caso de erros]**.
* **[!UICONTROL Processamento completo]**: Não é mais usado - este botão foi usado somente para [Fontes de dados de processamento completo](full-processing-eol.md).
* **[!UICONTROL Parar o processamento em caso de erros]**: Uma caixa de seleção que instrui o servidor de processamento a parar quando encontrar um erro. A fonte de dados não reinicia o processamento até que você selecione **[!UICONTROL Reiniciar Processamento]**. Quando uma fonte de dados encontra um erro de arquivo, ela o notifica do erro. O Adobe move o arquivo com o erro para uma pasta chamada `files_with_errors` no servidor FTP. Depois de resolver o problema, envie novamente o arquivo para processamento.
* **[!UICONTROL Configurar]**: Um link que o orienta pelo assistente de criação de fontes de dados para essa fonte de dados. Este assistente permite renomear a fonte de dados ou reconfigurar as variáveis incluídas automaticamente ao baixar um arquivo de modelo.
* **[!UICONTROL Informações de FTP]**: Um link que leva você à última etapa do assistente de criação de fontes de dados, onde as credenciais do FTP são exibidas.

Quando uma fonte de dados recebe dados, uma tabela é mostrada contendo várias colunas para os arquivos carregados.

* **[!UICONTROL Arquivos Na Fila De Processamento]**: O nome do arquivo.
* **[!UICONTROL Linhas]**: O número total de linhas no arquivo.
* **[!UICONTROL Erros]**: O número de linhas que continham erros e que não puderam ser assimiladas.
* **[!UICONTROL Avisos]**: O número de linhas que continham avisos.
* **[!UICONTROL Recebido]**: O carimbo de data e hora em que o arquivo foi recebido no fuso horário do conjunto de relatórios.
* **[!UICONTROL Status]**: O status do arquivo (`Success` ou `Failed`).

## Criar

O **[!UICONTROL Criar]** fornece um ponto de partida para o assistente de criação de fontes de dados.

![Criar](assets/create.png)

A categoria e o tipo da fonte de dados eram mais valiosos em versões anteriores do Adobe Analytics. No entanto, a sua utilização é limitada:

* O tipo de fonte de dados é exibido na variável [Gerenciar](#manage) para a própria fonte de dados, e a guia [Log de arquivo](#file-log) para cada arquivo individual.
* Alguns tipos de fonte de dados incluem variáveis automaticamente ao baixar o arquivo de modelo. No entanto, é possível incluir qualquer dimensão ou métrica disponível, desde que ela adira ao [Formato de arquivo](file-format.md).

Além desses motivos, todas as categorias e tipos de fonte de dados que você pode escolher são efetivamente idênticos. Escolha a categoria e o tipo que melhor represente sua finalidade para usar as fontes de dados.

Com a aposentação de [Fontes de dados de processamento completo](full-processing-eol.md), não é possível selecionar várias categorias e tipos. Se você selecionar um tipo de fonte de dados de processamento completo, a variável **[!UICONTROL Ativar]** está acinzentado.

## Log de arquivo

O **[!UICONTROL Log de arquivo]** Essa guia oferece uma visualização agregada de todos os arquivos de fonte de dados carregados para o conjunto de relatórios em questão.

![Log de arquivo](assets/file-log.png)

Uma barra de pesquisa está disponível e ajuda a localizar uma fonte de dados específica. A tabela mostra as seguintes colunas:

* **[!UICONTROL Nome da fonte de dados]**: O nome da fonte de dados.
* **[!UICONTROL Tipo]**: O tipo da fonte de dados.
* **[!UICONTROL Nome do arquivo]**: O nome do arquivo que foi carregado.
* **[!UICONTROL Linhas]**: O número total de linhas no arquivo.
* **[!UICONTROL Erros]**: O número de linhas que continham erros.
* **[!UICONTROL Avisos]**: Não está mais em uso. O número de linhas que continham avisos.
* **[!UICONTROL Recebido]**: A data e a hora em que o Adobe iniciou o processamento do arquivo.
* **[!UICONTROL Status]**: O status do arquivo (`Success` ou `Failed`).
