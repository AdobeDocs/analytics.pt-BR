---
description: Etapas que descrevem como criar uma solicitação do Data Warehouse.
title: Configurar opções de relatório para uma solicitação Data Warehouse
feature: Data Warehouse
source-git-commit: 42c95198a4d4389308c78c312b5bb37572350cc1
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 16%

---

# Configurar opções de relatório para uma solicitação Data Warehouse

{{release-limited-testing}}

Há várias opções de configuração disponíveis ao criar uma solicitação do Data Warehouse. As informações a seguir descrevem como configurar opções de relatório para a solicitação.

Para obter informações sobre como começar a criar uma solicitação, bem como links para outras opções de configuração importantes, consulte [Criar uma solicitação Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Para configurar opções de relatório para uma solicitação Data Warehouse:

1. Comece a criar uma solicitação no Adobe Analytics selecionando **[!UICONTROL Ferramentas]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Adicionar**].

   Para obter detalhes adicionais, consulte [Criar uma solicitação Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Na página Nova solicitação de Data Warehouse, selecione a variável [!UICONTROL **Opções de relatório**] guia.

   ![Guia Destino do relatório](assets/dw-report-options.png) <!-- update screenshot to include Sort by metrics -->

1. Preencha os campos a seguir:

   | Opção | Função |
   |---------|----------|
   | Nome do arquivo | Identifica o relatório. |
   | Anexar intervalo de datas do relatório ao nome do arquivo | Adiciona o intervalo de datas ao nome do arquivo do relatório. <p>Por exemplo, se você solicitar dados de 1º de maio de 2024 até 7 de maio de 2024, o nome do arquivo incluirá o intervalo de datas de 20240501 a 20240507.</p> |
   | CSV | Fornece relatórios em um formato de arquivo CSV para exibição de dados em uma planilha. |
   | Tableau (TDE) | Fornece relatórios em um formato de arquivo de Extração de dados do Tableau (TDE), que pode ser usado para visualizar dados e criar camadas de dados adicionais no Tableau. |
   | Enviar relatório como arquivo compactado (ZIP) | Fornece relatórios em formato de arquivo compactado (ZIP). Recomendamos ativar essa opção ao usar o email como [destino do relatório](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | Número de linhas na tabela | O número de linhas que podem ser incluídas no relatório. Use 0 para incluir todas as linhas (esta é a seleção padrão). <!-- when would you want to limit the rows? To improve performance? Do we have recommendations? --> |
   | Comentários | Adicione comentários que você deseja incluir no relatório. Os comentários aparecem no início do relatório. |
   | Classificar por métricas | Oferece relatórios classificados e detalhados no Data Warehouse, organizados pelo valor de métrica decrescente. A classificação por métrica facilita a interpretação dos relatórios do Data Warehouse, além de facilitar a comparação deles com outros relatórios de exibição de detalhamento do Analytics.<p>Para obter mais informações, consulte [Classificar por métrica](/help/export/data-warehouse/sorting-by-metric.md).</p> |
   | Enviar arquivo de manifesto | Inclui metadados sobre os arquivos incluídos no relatório.<!-- What kind of metadata is included in the manifest file? --> |
   | Enviar arquivo de assinatura digital | Permite aos destinatários do relatório verificar se o arquivo veio do Adobe e se não foi alterado. |
   | Enviar um arquivo vazio quando não houver dados no relatório | Envia um relatório mesmo quando ele não contém dados. |

   {style="table-layout:auto"}

1. Continue configurando sua solicitação do Data Warehouse no [!UICONTROL **Opções de agendamento**] guia. Para obter mais informações, consulte [Configurar opções de agendamento para uma solicitação Data Warehouse](/help/export/data-warehouse/create-request/dw-request-scheduling.md).