---
description: Etapas que descrevem como criar uma solicitação do data warehouse.
title: Configurar opções de relatório para uma solicitação Data Warehouse
feature: Data Warehouse
exl-id: b273bddb-431c-44d9-82a5-cb088829b3a3
source-git-commit: 4e4b5e1c362778223be01f78b173a698c53f9b32
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 19%

---

# Configurar opções de relatório para uma solicitação Data Warehouse

Há várias opções de configuração disponíveis ao criar uma solicitação do data warehouse. As informações a seguir descrevem como configurar opções de relatório para a solicitação.

Para obter informações sobre como começar a criar uma solicitação, bem como links para outras opções de configuração importantes, consulte [Criar uma solicitação do data warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Para configurar opções de relatório para uma solicitação Data Warehouse:

1. Caso ainda não o tenha feito, comece criando uma solicitação no Adobe Analytics selecionando **[!UICONTROL Ferramentas]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Adicionar**].

   Para obter detalhes adicionais, consulte [Criar uma solicitação do data warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Na página Nova solicitação de Data Warehouse, selecione a variável [!UICONTROL **Opções de relatório**] guia.

   ![Guia Destino do relatório](assets/dw-report-options.png) <!-- update screenshot to include Sort by metrics -->

1. Preencha os campos a seguir:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Nome do arquivo**] | Identifica o relatório. <p>Se qualquer um dos seguintes caracteres especiais for usado no nome do arquivo, a solicitação não poderá ser salva: <code>! &quot; # $ &amp; &#39; ( ) * + , / : ; > = &lt; ? @ [ ] \ ^ ` { } \| ~</code> </p><p>O caractere % pode ser usado somente se for seguido por &quot;R&quot;, &quot;rsid&quot; ou &quot;id&quot;, da seguinte maneira: <code>%R</code>, <code>%rsid</code>, e <code>%id</code>.</p> |
   | [!UICONTROL **Anexar intervalo de datas do relatório ao nome do arquivo**] | Adiciona o intervalo de datas ao nome do arquivo do relatório. <p>Por exemplo, se você solicitar dados de 1º de maio de 2024 até 7 de maio de 2024, o nome do arquivo incluirá o intervalo de datas de 20240501 a 20240507.</p> |
   | [!UICONTROL **CSV**] | Fornece relatórios em um formato de arquivo CSV para exibição de dados em uma planilha. |
   | [!UICONTROL **Tableau (TDE)**] | Fornece relatórios em um formato de arquivo de Extração de dados do Tableau (TDE), que pode ser usado para visualizar dados e criar camadas de dados adicionais no Tableau. |
   | [!UICONTROL **Enviar relatório como arquivo compactado (ZIP)**] | Fornece relatórios em formato de arquivo compactado (ZIP). Recomendamos ativar essa opção ao usar o email como [destino do relatório](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **Retornar todas as linhas**] | Quando ativado, todas as linhas são incluídas no relatório. Desative essa opção para especificar o número de linhas a serem incluídas. |
   | [!UICONTROL **Início dos comentários do relatório**] | Adicione comentários que você deseja incluir no relatório. Os comentários aparecem no início do relatório. |
   | [!UICONTROL **Classificar por métricas**] | Fornece relatórios classificados e detalhados no Data Warehouse, classificados por valor de métrica decrescente. A classificação por métrica facilita a interpretação dos relatórios do Data Warehouse, além de facilitar a comparação deles com outros relatórios de exibição de detalhamento do Analytics.<p>Para obter mais informações, consulte [Classificar por métrica](/help/export/data-warehouse/sorting-by-metric.md).</p> |
   | [!UICONTROL **Enviar um arquivo de manifesto**] | Inclui metadados sobre os arquivos incluídos no relatório.<!-- What kind of metadata is included in the manifest file? --> |
   | [!UICONTROL **Enviar um arquivo de assinatura digital**] | Permite aos destinatários do relatório verificar se o arquivo veio do Adobe e se não foi alterado. |
   | [!UICONTROL **Enviar um arquivo vazio quando não houver dados no relatório**] | Envia um relatório mesmo quando ele não contém dados. |

   {style="table-layout:auto"}

1. Continue configurando sua solicitação do Data Warehouse no [!UICONTROL **Opções de agendamento**] guia. Para obter mais informações, consulte [Configurar opções de agendamento para uma solicitação Data Warehouse](/help/export/data-warehouse/create-request/dw-request-scheduling.md).
