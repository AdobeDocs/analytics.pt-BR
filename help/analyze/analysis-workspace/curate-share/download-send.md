---
description: É possível baixar dados do Analysis Workspace copiando-os ou em formatos PDF e CSV.
title: Baixar arquivos PDF ou CSV
feature: Curate and Share
role: User, Admin
exl-id: 085013dc-8263-4fc8-9492-99f0ecadf14b
source-git-commit: 99f9a1d1fa6238918c1566f64df41418cd13fa0e
workflow-type: tm+mt
source-wordcount: '1007'
ht-degree: 66%

---

# Baixar arquivos PDF ou CSV

Há várias maneiras de exportar dados do Analysis Workspace. O método escolhido depende do conjunto de dados que você deseja analisar e de quem precisa acessá-lo.

Os dados exportados podem estar no formato de dados copiados, CSV ou PDF. Um PDF geralmente é melhor se você quiser que visualizações sejam incluídas no arquivo. CSV e dados copiados são preferidos se você simplesmente quiser dados de texto simples.

## Baixar um projeto como CSV ou PDF {#download-project}

1. Siga um destes procedimentos, dependendo do formato em que você deseja baixar o projeto:

   * **PDF:** Selecionar **[!UICONTROL Projeto]** > **[!UICONTROL Baixar PDF]**.

      Escolha essa opção se desejar que o arquivo baixado contenha todas as tabelas e visualizações exibidas (visíveis) no projeto.

   * **CSV:** Selecionar **[!UICONTROL Projeto]** > **[!UICONTROL Baixar CSV]**.

      Escolha essa opção se desejar dados de texto simples.
   ![](assets/download-project.png)

1. (Condicional) Se você optar por baixar um PDF, uma mensagem será exibida depois que o projeto estiver pronto para ser baixado. Clique em [!UICONTROL **Baixar**].

Para downloads de projetos, lembre-se:

* O projeto pode ser salvo ou não ao solicitar um download do projeto. No entanto, somente os projetos salvos podem ser [agendados](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html?lang=pt-BR).
* Os PDFs baixados no navegador podem levar vários minutos para serem exportados porque o projeto é executado novamente em servidores da Adobe antes da renderização no formato PDF. Recomendamos não sair do projeto até que o PDF seja baixado no navegador. No entanto, você pode continuar fazendo alterações no projeto enquanto espera. Se um PDF demorar mais de 5 minutos para ser renderizado, você será solicitado a enviá-lo por email.
* Os downloads de PDF são renderizados como uma página única sem paginação aplicada.
* Quando um projeto é renderizado para PDF, renderizamos o que está na página. Se um projeto tiver visualizações e painéis com tamanhos personalizados, é necessário alterá-los para terem tamanhos automáticos (botão no canto superior direito) para que não haja truncamento de conteúdo.

## Copiar dados para a área de transferência (tecla de atalho: Ctrl + C) {#copy-data}

A opção de clique com o botão direito **[!UICONTROL Copiar para a área de transferência]** O permite copiar dados do Workspace rapidamente e colá-los em uma ferramenta de terceiros.

* Se desejar que a tabela exibida seja copiada, clique com o botão direito do mouse no cabeçalho da tabela e escolha **Copiar dados para a área de transferência**.
* Se quiser que um subconjunto de dados seja copiado, faça uma seleção na tabela e clique com o botão direito do mouse em > **Copiar seleção para a área de transferência**.

>[!TIP]
>
>Você pode usar a tecla de atalho `Ctrl+C` para copiar sua seleção para a área de transferência, use `Ctrl+V` para colá-lo em uma ferramenta de terceiros.

![](assets/copy-selection.png)

## Baixar dados como CSV {#download-data}

A opção de clique com o botão direito **[!UICONTROL Baixar dados como CSV]** permite baixar uma tabela de dados ou a fonte de dados de qualquer visualização como CSV.

* No cabeçalho de qualquer tabela ou visualização, clique com o botão direito do mouse e escolha **[!UICONTROL Baixar dados como CSV]**. Isso baixa os dados exibidos na tabela ou na fonte de dados subjacente de uma visualização como CSV.

   >[!NOTE]
   >
   >  Observação: a visualização de mapa não é compatível com essa opção.

* Em uma tabela, clique com o botão direito do mouse e escolha **[!UICONTROL Baixar seleção como CSV]**. Somente a seleção é baixada com essa opção, em vez da tabela totalmente exibida.

![](assets/download-data-viz.png)

## Baixar itens como CSV {#download-items}

Se quiser analisar mais do que as 400 linhas de dados visíveis em uma tabela, clique com o botão direito do mouse no cabeçalho da tabela ou em qualquer linha e selecione **Baixar itens como CSV (_nome do Dimension_)**. Essa opção exporta até 50.000 itens de dimensão (com base na classificação da tabela) para a dimensão selecionada, com filtros e segmentos aplicados. Se você escolher essa opção na parte superior da tabela, a primeira dimensão na tabela será exportada. Embora nenhum limite seja empregado na tabela de forma livre, é recomendável que a opção Baixar itens seja usada em tabelas com menos de 20 colunas para garantir o desempenho ideal.

>[!TIP]
>
> Se sua dimensão exceder 50.000 itens, baixe o arquivo com métricas de classificação diferentes aplicadas ou use um filtro. Por exemplo, classifique em ordem decrescente por Visitas em um download e em ordem crescente por Visitas em um segundo download. Esta dica pode ajudar você a recuperar itens mais longos.

É possível executar várias tarefas no projeto e até mesmo navegar para um novo projeto do Workspace na mesma guia enquanto o download está em andamento. O download é pausado se você abrir uma nova guia do navegador. O download será cancelado se você sair do Workspace completamente ou fechar a guia do navegador.

![](assets/download-items.png)

### Arquivo de itens baixados

Os recursos da tabela serão aplicados ao arquivo baixado da seguinte maneira:

* Todos os segmentos do painel são aplicados como filtros.
* Os detalhamentos **acima** da dimensão selecionada na tabela são aplicados como filtros acima de cada coluna.
* Detalhamentos **abaixo** da dimensão selecionada na tabela são removidos.

No exemplo acima, os itens de Página são baixados com o segmento do painel (Novos clientes visitantes), os componentes acima (Canal de marketing = Email) são aplicados como filtros e os componentes abaixo (Tipo de dispositivo móvel) são removidos do CSV baixado.

![](assets/downloaded-file.png)

### Baixar notificações

À medida que o arquivo for baixado, você verá uma notificação informativa com o progresso. A qualquer momento, você pode cancelar o download clicando em **[!UICONTROL Cancelar download]**. Fechar a janela **não** cancela o download.

Quando o arquivo for concluído, você verá uma notificação de conclusão e o arquivo será baixado no navegador.

Se solicitar mais de um download por vez, você receberá uma notificação de que cada download adicional será enfileirado até que o download anterior seja concluído.

![](assets/toast.png)

## Perguntas frequentes {#faq}

| Pergunta | Resposta |
| --- | --- |
| Por que meu PDF baixado tem apenas uma página? | O Workspace não faz a paginação de PDFs baixados no momento. |
| Posso exportar mais de 50.000 itens com a opção &quot;Baixar itens como CSV&quot;? | Embora cada download possa conter até 50.000 itens de dimensão, você pode alterar a classificação da tabela para recuperar itens mais longos ou aplicar um filtro para baixar itens mais específicos. |
| O que a opção **[!UICONTROL Copiar visualização]** faz? | Ao contrário [!UICONTROL **Copiar dados para a área de transferência**] ou [!UICONTROL **Copiar seleção para a área de transferência**], o **[!UICONTROL Copiar visualização]** clicar com o botão direito do mouse não é uma opção de exportação. Ela permite copiar uma visualização ou painel de um local no Workspace para outro. Por exemplo, de um painel para outro no mesmo projeto ou de um projeto para outro. [Vídeo intravinculante](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html?lang=pt-BR) |
