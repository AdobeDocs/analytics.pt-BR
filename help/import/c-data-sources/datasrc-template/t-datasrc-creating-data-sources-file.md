---
description: O arquivo modelo para importação foi projetado para ajudar você com a importação.
subtopic: Data sources
title: Criar um modelo de arquivo de importação
topic: Developer and implementation
uuid: bcd90e34-42e6-4cd1-b67e-87586dea25d8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Criar um modelo de arquivo de importação

O arquivo modelo para importação foi projetado para ajudar você com a importação.

Não é preciso se limitar às colunas definidas no modelo. É possível inserir mais colunas, conforme necessário, desde que a métrica ou a definição seja suportada pelo tipo de processamento de dados selecionado. É possível exibir as métricas e dimensões de cada tipo nas seguintes seções: [Registro da Web](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md), [Tráfego](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md), [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md), [ID de transação](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md), [ID do visitante](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md), [Processamento completo](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)). Por exemplo, em um tipo de dados de tráfego, é possível adicionar uma coluna a qualquer métrica ou dimensão descrita em [Tráfego](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md).

Após sua criação, é possível baixar o modelo, inserir seus dados nele, e então carregar os dados no local FTP das Fontes de Dados. Depois de processados pelo servidor das Fontes de Dados, os dados importados são disponibilizados para o uso nos relatórios do Analytics.

O modelo da Fonte de Dados é um arquivo .txt que pode ser aberto em qualquer editor de texto. No entanto, é mais fácil trabalhar com o modelo no Microsoft Excel ou em outro aplicativo de planilha eletrônica. O conteúdo do modelo varia com base em suas seleções no Assistente de Ativação da Fonte de Dados.

Consulte [Referência do arquivo de importação](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md) para obter mais detalhes.

1. Logon no Analytics.
1. No título do Conjunto de Ferramentas, selecione **[!UICONTROL Admin]**> **[!UICONTROL Fontes de Dados]**.
1. Na guia **[!UICONTROL Criar das fontes de dados]**, selecione uma categoria e um tipo de modelo.
1. Revise as Instruções/informações de ativação, e clique em **[!UICONTROL Ativar]**.

   Resultado da etapa 1. Selecione as opções de geração de modelo no Assistente de ativação da Fonte de dados.

   | Página do Assistente | Campo | Descrição |
   |--- |--- |--- |
   | 1 | Nome | O nome do modelo que o Analytics exibe no Gerenciador da fonte de dados. |
   | 1 | Email | O endereço de email que recebe todas as notificações relacionadas ao uso desse modelo de Fonte de Dados. |
   | 1 | Caixa de seleção das tarifas associadas | Marque a caixa de seleção para indicar que aceita as tarifas associadas à utilização desse modelo de Fonte de Dados. |
   | 2 | Escolher Métricas | Selecione as métricas para importar usando esta Fonte de Dados. O Analytics recomenda determinadas métricas com base na Categoria e no Tipo de fonte de dados selecionadas na etapa 3.  Para especificar uma métrica diferente, digite o nome em um campo em branco e marque a caixa de seleção para habilitá-la. |
   | 3 | Mapear Métricas | Selecione um evento do Analytics para receber cada métrica importada selecionada na página 2 do Assistente.  Esses eventos (que você nomeou de modo a corresponder aos dados métricos importados que receberão pelas Fontes de Dados) devem ser novos e não devem estar atribuídos.  Se uma variável eVar, Produto ou Código de rastreamento for uma variável de destino, e os valores carregados coincidirem com os valores obtidos, os eventos carregados basicamente adicionam métricas aos valores existentes. Por exemplo, você pode criar uma métrica &quot;Pedidos offline&quot; em uma dimensão de dados de Produtos que já tem Exibições de produto, Check-outs e Pedidos como métricas existentes. |
   | 4 | Escolher Dimensão de Dados | Selecione as dimensões de dados para analisar as métricas importadas nesta Fonte de Dados. O Analytics recomenda determinadas dimensões de dados com base no Tipo de fonte de dados selecionado na etapa 3.  Para especificar uma dimensão de dados diferente, digite o nome em um campo em branco e marque a caixa de seleção para habilitá-la. |
   | 5 | Mapear Dimensões de Dados | Selecione um relatório padrão ou eVar para receber cada dimensão de dados importada selecionada na página 4 do Assistente. |

1. Após a criação do modelo, copie os dados nas colunas apropriadas do modelo de Fontes de dados, respeitando o formato dos dados exigido para a coluna de dados.

   Resultado da etapa 1. Salve o arquivo de Fontes de dados, usando uma convenção de nomenclatura de sua escolha. O Adobe recomenda usar uma convenção de nomenclatura consistente para todos os arquivos de Fontes de Dados. Use uma extensão de arquivo comum, como .txt ou .tsv (ou não use uma extensão).

