---
description: O arquivo modelo para importação foi projetado para ajudar você com a importação.
seo-description: O arquivo modelo para importação foi projetado para ajudar você com a importação.
seo-title: Gerar um modelo de arquivo de importação
solution: Analytics
subtopic: Fontes de dados
title: Gerar um modelo de arquivo de importação
topic: Desenvolvedor e implementação
uuid: bcd 90 e 34-42 e 6-4 cd 1-b 67 e -87586 dea 25 d 8
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Gerar um modelo de arquivo de importação

O arquivo modelo para importação foi projetado para ajudar você com a importação.

Não é preciso se limitar às colunas definidas no modelo. É possível inserir mais colunas, conforme necessário, desde que a métrica ou a definição seja suportada pelo tipo de processamento de dados selecionado. É possível exibir as métricas e dimensões de cada tipo nas seguintes seções: [Log da Web](../../../import/c-data-sources/c-datasrc-types/datasrc-web-log.md#concept_E25D89C8B90A41FEB7DF4E936CACEE2B), [Tráfego](../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC), [Conversão](../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0), ID [da transação](../../../import/c-data-sources/c-datasrc-types/datasrc-transactionid.md#concept_A97302E9EC45468A8F30285FACE8C776), ID [do visitante](../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5), [Processamento completo](../../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED)). For example, for a traffic data type, you can add a column for any metric or dimensions listed in [Traffic](../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC).

Após sua criação, é possível baixar o modelo, inserir seus dados nele, e então carregar os dados no local FTP das Fontes de Dados. Depois de serem processados pelo servidor das Fontes de Dados, os dados importados ficam disponíveis para uso nos relatórios do Analytics.

O modelo da Fonte de Dados é um arquivo .txt que pode ser aberto em qualquer editor de texto. No entanto, é mais fácil trabalhar com o modelo no Microsoft Excel ou em outro aplicativo de planilha eletrônica. O conteúdo do modelo varia com base em suas seleções no Assistente de Ativação da Fonte de Dados.

Consulte [Referência do arquivo de importação](../../../import/c-data-sources/datasrc-template/datasrc-import-file-reference.md#concept_472095E1D011434D98A21C101A4618BD) para obter mais detalhes.

1. Logon no Analytics.
1. No título do Conjunto de Ferramentas, selecione **Admin**&gt; **[!UICONTROL Fontes de Dados]**.
1. On the **[!UICONTROL Data Sources Create]** tab, select a template category and type.
1. Review the Activation Instructions/Information, then click **[!UICONTROL Activate]**.

   Resultado da etapa 1. Selecione as opções de geração de modelo no Assistente de ativação da Fonte de dados.

   | Página do Assistente | Campo | Descrição |
   |--- |--- |--- |
   | 1 | Nome | O nome do modelo que o Analytics exibe no Gerenciador de fontes de dados. |
   | 1 | Email | O endereço de email que recebe todas as notificações relacionadas ao uso desse modelo de Fonte de Dados. |
   | 1 | Caixa de seleção das taxa associadas | Marque a caixa de seleção para indicar a aceitação das taxas associadas ao uso desse modelo de Fonte de Dados. |
   | 2 | Escolher Métricas | Selecione as métricas para importar usando esta Fonte de Dados. O Analytics recomenda determinadas métricas com base na Categoria de fonte de dados e no Tipo selecionado na Etapa 3. Para especificar uma métrica diferente, digite o nome em um campo em branco e marque a caixa de seleção para habilitá-la. |
   | 3 | Mapear Métricas | Selecione um Evento do Analytics para receber cada métrica importada selecionada na página 2 do Assistente. Esses eventos (que você nomeou de modo a corresponder aos dados métricos importados que receberão pelas Fontes de Dados) devem ser novos e não devem estar atribuídos.  Se uma variável eVar, Produto ou Código de Acompanhamento for uma variável de destino, e os valores carregados coincidirem com os valores obtidos, os eventos carregados basicamente adicionam métricas aos valores existentes. Por exemplo, você pode criar uma métrica "Pedidos off-line" em uma dimensão de dados de Produtos que já tem Exibições de Produto, Check-outs e Pedidos como métricas existentes. |
   | 4 | Escolher Dimensão de Dados | Selecione as dimensões de dados para analisar as métricas importadas nesta Fonte de Dados. O Analytics recomenda determinadas dimensões de dados com base no Tipo de fonte de dados selecionado na Etapa 3. Para especificar uma dimensão de dados diferente, digite o nome em um campo em branco e marque a caixa de seleção para habilitá-la. |
   | 5 | Mapear Dimensões de Dados | Selecione um relatório padrão ou eVar para receber cada dimensão de dados importada selecionada na página 4 do Assistente. |

1. Após a criação do modelo, copie os dados nas colunas apropriadas do modelo de Fontes de dados, respeitando o formato dos dados exigido para a coluna de dados.

   Resultado da etapa 1. Salve o arquivo de Fontes de dados, usando uma convenção de nomenclatura de sua escolha. O Adobe recomenda usar uma convenção de nomenclatura consistente para todos os arquivos de Fontes de Dados. Use uma extensão de arquivo comum, como .txt ou .tsv (ou não use nenhuma extensão).

