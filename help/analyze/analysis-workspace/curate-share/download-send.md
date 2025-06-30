---
description: Saiba mais sobre as várias possibilidades de baixar dados do seu projeto do Analysis Workspace.
title: Baixar Projetos E Dados Do Analysis Workspace
feature: Curate and Share
role: User, Admin
exl-id: 085013dc-8263-4fc8-9492-99f0ecadf14b
source-git-commit: 599fbea7cb22e9cd0193b56fc2fb3c506bc62949
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 27%

---


# Baixar projetos e dados

Você pode baixar projetos e dados do Analysis Workspace no seu dispositivo local. Esse download pode ser copiado com dados, um arquivo CSV (dados de valores separados por vírgula) ou um documento PDF (formato de documento portátil).

* Selecione a opção PDF se desejar que as visualizações sejam incluídas no arquivo baixado.
* Selecione as opções CSV e dados copiados se precisar apenas de dados de texto simples.

Métodos adicionais para exportar dados do Adobe Analytics estão descritos no [Guia de exportação](/help/export/home.md).

## Baixar como CSV ou PDF {#download-project}

![O menu suspenso “Projeto”, com as opções de “Baixar CSV” e “Baixar PDF” realçadas.](assets/download-project.png)

Considere o seguinte ao baixar um projeto as a PDF:

* O download pode levar vários minutos, pois o projeto é executado novamente em servidores Adobe para renderizar no formato PDF. Não saia do projeto até que ele seja baixado no navegador.  Você pode continuar a fazer alterações no projeto enquanto o download é renderizado. Se uma PDF levar mais de 5 minutos para ser renderizada, você será solicitado a [enviar um email para a PDF](../curate-share/send-schedule-files.md).
* Os downloads são renderizados como uma página única sem paginação aplicada.
* O PDF contém o que está visível na página do navegador no Analysis Workspace. É necessário dimensionar automaticamente as visualizações e painéis com tamanhos personalizados para evitar conteúdo truncado. Selecione ![Redimensionar](/help/assets/icons/Resize.svg) para dimensionar automaticamente uma visualização ou painel com tamanho personalizado.
* [Hiperlinks](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) nas tabelas de forma livre como hiperlinks no PDF baixado.



Para baixar um projeto como um arquivo PDF:

1. Selecione **[!UICONTROL Projeto]** > **[!UICONTROL Baixar o PDF]**.
Uma barra verde com a mensagem ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Seu download foi solicitado. Aguarde.]** é exibido.

1. Assim que o download estiver pronto, uma barra verde com a mensagem ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL *Name of the project *PDF estará pronta.]**aparece.
Selecione**[!UICONTROL Baixar]**para baixar a PDF. A forma como o PDF é apresentado ou baixado depende da configuração do navegador para lidar com os documentos do PDF.


Para baixar um projeto como um arquivo CSV:

* Selecione **[!UICONTROL Projeto]** > **[!UICONTROL Baixar CSV]**. O projeto é baixado diretamente para a pasta de download configurada como parte da configuração do navegador. O nome do arquivo é composto por *nome do projeto* - *nome do conjunto de relatórios* - *data*, por exemplo `Example Project - Omni-Channel - Luma - Jun 30, 2025.csv`.

## Copiar para área de transferência {#copy-data}

A opção **[!UICONTROL Copiar para a área de transferência]** do menu de contexto permite copiar dados do Analysis Workspace rapidamente e colá-los em uma ferramenta de terceiros.

* Se desejar que os dados da tabela exibidos sejam copiados, selecione o cabeçalho da tabela e selecione **Copiar dados para a área de transferência** no menu de contexto.
* Se quiser que um subconjunto dos dados seja copiado, faça uma seleção na tabela e selecione **Copiar seleção para a área de transferência** no menu de contexto.

>[!TIP]
>
>Você pode usar a tecla de atalho **_cmd + c_** (macOS) ou **_ctrl + c_** (Windows) para copiar sua seleção para a área de transferência. Em seguida, use o **_cmd + v_** (macOS) ou o **_ctrl + v_** (Windows) para colar os dados.


![A opção de “Copiar seleção para a área de transferência”. ](assets/copy-clipboard.png){zoomable="yes"}

## Baixar como CSV {#download-data}

As opções Baixar como CSV no menu de contexto permitem baixar uma tabela de dados ou a fonte de dados de qualquer visualização como CSV.

Para fazer isso:

* No cabeçalho de qualquer tabela ou visualização, selecione **[!UICONTROL Baixar dados como CSV]** no menu de contexto. Isso baixa os dados exibidos na tabela ou na fonte de dados subjacente de uma visualização como CSV. 

<!-- Only relevant as soon as CJA supports Map visualization 
  >[!NOTE]
  >
  >  Note: the Map visualization does not support this option.
-->

* Em uma tabela, selecione **[!UICONTROL Baixar seleção como CSV]** no menu de contexto. Somente a seleção é baixada com essa opção, em vez da tabela completa.

![A opção de “Baixar dados como CSV”.](assets/download-data-as-csv.png)

## Baixar itens como CSV {#download-items}

Se quiser analisar mais do que as 400 linhas de dados visíveis em uma tabela, selecione **Baixar itens como CSV (_Nome da Dimension_)** no menu de contexto do cabeçalho da tabela ou de qualquer linha. Esta opção exporta até 50 mil itens de dimensão (com base na classificação da tabela) para a dimensão selecionada, com opções de ordenação e filtros aplicados. Se você selecionar essa opção na parte superior da tabela, a primeira dimensão na tabela será exportada.

![A opção de “Baixar itens como CSV (Página)”.](assets/download-items-as-csv.png)

Nenhum limite é aplicado na tabela de forma livre. Para garantir o desempenho ideal, recomenda-se usar essa opção em tabelas com menos de 20 colunas.

>[!TIP]
>
> Se sua dimensão exceder 50.000 itens, baixe o arquivo com diferentes métricas de classificação aplicadas ou use um segmento. Por exemplo, classifique em ordem decrescente por Visitas em um download e em ordem crescente por Visitas em um segundo download. Esta dica pode ajudar você a recuperar itens mais longos.

É possível executar várias tarefas no projeto e até mesmo navegar para um novo projeto do Workspace na mesma guia enquanto o download está em andamento. O download será pausado se você abrir uma nova guia do navegador. O download será cancelado se você sair do Workspace completamente ou fechar a guia do navegador.


### Arquivo de itens baixados {#items-file}

Os seguintes recursos de uma tabela de forma livre são aplicados ao arquivo baixado:

* Todos os segmentos do painel são aplicados como filtros.
* Os detalhamentos **acima** da dimensão selecionada na tabela são aplicados como filtros acima de cada coluna.
* Detalhamentos **abaixo** da dimensão selecionada na tabela são removidos.

![O arquivo .csv baixado aberto no Excel.](assets/download-items-file.png)

### Baixar notificações {#notifications}

À medida que o arquivo é baixado, você vê as seguintes notificações:

* Um **[!UICONTROL _Nome de tabela _-_Dimension _.csv azul foi solicitado._x _% concluído]**indicando o progresso. Para cancelar o download a qualquer momento, selecione **[!UICONTROL Cancelar download]**. Selecione ![CrossSize100](/help/assets/icons/CrossSize100.svg) se desejar fechar a mensagem, o que não cancela o download.
* Uma notificação de conclusão **[!UICONTROL _do nome da tabela _-_Dimension _.csv foi baixada]**assim que o download do arquivo foi concluído. O arquivo é baixado na pasta de downloads configurada para o seu navegador.

Se solicitar mais de um download por vez, você receberá uma notificação de que cada download adicional será enfileirado até que o download anterior seja concluído.


## Perguntas frequentes {#faq}

| Pergunta | Resposta |
| --- | --- |
| Por que meu PDF baixado consiste em apenas uma página? | A funcionalidade [Baixar PDF](#download-as-csv-or-pdf) não faz a paginação de PDFs baixados. |
| Posso exportar mais de 50.000 itens com a opção **[!UICONTROL Baixar itens como CSV]**? | Embora cada download possa conter até 50.000 itens de dimensão, você pode alterar a classificação da tabela para recuperar itens mais longos ou aplicar um filtro para baixar itens mais específicos. |
| O que a opção **[!UICONTROL Copiar visualização]** faz? | Ao contrário de [!UICONTROL **Copiar dados para a área de transferência**] ou [!UICONTROL **Copiar seleção para a área de transferência**], a opção de menu de contexto **[!UICONTROL Copiar visualização]** não é uma opção de exportação. Esta opção permite [copiar uma visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu) ou [copiar um painel](/help/analyze/analysis-workspace/c-panels/panels.md#context-menu) de um local no Workspace para outro. Por exemplo, de um painel para outro no mesmo projeto ou de um projeto para outro. |



<!--

# Download 

There are several ways to export data from Analysis Workspace. The method you choose depends on what set of data you want to analyze and who needs to access it.

Exported data can be in the form of copied data, CSV, or PDF. A PDF is typically preferred if you want visualizations included in the file. CSV and copied data is preferred if you simply want plain-text data.

## Download a project as CSV or PDF {#download-project}

Consider the following when downloading projects:

* When downloading projects as a CSV or PDF, the project can be saved or unsaved when you request a project download. However, only saved projects can be [scheduled](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md). 

* When downloading projects as a PDF:
  * Downloads can take several minutes to export because the project is re-run on Adobe servers before rendering in PDF format. We recommend not leaving the project until the PDF downloads in your browser. However, you can continue to make changes to the project while you wait. If a PDF takes longer than 5 minutes to render, you will be prompted to email it instead.
  * Downloads are rendered as a single page with no pagination applied.
  * PDF renderings contain what is on the page in Workspace. If a project has custom-sized visualizations and panels, you need to change them to be auto-sized (button in top-right corner) so that there will be no truncated content.
  * Any [hyperlinks](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) that exist within freeform tables are not functional in the downloaded PDF. 

To download a project as a CSV or PDF file:

1. Do either of the following, depending on what format you want to download the project in:

   * **PDF:** Select **[!UICONTROL Project]** > **[!UICONTROL Download PDF]**.

     Choose this option if you want the downloaded file to contain all the displayed (visible) tables and visualizations in the project.

   * **CSV:** Select **[!UICONTROL Project]** > **[!UICONTROL Download CSV]**. 

     Choose this option if you want plain-text data.

   ![](assets/download-project.png)

1. (Conditional) If you chose to download a PDF, a message is shown after the project is ready to be downloaded. Click [!UICONTROL **Download**].
1. Click the **[!UICONTROL Download this file]** icon and save the file to a folder of your choice.

## Copy data to clipboard (hotkey: cmd + c) {#copy-data}

The right-click option **[!UICONTROL Copy to clipboard]** lets you quickly copy data from Workspace and paste it in a third-party tool. 

* If you want the displayed table copied, right-click the table header and choose **Copy data to clipboard**. 
* If you want a subset of data copied, make a selection in the table and then right-click > **Copy selection to clipboard**.

>[!TIP]
>
>You can use the hotkey `Ctrl+C` to copy your selection to the clipboard, then use `Ctrl+V` to paste it into a third-party tool.

![](assets/copy-selection.png)

## Download data as CSV {#download-data}

The right-click option **[!UICONTROL Download data as CSV]** allows you to download a table of data or the data source of any visualization as a CSV.

* From the header of any table or visualization, right-click and choose **[!UICONTROL Download data as CSV]**. This downloads the displayed data in the table or the underlying data source for a visualization as a CSV. 

  >[!NOTE]
  >
  >  Note: the Map visualization does not support this option.

* Within a table, right-click and choose **[!UICONTROL Download selection as CSV]**. Only the selection is downloaded with this option, as opposed to the full, displayed table.

![](assets/download-data-viz.png)

## Download items as CSV {#download-items}

If you want to analyze more than the visible 400 rows of data in a table, right-click the table header or any row and select **Download items as CSV (_Dimension name_)**. This option exports up to 50,000 dimension items (based on the table sort) for the selected dimension, with filters and segments applied. If you chose this option from the top of the table, the first dimension in the table will be exported. While no limits are enforced in the freeform table, it is recommended that the Download items option be used in tables with less than 20 columns to ensure optimal performance.

>[!TIP]
>
> If your dimension exceeds 50,000 items, download the file with different sort metrics applied or apply a filter. For example, sort descending by Visits in one download and then ascending by Visits in a second download. This tip can help you retrieve longer-tail items.

You can multi-task within the project and even navigate to a new Workspace project in the same tab while the download is in progress. The download pauses if you open a new browser tab. The download is canceled if you leave Workspace completely or close the browser tab.

![](assets/download-items.png)

### Downloaded items file 

Features of the table will be applied to the downloaded file as follows:

* All panel segments are applied as filters.
* Breakdowns **above** the selected dimension in the table are applied as filters above each column. 
* Breakdowns **below** the selected dimension in the table are removed.

In the example above, Page items are downloaded with the panel segment (New Visitors Customers) and components above (Marketing Channel = Email) applied as filters, and the components below (Mobile Device Type) removed from the downloaded CSV.

![](assets/downloaded-file.png)

### Download notifications

As the file downloads, you will see an informational notification with the progress. At any time, you can cancel the download by clicking **[!UICONTROL Cancel download]**. Closing the toast **will not** cancel the download. 

Once the file completes, you will see a completion notification and the file will download to your browser.

If you request more than one download at a time, you will receive a notification that each additional download will be queued until the prior download completes.

![](assets/toast.png)

## FAQ {#faq}

| Question | Answer |
| --- | --- |
| Why is my downloaded PDF one page? | Workspace does not paginate downloaded PDFs at this time. |
| Can I export more than 50,000 items with the "Download items as CSV" option? | While each download can contain up to 50,000 dimension items, you can change the sort of your table to retrieve longer tail items, or apply a filter to download more specific items. |
| What does **[!UICONTROL Copy visualization]** do? | Unlike [!UICONTROL **Copy data to clipboard**] or [!UICONTROL **Copy selection to clipboard**], the **[!UICONTROL Copy visualization]** right-click option is not an export option. It allows you to copy a visualization or panel from one place in Workspace to another. For example, from one panel to another in the same project, or from one project to another project. [Intra-linking video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html) |

-->