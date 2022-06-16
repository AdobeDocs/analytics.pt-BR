---
title: Configurações do conjunto de classificações
description: Crie ou edite um Conjunto de classificações.
exl-id: abf00508-5dde-4669-bf94-5eb4754888cc
source-git-commit: c849f216f8dda83070fc3f8d8b1c25fba4d2786a
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---

# Configurações do conjunto de classificações

Configure um conjunto de classificações, faça upload de dados ou baixe dados.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de classificações]** > **[!UICONTROL Conjuntos]** > Clique no nome do Conjunto de classificações desejado

Ao editar um Conjunto de classificações, duas guias estão disponíveis; **[!UICONTROL Esquema]** e **[!UICONTROL Configurações]**.

## Configurações 

Os seguintes campos estão disponíveis na variável [!UICONTROL Configurações] e pode ser editado:

* **[!UICONTROL Nome]**: O nome do Conjunto de classificações.
* **[!UICONTROL Descrição]**: A descrição do Conjunto de classificações.
* **[!UICONTROL Nome do proprietário]**: O nome do proprietário.
* **[!UICONTROL Email do proprietário]**: O endereço de email do proprietário.
* **[!UICONTROL Notificação de problemas]**: Uma lista delimitada por vírgulas de endereços de email que são notificados sobre problemas com este Conjunto de classificações.
* **[!UICONTROL Tags]**: Adicione uma ou mais tags ao(s) conjunto(s) de classificação selecionado(s), o que permite organizar ou agrupar conjuntos de classificação para facilitar a localização no futuro.

Campos adicionais estão disponíveis para fins informativos e não podem ser editados:

* **[!UICONTROL Tipo]**: O tipo de classificação entre [!UICONTROL Primário] e [!UICONTROL Pesquisa]. As classificações primárias são normalmente usadas.
* **[!UICONTROL Subscrições]**: O Conjunto de relatórios e a variável à qual o Conjunto de classificações se aplica. Somente um conjunto de relatórios é compatível com um determinado conjunto de classificações no momento; o suporte para vários conjuntos de relatórios está planejado.

## Esquema

Exibir dimensões de classificação atualmente configuradas para esta assinatura. Os seguintes botões estão disponíveis:

* **[!UICONTROL Upload]**: Faça upload manual dos dados de classificação de uma ou mais dimensões de classificação. Arquivos JSON, CSV, TSV e TAB são compatíveis. O upload de um arquivo válido mostra uma pré-visualização de tabela de dados a serem classificados.
   * **[!UICONTROL Codificação de arquivo]**: Selecione a codificação de arquivo correta usando essa lista suspensa. As opções válidas incluem [!UICONTROL UTF-8] e [!UICONTROL Latim1].
   * **[!UICONTROL Delimitador de lista]**: Selecione o delimitador de lista correto. Se estiver usando um arquivo baixado ou um arquivo de modelo, verifique se a variável [!UICONTROL Delimitador de lista] corresponde ao [!UICONTROL Delimitador de lista] quando o arquivo foi baixado.
   * **[!UICONTROL Aplicar]**: Salve os dados de classificação carregados no Conjunto de classificações.

   ![Upload do Conjunto de classificações](../assets/classification-set-upload.png)

* **[!UICONTROL Baixar]**: Baixe os valores da chave e suas colunas de classificação.
   * **[!UICONTROL Linhas]**: O número máximo de linhas a serem incluídas no arquivo de download.
   * **[!UICONTROL Fazer download de linhas entre]**: Um seletor de datas do calendário que permite filtrar os valores principais por quando eles aparecem no relatório. Se um valor principal não tiver sido coletado nesse intervalo de datas, ele não aparecerá no arquivo baixado.
   * **[!UICONTROL Dados retornados]**: Uma lista suspensa que permite filtrar os valores principais incluídos no arquivo baixado com base nos dados de classificação associados.
      * **[!UICONTROL Todos os valores classificados]**: Inclui linhas nas quais os dados de classificação estão incluídos em pelo menos uma coluna.
      * **[!UICONTROL Todos os valores não classificados]**: Inclui linhas nas quais os dados de classificação estão ausentes em pelo menos uma coluna.
   * **[!UICONTROL Formato de arquivo]**: Lista suspensa que determina o formato de arquivo no qual o arquivo de download está. As opções incluem [!UICONTROL JSON], [!UICONTROL Valores separados por vírgula]e [!UICONTROL Valores separados por tabulação do Excel].
   * **[!UICONTROL Codificação de arquivo]**: Lista suspensa que determina a codificação do arquivo. As opções incluem [!UICONTROL UTF-8] e [!UICONTROL Latim1]. UTF-8 é recomendado.
   * **[!UICONTROL Delimitadores de lista]**: Lista suspensa que determina o delimitador da lista que separa as colunas de classificação em cada linha.

   ![Download do conjunto de classificações](../assets/classification-set-download.png)

* **[!UICONTROL Modelo]**: Baixe um arquivo de modelo. Esse arquivo é semelhante ao [!UICONTROL Baixar] , exceto que não contém dados de classificação ou valores-chave.
   * **[!UICONTROL Formato de arquivo]**: Lista suspensa que determina o formato de arquivo no qual o arquivo de modelo está. As opções incluem [!UICONTROL Valores separados por vírgula]e [!UICONTROL Valores separados por tabulação do Excel].
   * **[!UICONTROL Codificação de arquivo]**: Lista suspensa que determina a codificação do arquivo. As opções incluem [!UICONTROL UTF-8] e [!UICONTROL Latim1]. UTF-8 é recomendado.
   * **[!UICONTROL Delimitadores de lista]**: Lista suspensa que determina o delimitador da lista que separa as colunas de classificação em cada linha.
* **[!UICONTROL Histórico de tarefas]**: Um link de atalho que direciona você ao [Gerente de emprego](job-manager.md), mostrando trabalhos somente para esse Conjunto de Classificações.

   ![Modelo do Conjunto de classificações](../assets/classification-set-template.png)
