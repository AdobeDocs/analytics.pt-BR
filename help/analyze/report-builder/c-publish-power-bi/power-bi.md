---
description: 'null'
title: Publicar no Power BI - Visão geral
uuid: ad688817-6e3c-45da-983d-48c123465309
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Publicar no Power BI - Visão geral

O Microsoft Power BI é um conjunto de painéis de análise de negócios para analisar dados e compartilhar insights. A integração do Adobe Analytics com o Power BI permite a visualização dos dados analíticos do Report Builder dentro do Microsoft Power BI e o seu fácil compartilhamento em toda a organização.

Anteriormente você, como um analista, agendaria pastas de trabalho do Report Builder para serem disseminadas via email (ou ftp). Agora você pode dar aos seus usuários comerciais acesso (de dentro de suas contas do Power BI) a dados precisos e atualizados em um ambiente baseado na Web que esteja acessível em plataformas e dispositivos.

Combinar a capacidade de geração de relatórios do Report Builder com os recursos de visualização do Power BI torna as informações mais acessíveis para todos na organização. Com o Power BI, você também pode integrar o Adobe Analytics a outras fontes de dados (por exemplo, ponto de venda, CRM) para descobrir insights, associações e oportunidades exclusivos do cliente.

![](assets/aaplusbi.png)

A integração com o Report Builder da Adobe permite

* [Publicar pastas de trabalho agendadas do Report Builder no Power BI](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)
* [Publicar todas as tabelas formatadas na pasta de trabalho como tabelas de conjuntos de dados do Power BI](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)
* [Publicar todas as solicitações do Report Builder como tabelas de conjuntos de dados do Power BI](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)

## Requisitos do sistema {#section_0B71092D853446F38FA36447DAC0D32B}

* Adobe Report Builder 5.5 [instalado](/help/analyze/report-builder/setup/t-install-arb.md)
* Ative a conta da Microsoft que permite fazer logon no Power BI

## Publicar pasta de trabalho no Power BI {#section_21CA66229EC240D49594A9A7D3FBA687}

Pastas de trabalho agendadas são planilhas Excel formatadas populadas com dados do Adobe Analytics e enviadas regularmente de forma agendada.

**Publicar a pasta de trabalho no Report Builder**

1. No Report Builder, gere e salve uma pasta de trabalho.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. No Assistente básico de agendamento, marque a caixa ao lado de **[!UICONTROL Publish Workbook to Microsoft Power BI]**.

   ![](assets/simple-schedule-wizard.png)

1. Especifique seu email e envie imediatamente ou especifique a frequência de agendamento (por hora, diariamente etc.).
1. Clique **[!UICONTROL OK]** para publicar.
1. Agora, você será solicitado a fazer logon em sua conta da Microsoft. Forneça suas credenciais.
1. A pasta de trabalho do Report Builder é agendada e publicada no Power BI.

   Com cada instância agendada e após o processo de agendamento do Report Builder ter atualizado a pasta de trabalho com dados atualizados do Analytics, ela será publicada no Microsoft Power BI.

**Exibir dados da pasta de trabalho do Report Builder no Power BI**

1. No Power BI, clique no duplo da pasta de trabalho sob o [!UICONTROL Workbooks] menu.

   ![](assets/workbooks-power-bi.png)

1. Agora você pode exibir os dados no painel da pasta de trabalho.  ![](assets/view-data-pbi.png)

1. Então é possível recortar uma área dessa pasta de trabalho de forma a incluí-la em qualquer um de seus painéis do Power BI.

## Publicar todas as tabelas formatadas na pasta de trabalho como tabelas de conjuntos de dados do Power BI {#section_7C54A54E75184DD6BAEF4ACCE241239A}

>[!NOTE] Se a pasta de trabalho contiver uma macro, a opção &quot;Publicar todas as tabelas formatadas na pasta de trabalho como tabelas de conjuntos de dados do Power BI&quot; estará desativada.

Em vez de importar a pasta de trabalho inteira, você pode importar apenas o conteúdo de todas as tabelas formatadas dentro da pasta de trabalho.

**Caso de uso**: você tem uma pasta de trabalho do Excel que extrai dados de múltiplas solicitações do Report Builder e cria uma tabela de resumo com muitas fórmulas. É possível importar somente a tabela de resumo para o Power BI e criar uma visualização para ela.

**Publicar uma tabela formatada no Report Builder**

1. No Report Builder, gere uma tabela de dados que inclua um linha de cabeçalho, seguida de uma linha de dados.
1. Selecione a tabela e selecione **[!UICONTROL Format as Table]** no [!UICONTROL Home] menu. A tabela é nomeada por padrão (Tabela 1, Tabela 2, etc.), mas é possível alterar o nome no menu [!UICONTROL Design].

1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. No Assistente básico de agendamento, clique em **[!UICONTROL Advanced Scheduling Options]**.
1. Na guia [!UICONTROL Scheduling Wizard - Advanced], na **[!UICONTROL Publishing Options]** , marque a caixa ao lado de **[!UICONTROL Publish all Formatted Tables as Power BI dataset tables]**.

   ![](assets/advanced-schedule-wizard2.png)

1. (Opcional) Você pode personalizar o nome do ativo publicado no Power BI. Isso pode ser útil se você usar o controle de versão como parte do nome da pasta de trabalho (por exemplo, myworkbook_v1.1.xlsx) e não quiser que o número da versão apareça no nome do ativo publicado do Power BI. Ele tem a vantagem adicional de que o ativo publicado não será alterado se o número da versão for alterado. ( [Especificações](/help/analyze/report-builder/c-publish-power-bi/specifications-limits.md) de Visualização aqui.)

**Exibir os dados da tabela no Power BI**

1. No Power BI, vá para o menu **[!UICONTROL Workspaces]** > **[!UICONTROL Datasets]** .

   ![](assets/datasets-menu.png)

1. Selecione o conjunto de dados que você publicou e clique no [!UICONTROL Create report] ícone ao lado dele. Observe que as tabelas aparecerão como Campos.

   ![](assets/formatted-tables.png)

1. Selecione uma tabela e suas colunas associadas.

   ![](assets/view-table-dataset.png)

1. No [!UICONTROL Visualizations] menu, você pode selecionar como visualizar uma tabela no Power BI. Por exemplo, você pode optar por apresentar seus dados como um gráfico de linhas:

   ![](assets/bi-line-graph.png)

1. Aqui, você pode criar visualizações a partir dessa tabela de conjunto de dados.

## Publicar todas as solicitações do Report Builder como tabelas de conjuntos de dados do Power BI {#section_0C26057C7DBB4068A643FDD688F6E463}

É possível transformar todas as suas solicitações em tabelas de conjuntos de dados e construir visualizações a partir delas.

>[!IMPORTANT]
>
>Se a pasta de trabalho contiver mais de 100 solicitações, apenas as primeiras 100 serão publicadas no Power BI. Além disso, para cada solicitação publicada no Power BI, somente as primeiras 10.000 linhas de dados serão publicadas. Assim, embora essas solicitações sejam entregues com êxito por meio do agendamento, o escopo da publicação no Power BI é limitado.

1. No Report Builder, abra ou crie uma pasta de trabalho com solicitações do Report Builder.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. No Assistente básico de agendamento, clique em **[!UICONTROL Advanced Scheduling Options]**.
1. Na guia [!UICONTROL Scheduling Wizard - Advanced], na **[!UICONTROL Publishing Options]** guia, marque a caixa ao lado de **[!UICONTROL Publish all Report Builder Requests as Power BI Dataset Tables]**![](assets/advanced-schedule-wizard2.png)

1. Clique em **[!UICONTROL OK]**.

**Exibir os dados das solicitações no Power BI**

Cada solicitação agendada do Report Builder será publicada como uma tabela no conjunto de dados. Cada tabela de solicitação é nomeada após a dimensão principal na solicitação e tem uma [!UICONTROL Report Suite] coluna e uma [!UICONTROL Segments] .

1. No Power BI, vá para o menu **[!UICONTROL Workspaces]** > **[!UICONTROL Datasets]** .

1. Selecione a solicitação que você publicou e clique no [!UICONTROL Create report] ícone ao lado dela.

   Observe que as solicitações aparecem como tabelas no [!UICONTROL Fields] menu.

   ![](assets/published-requests.png)

   >[!NOTE]
   >
   >Não importa como você configurou sua solicitação do Report Builder para aparecer na planilha (layout dinâmico, layout personalizado, algumas colunas invisíveis), o Report Builder sempre publicará sua solicitação no mesmo formato bidimensional com apenas uma linha de cabeçalho: Data, Dimensões, Métricas, Conjuntos de relatórios, Segmentos.

1. Observe também que existe uma tabela adicional chamada **[!UICONTROL Legend]**. Caso retire uma solicitação do contexto do Report Builder, pode ser difícil se lembrar o que cada solicitação significa. A finalidade da tabela Legenda é, por exemplo, mostrar o nome de cada solicitação na ID da tabela. Você também pode adicionar as outras colunas de Legenda para obter uma visualização completa da solicitação.

   ![](assets/legend-table.png)

