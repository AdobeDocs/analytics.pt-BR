---
title: Gerenciador de processos do conjunto de classificações
description: Exibir os trabalhos de classificação atuais e concluídos gerados a partir dos conjuntos de classificações.
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
feature: Classifications
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 49%

---

# Gerenciador de processos do conjunto de classificações

O gerenciador de processos do conjunto de classificações permite visualizar os processos de classificação atuais e concluídos que foram gerados a partir dos conjuntos de classificações. Também é possível usar essa interface para baixar dados de classificação ou modelos para um processo específico ou fazer upload de dados adicionais para um processo.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de classificações]** > **[!UICONTROL Processos]**

Não é possível criar trabalhos a partir dessa interface. Crie processos fazendo upload de dados para um conjunto de classificações (manualmente ou por meio de um local externo configurado), solicitando um arquivo de download ou um arquivo de modelo.

## Filtrar conjuntos de classificação

O lado esquerdo do gerenciador de processos do conjunto de classificações fornece configurações de filtro para localizar o processo desejado. Clicar no ícone de filtro alterna a visibilidade das configurações de filtro. É possível filtrar conjuntos de classificações por **[!UICONTROL Conjunto de classificações]**, **[!UICONTROL Hora de conclusão]**, **[!UICONTROL Status]**, **[!UICONTROL Tipo de tarefa]** ou **[!UICONTROL Origem]**.

![Filtros de trabalho do conjunto de classificações](../assets/classification-set-job-filters.png)

Opções de filtro adicionais estão disponíveis acima das colunas do gerenciador de processos do conjunto de classificações:

* **[!UICONTROL Pesquisar por título]**: pesquisar processos por nome de arquivo.
* **[!UICONTROL Carregar mais]**: inicialmente, o gerenciador de processos do conjunto de classificações exibe até 1000 processos. Se houver mais jobs, clique neste botão para carregar mais 1000 jobs.
* **Mostrar/Ocultar colunas**: alternar a visibilidade de qualquer coluna além de [!UICONTROL Nome do arquivo] e [!UICONTROL Hora de conclusão].

## Colunas do gerenciador de trabalhos do conjunto de classificações

As seguintes colunas estão disponíveis no gerenciador de trabalhos do conjunto de classificações:

* **[!UICONTROL Nome do arquivo]**: o nome do arquivo de upload ou download.
* **[!UICONTROL Conjunto de classificações]**: o nome do conjunto de classificações ao qual o arquivo se aplica. Você pode clicar no nome do conjunto de classificações para acessar seu [Configurações](manage/settings.md).
* **[!UICONTROL Tamanho]**: o tamanho do arquivo.
* **[!UICONTROL Status]**: o status do processo do arquivo.
   * **[!UICONTROL Criado]**: o processo foi enviado.
   * **[!UICONTROL Em fila]**: o arquivo está pronto para ser processado e aguarda um servidor de classificação processar o arquivo.
   * **[!UICONTROL Validado]**: o arquivo é válido e está aguardando para ser processado.
   * **[!UICONTROL Falha na validação]**: o arquivo está formatado incorretamente ou é inválido. O arquivo não passa pelo processamento.
   * **[!UICONTROL Processamento]**: o arquivo está sendo processado ativamente pela Adobe.
   * **[!UICONTROL Falha no processamento]**: falha no processamento do arquivo.
   * **[!UICONTROL Concluído]**: o processamento está concluído. Os dados de classificação são visíveis no relatório.
   * **[!UICONTROL Falha]**: falha genérica não relacionada à validação ou ao processamento.
* **[!UICONTROL Tipo de trabalho]**: o tipo de trabalho.
* **[!UICONTROL Origem]**: a origem do trabalho.
* **[!UICONTROL Download de arquivo]**: aplica-se somente a processos de download, como o download de dados de classificação ou modelos. Quando um download está pronto, esta coluna fornece um link de download.
* **[!UICONTROL Linhas modificadas]**: o número de linhas modificadas.
* **[!UICONTROL Linhas concluídas]**: o número de linhas concluídas.
* **[!UICONTROL Hora de conclusão]**: a data e a hora em que o processo foi concluído (ou falhou).
