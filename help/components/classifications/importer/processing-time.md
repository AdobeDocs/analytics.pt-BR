---
title: Tempo de processamento do importador de classificação
description: Entenda o Adobe de tempo que processa os arquivos de classificação e como minimizar o tempo de processamento.
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---


# Tempo de processamento do importador de classificação

O tempo de processamento de um arquivo de classificação varia com o tamanho do arquivo e o número total de processos de Adobe de arquivos. As classificações normalmente não levam mais de 72 horas. No entanto, os períodos de classificação pesada que usam organizações que usam o Adobe Analytics podem fazer com que os arquivos demorem mais de 72 horas. O Adobe vê um uso intenso de classificação em meses antes da temporada de férias.

Se quiser ver se um arquivo de classificação foi concluído, faça o seguinte:

1. Faça logon no Adobe Analytics e navegue até **[!UICONTROL Admin]** > Importador **** de classificação.
2. Selecione o conjunto de relatórios e o conjunto de dados em questão.
3. Se o processamento ainda não estiver concluído, uma das seguintes mensagens será exibida:

   * ![Aviso](assets/icon_notice_notice.gif) O relatório selecionado tem uma importação de classificação que está sendo processada.
   * ![Aviso](assets/icon_notice_notice.gif) O relatório selecionado tem dados de classificação que ainda não foram propagados para todos os servidores.

Se você quiser minimizar o tempo de importação da classificação, o Adobe recomenda seguir as seguintes diretrizes:

* **Use o construtor de regras de classificação quando possível**: O construtor de regras de classificação processa os dados de forma diferente do importador de classificação tradicional. Se os dados de classificação seguirem padrões específicos, o uso desse recurso é altamente recomendado.
* **Carregar somente linhas** alteradas: Essa prática reduz muito o tempo necessário para processar arquivos de classificação, pois não classifica em linhas inalteradas. O Adobe recomenda que somente as linhas alteradas sejam carregadas.
* **Planeje**: O upload de dados de classificação pelo start é feito o mais rápido possível, especialmente se esses dados forem usados durante a temporada de festas.
* **Combinar arquivos de classificação sempre que possível**: Se uma única variável tiver várias classificações, carregue um único arquivo com todas as classificações aplicáveis. Evite carregar várias classificações para a mesma variável.
* **Evite carregar arquivos acima de 500 MB**: Se estiver lidando com grandes quantidades de dados de classificação, o Adobe recomenda dividir os arquivos em arquivos de 100 MB-500 MB.
* **Evite carregar grandes quantidades de arquivos no FTP**: Se você planeja carregar os mesmos arquivos para muitos conjuntos de relatórios por FTP, limite o número de arquivos carregados de uma vez. O Adobe recomenda que o número de arquivos multiplicado pelo número de conjuntos de relatórios aplicáveis seja inferior a 1000. Se for necessário carregar 100 arquivos para 100 conjuntos de relatórios, o número total de arquivos será 10.000. Em vez de carregar todos os 100 arquivos de uma só vez, divida-o em 10 grupos de 10 arquivos de cada vez.
* **Carregue arquivos pequenos pelo importador** do navegador: Se você tiver um arquivo com menos de 1 MB (menos de 50.000 linhas), o Adobe recomenda o uso do importador do navegador. As importações de navegador são quase sempre mais rápidas que as importações FTP.
