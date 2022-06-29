---
title: Gerenciador de trabalho do conjunto de classificações
description: Exibir trabalhos de classificação atuais e concluídos gerados a partir dos Conjuntos de Classificação.
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
source-git-commit: 3b0e2bbe531692f26ed118b1d2adc0b5ed28a9bf
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---

# Gerenciador de tarefas do conjunto de classificações

O Gerenciador de trabalhos do conjunto de classificações permite que você veja os trabalhos de classificação atuais e concluídos que foram gerados a partir dos conjuntos de classificações. Também é possível usar essa interface para baixar dados ou modelos de classificação para um trabalho específico ou fazer upload de dados adicionais para um trabalho.

>[!NOTE]
>
>Este recurso está atualmente em versão limitada. Se você quiser acessar esse recurso, entre em contato com o Atendimento ao cliente do Adobe ou com o Gerente de conta, que pode encaminhar sua solicitação para o provisionamento da equipe de Classificações.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de classificações]** > **[!UICONTROL Tarefas]**

Observe que não é possível criar tarefas a partir dessa interface. Em vez disso, você pode criar tarefas carregando dados em um Conjunto de classificações, solicitando um arquivo de download ou solicitando um arquivo de modelo.

## Filtrar conjuntos de classificações

O lado esquerdo do Gerenciador de trabalho do conjunto de classificações fornece configurações de filtro para localizar o trabalho desejado. Clicar no ícone de filtro ativa a visibilidade das configurações de filtro. Você pode filtrar Conjuntos de classificações ao **[!UICONTROL Conjunto de classificações]**, **[!UICONTROL Hora de conclusão]** ou **[!UICONTROL Status]**.

![Filtros de trabalho do conjunto de classificações](../assets/classification-set-job-filters.png)

Opções de filtro adicionais estão disponíveis acima das colunas do Gerenciador de trabalho do conjunto de classificações:

* **[!UICONTROL Pesquisar por título]**: Pesquise trabalhos por nome de arquivo.
* **[!UICONTROL Carregar mais]**: O Gerenciador de trabalho do conjunto de classificações exibe inicialmente até 1000 trabalhos. Clique nesse botão para carregar mais 1000 trabalhos.
* **Mostrar/Ocultar colunas**: Alternar visibilidade de qualquer coluna além de [!UICONTROL Nome do arquivo] e [!UICONTROL Hora de conclusão].

## Colunas do Gerenciador de Jobs do Conjunto de Classificações

As seguintes colunas estão disponíveis no Gerenciador de Jobs do Conjunto de Classificações:

* **[!UICONTROL Nome do arquivo]**: O nome do arquivo de upload ou download.
* **[!UICONTROL Conjunto de classificações]**: O nome do Conjunto de classificações ao qual o arquivo se aplica. Você pode clicar no nome do Conjunto de Classificação para acessar o [Configurações](settings.md).
* **[!UICONTROL Tamanho]**: O tamanho do arquivo.
* **[!UICONTROL Status]**: O status do trabalho que processa o arquivo.
   * **[!UICONTROL Criado]**: O trabalho foi enviado.
   * **[!UICONTROL Em fila]**: O arquivo está pronto para ser processado e aguarda um servidor de classificação processar o arquivo.
   * **[!UICONTROL Validado]**: O arquivo é válido e está aguardando para ser processado.
   * **[!UICONTROL Falha na validação]**: O arquivo está formatado incorretamente ou é inválido. O arquivo não passa pelo processamento.
   * **[!UICONTROL Processamento]**: O arquivo está sendo processado ativamente pelo Adobe.
   * **[!UICONTROL Falha no processamento]**: Falha no processamento do arquivo.
   * **[!UICONTROL Concluído]**: O processamento está concluído. Os dados de classificação são visíveis no relatório.
   * **[!UICONTROL Falha]**: Falha genérica não relacionada à validação ou ao processamento.
* **[!UICONTROL Tipo]**: O tipo de trabalho.
* **[!UICONTROL Download de arquivo]**: Aplica-se somente a tarefas de download, como baixar dados de classificação ou baixar modelos. Quando um download está pronto, esta coluna fornece um link de download.
* **[!UICONTROL Hora de conclusão]**: A data e a hora em que o trabalho foi concluído (ou falhou).
