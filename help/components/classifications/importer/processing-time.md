---
title: Tempo de processamento do importador de classificação
description: Entenda o período que a Adobe processa arquivos de classificação e como minimizar o tempo de processamento.
translation-type: ht
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: ht
source-wordcount: '416'
ht-degree: 100%

---


# Tempo de processamento do importador de classificação

O tempo de processamento de um arquivo de classificação varia de acordo com o tamanho do arquivo e o número total de arquivos que a Adobe processa. As classificações normalmente não levam mais de 72 horas. No entanto, os períodos de classificação intensa que usam organizações que contam com o Adobe Analytics podem fazer com que os arquivos demorem mais de 72 horas. A Adobe vê um uso intenso de classificação nos meses que antecedem a temporada de férias.

Se quiser ver se um arquivo de classificação foi concluído, faça o seguinte:

1. Faça logon no Adobe Analytics e acesse **[!UICONTROL Admin]** > **[!UICONTROL Importador de classificação]**.
2. Selecione o conjunto de relatórios e o conjunto de dados em questão.
3. Se o processamento não tiver sido concluído, uma das mensagens a seguir será exibida:

   * ![Aviso](assets/icon_notice_notice.gif) O relatório selecionado tem uma importação de classificações em andamento.
   * ![Aviso](assets/icon_notice_notice.gif) O relatório selecionado tem dados de classificação que ainda não propagaram para todos os servidores.

Se você quiser minimizar o tempo de importação da classificação, a Adobe recomenda seguir as seguintes diretrizes:

* **Use o construtor de regras de classificação quando possível**: o construtor de regras de classificação processa os dados de forma diferente do importador de classificação tradicional. Se os dados de classificação seguirem padrões específicos, o uso desse recurso é altamente recomendado.
* **Carregar somente linhas alteradas**: essa prática reduz muito o tempo necessário para processar arquivos de classificação, pois não classifica linhas inalteradas. A Adobe recomenda fazer o upload somente das linhas alteradas.
* **Planejar com antecedência**: comece a fazer upload dos dados de classificação o mais rápido possível, especialmente se esses dados forem usados durante a temporada de festas.
* **Combinar arquivos de classificação sempre que possível**: se uma única variável tiver várias classificações, carregue um único arquivo com todas as classificações aplicáveis. Evite carregar várias classificações para a mesma variável.
* **Evitar carregar arquivos com mais de 500 MB**: se estiver lidando com grandes quantidades de dados de classificação, a Adobe recomenda dividir os arquivos em arquivos de 100 MB a 500 MB.
* **Evitar carregar grandes quantidades de arquivos no FTP**: se você planeja carregar os mesmos arquivos para muitos conjuntos de relatórios por FTP, limite o número de arquivos carregados de uma vez. A Adobe recomenda que o número de arquivos multiplicado pelo número de conjuntos de relatórios aplicáveis seja inferior a 1000. Se for necessário carregar 100 arquivos para 100 conjuntos de relatórios, o número total de arquivos será 10.000. Em vez de carregar todos os 100 arquivos de uma só vez, divida-o em 10 grupos de 10 arquivos de cada vez.
* **Carregar arquivos pequenos pelo importador de navegador**: se você tiver um arquivo com menos de 1 MB (menos de 50.000 linhas), a Adobe recomenda o uso do importador de navegador. As importações de navegador são quase sempre mais rápidas que as importações de FTP.
