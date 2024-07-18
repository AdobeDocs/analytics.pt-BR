---
description: Uma visão geral de como usar relatórios padrão no Analysis Workspace.
title: Usar relatórios
feature: Analysis Workspace
role: User, Admin
exl-id: 0d43fa5e-9167-4af7-891d-e49b0249bca2
source-git-commit: 3d5a940386cf1ba2b869fd1b76f291cc2e1e4046
workflow-type: tm+mt
source-wordcount: '1520'
ht-degree: 100%

---

# Utilização de relatórios pré-criados

Os relatórios pré-criados no Analysis Workspace fornecem insights rápidos sobre os cenários de relatórios mais comuns. A seguir estão alguns exemplos de perguntas que você pode responder com relatórios pré-criados:

* Quantas pessoas visitam o seu site
* Quantos desses visitantes são visitantes únicos (contados somente uma vez)
* Como eles chegaram até o site (se os visitantes seguiram um link ou chegaram diretamente ao site)
* Quais palavras-chave os visitantes usaram para pesquisar pelo conteúdo do site
* Por quanto tempo os visitantes permaneceram em uma página específica ou no site
* Em quais links o visitante clicou e quando ele deixou o site
* Quais canais de marketing são os mais eficazes na geração de receita ou eventos de conversão
* Quanto tempo foi utilizado ao assistir a um vídeo
* Quais navegadores e dispositivos eles utilizaram para visitar seu site

As informações a seguir descrevem como acessar e utilizar relatórios pré-criados da guia [!UICONTROL Relatórios] no Analysis Workspace.

## Acesso e execução de um relatório

1. No Adobe Analytics, selecione a guia [!UICONTROL **Espaço de trabalho**].

1. Selecione [!UICONTROL **Relatórios**].

   ![Guia Relatórios](assets/view-prebuilt-reports.png)

1. No campo de pesquisa, comece digitando o nome do relatório que deseja localizar, em seguida, selecione-o na lista de relatórios. Também é possível pesquisar a lista de relatórios por propriedade, eVar e número do evento. <!-- still true? -->

   Ou

   Selecione a categoria do relatório que deseja exibir e selecione o relatório na lista de relatórios.

   >[!TIP]
   >
   >   Para navegar no menu utilizando as teclas de seta, pressione a tecla Barra (/) e, em seguida, pressione a tecla Seta para baixo. Pressione Enter para carregar o relatório selecionado.

Para obter uma lista de relatórios disponíveis, consulte a seção [Relatórios disponíveis](#available-reports) abaixo.

## Salvar um relatório {#use-reports}

Se você sair de um relatório depois de fazer alterações, será solicitado que salve ou descarte as alterações. Salvar as alterações de um relatório o salva como um novo projeto.

1. Acesse a guia [!UICONTROL **Relatórios**].
1. Selecione os relatórios que deseja exibir. Por exemplo, em [!UICONTROL **Mais popular**], selecione o relatório [!UICONTROL **Páginas**].

   ![Relatório de páginas](assets/pages-report.png)

1. O Relatório de páginas, conforme exibido no Analysis Workspace, mostra duas [visualizações](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ([Gráfico de barras](/help/analyze/analysis-workspace/visualizations/bar.md) e [Número do resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)) e uma [Tabela de forma livre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md). A métrica usada é Ocorrências.
1. Siga um destes procedimentos:

   * Exiba o relatório.
   * Arraste um ou mais segmentos para a zona de destino Segmentos na parte superior. Por exemplo, arraste o segmento [!UICONTROL **Clientes móveis**] e veja os resultados.
   * Altere o intervalo de datas acessando o calendário no canto superior direito.
   * Adicione detalhamentos de dimensão, arraste outras métricas e faça personalizações gerais no relatório para atender às suas necessidades.

1. (Opcional) Salve o relatório como um projeto selecionando [!UICONTROL **Projeto**] > [!UICONTROL **Salvar**].

   O relatório é salvo como um novo projeto e não modifica o relatório existente. Para obter mais informações sobre como salvar um relatório como projeto, consulte [Salvar projetos](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md).

## Relatórios disponíveis

A tabela a seguir contém a lista completa dos relatórios pré-criados disponíveis.

Alguns dos relatórios pré-criados mais populares incluem: fluxo, fallout, canal de marketing e relatórios em tempo real.

| Item de menu | Relatórios neste item de menu |
| --- | --- |
| **[!UICONTROL Mais populares]** | <ul><li>Tutorial de treinamento (modelo do Workspace pré-existente)</li><li>Páginas (quais são minhas páginas principais?)</li><li>Visualizações de página (quantas visualizações de página estou gerando?)</li><li>Visitas (quantas visitas estou recebendo?)</li><li>Visitantes (quantos visitantes estou recebendo?)</li><li>Métricas principais (qual é o desempenho das minhas métricas mais importantes?)</li><li>Seções do site (quais seções do meu site geraram mais visualizações de página?)</li><li>Tempo real (quais são as tendências no meu site e por quê?)</li><li>Próxima página (quais são as próximas páginas que meus visitantes acessam?)</li><li>Página anterior (quais são as páginas anteriores que meus visitantes acessaram?)</li><li>Campanhas (que campanhas estão gerando minhas métricas principais?)</li><li>Produtos (que produtos estão acionando minhas métricas principais?)</li><li>Canal de último contato (qual canal de último contato tem melhor desempenho?</li><li>Detalhe do canal de último contato (qual canal de último contato específico está superando outros?)</li><li>Receita (como está o desempenho da minha receita?)</li><li>Pedidos (como está o desempenho dos meus pedidos?)</li><li>Unidades (quantas unidades estou vendendo?)</li></ul> |
| **[!UICONTROL Engajamento]** | <ul><li>Métricas principais (qual é o desempenho das minhas métricas mais importantes?)</li><li>Visualizações de página (quantas visualizações de página estou gerando?)</li><li>Páginas (quais são minhas páginas principais?)</li><li>Visitas (quantas visitas estou recebendo?)</li><li>Visitantes (quantos visitantes estou recebendo?)</li><li>Tempo gasto por visita (quanto tempo meus usuários gastam por visita?)</li><li>Tempo antes do evento (quanto tempo meus usuários gastam antes de um evento bem-sucedido?)</li><li>Seções do site (quais seções do meu site geraram mais visualizações de página?)</li><li>Consumo de conteúdo da Web (qual conteúdo é mais consumido e envolve os usuários?)</li><li>Consumo de conteúdo de mídia (qual conteúdo é mais consumido e envolve os usuários?)</li><li>Fluxo da página seguinte e anterior (quais são/foram os caminhos anteriores/seguintes que meus visitantes tomaram?)</li><li>Fallout (onde estou vendo fallout em minhas propriedades digitais?)</li><li>Análise entre dispositivos (usando análise entre dispositivos no Analysis Workspace)</li><li>Retenção da Web (quem são meus usuários fiéis e o que eles fazem?)</li><li>Consumo de áudio de mídia (quais são as tendências e as métricas principais do consumo de áudio?)</li><li>Recenticidade de mídia, frequência, fidelidade (quem são meus leitores fiéis?)</li><li>Análise de página > Recarregamentos (quais páginas geram mais recarregamentos?)</li><li>Análise de página > Tempo gasto na página (quanto tempo meus usuários gastam nas páginas?)</li><li>Entradas &amp; saídas > Páginas de entrada (quais são minhas páginas de entrada principais?)</li><li>Entradas &amp; saídas > Páginas de entrada originais (de qual página meu visitante veio originalmente?)</li><li>Entradas &amp; saídas > Visitas em única página (quais páginas geraram mais visitas em única página?)</li><li>Entradas &amp; saídas > Páginas de saída (quais são minhas páginas de saída principais?)</li><li>Análise da página > Resumo da página</li></ul> |
| **[!UICONTROL Conversão]** | <ul><li>Produtos > Produtos (quais produtos estão impulsionando minhas métricas principais?)</li><li>Produtos > Desempenho do produto (quais produtos estão tendo o melhor desempenho?)</li><li>Produtos > Categorias (quais são minhas categorias de produtos com melhor desempenho?)</li><li>Carrinho de compras > Carrinhos (quantos usuários adicionaram um produto ao carrinho?)</li><li>Carrinho de compras > Visualizações do carrinho (quantas vezes meus visitantes visualizaram os carrinhos?)</li><li>Carrinho de compras > Adições ao carrinho (com que frequência os usuários adicionam um produto ao carrinho?)</li><li>Carrinho de compras > Remoções do carrinho (com que frequência os usuários removem um produto do carrinho?)</li><li>Compras > Receita (como minha receita está funcionando?)</li><li>Compras > Pedidos (como meus pedidos estão se saindo?)</li><li>Compras > Unidades (quantas unidades estou vendendo?)</li><li>[Magento: marketing e comércio](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#commerce)</li></ul> |
| **[!UICONTROL Público-alvo]** | <ul><li>Métrica de pessoas (quantas pessoas interagem com minha marca?)</li><li>Perfil do visitante > Visão geral de localização (quais locais estão promovendo mais uso entre os usuários)</li><li>Perfil do visitante > Geosegmentação > Geo Counties, Geo US States, Geo Regions, Geo Cities, Geo US DMA (quais regiões meus usuários estão visitando?)</li><li>Perfil do visitante > Idiomas (qual idioma meus usuários preferem?)</li><li>Perfil do visitante > Fusos horários (em quais fusos horários meus usuários estão visitando?)</li><li>Perfil do visitante > Domínios (quais ISPs meus visitantes estão usando para acessar meu site?)</li><li>Perfil do visitante > Domínios de nível superior (quais domínios estão direcionando o tráfego para meu site?)</li><li>Perfil do visitante > Tecnologia > Visão geral da tecnologia (que tecnologias as pessoas estão usando para acessar meu site?)</li><li>Perfil do visitante > Tecnologia > Navegadores, tipo de navegador, largura do navegador, altura do navegador (qual navegador da empresa, versão do navegador e sua largura e altura as pessoas estão usando para acessar meu site?)</li><li>Perfil do visitante > Tecnologia > Sistema operacional, Tipos de sistema operacional (qual SO e qual versão dele meus visitantes usam?)</li><li>Perfil do visitante > Tecnologia > Operadora de celular (quais operadoras de celular meus visitantes usam para acessar meu site?)</li><li>Retenção de visitante > Frequência de retorno (quanto tempo passa entre a visita atual do usuário e as visitas anteriores?)</li><li>Retenção de visitante > Visitas de retorno (quantas de minhas visitas são usuários recorrentes?)</li><li>Retenção de visitante > Número da visita (que contém o número da visita que direciona a maioria das minhas métricas principais)</li><li>Retenção de visitante > Ciclo de vendas > Fidelidade do cliente (a qual segmento de fidelidade meus usuários pertencem?)</li><li>Retenção de visitante > Ciclo de vendas > Dias antes da primeira compra (quantos dias se passaram entre a primeira visita de meus usuários e a primeira compra?)</li><li>Retenção de visitante > Ciclo de vendas > Dias desde a última compra (quantos dias se passaram entre a visita atual de meus usuários e a última compra? )</li><li>Retenção de visitante > Dispositivo móvel > Dispositivos e tipos de dispositivo (quais dispositivos e tipos de dispositivo meus visitantes estão usando?)</li><li>Retenção de visitante > Dispositivo móvel > Fabricante (qual fabricante de dispositivo móvel meus visitantes usam?)</li><li>Retenção de visitante > Dispositivo móvel > Tamanho da tela, Altura da tela, Largura da tela (que tamanho/altura/largura da tela móvel meus visitantes têm?)</li><li>Retenção de visitante > Dispositivo móvel > [Uso de aplicativo móvel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#mobile)</li><li>Retenção de visitante > Dispositivo móvel > [Jornadas de aplicativo móvel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#mobile)</li><li>Retenção de visitante > Dispositivo móvel > [Métricas de aplicativo móvel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#mobile)</li><li>Retenção de visitante > Dispositivo móvel > [Mensagens de aplicativo móvel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#mobile)</li><li>Retenção de visitante > Dispositivo móvel > [Desempenho do aplicativo móvel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#mobile)</li><li>Retenção de visitante > Dispositivo móvel > [Retenção de aplicativo móvel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#mobile)</li></ul> |
| **[!UICONTROL Aquisição]** | <ul><li>Canais de marketing > Canal de primeiro contato, Detalhes do canal de primeiro contato (qual canal de primeiro contato e qual canal de primeiro contato específico está tendo o melhor desempenho?)</li><li>Canais de marketing > Primeiro último canal, Detalhes do primeiro último canal (qual canal de último contato e qual canal de último contato específico está tendo o melhor desempenho?)</li><li>Campanhas > Campanhas (quais campanhas estão impulsionando minhas principais métricas?)</li><li>Campanhas > Desempenho da campanha (que campanhas estão gerando mais receita?)</li><li>Campanhas > Código de rastreamento (quais códigos de rastreamento de campanha têm o melhor desempenho?)</li><li>[Aquisição na web](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#web)</li><li>[Aquisição por dispositivo móvel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#mobile)</li><li>[Advertising Analytics: pesquisa paga](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=pt-BR#advertising)</li><li>Palavras-chave de pesquisa — todas, pagas, naturais (quais palavras-chave de pesquisa e palavras-chave de pesquisa pagas/naturais direcionam minhas métricas principais da melhor maneira?)</li><li>Mecanismos de pesquisa — todos, pagos, naturais (quais mecanismos de pesquisa e mecanismos de pesquisa pagos/naturais direcionam minhas métricas principais da melhor maneira?)</li><li>Toda a classificação da página de pesquisa (de qual página de pesquisa meus usuários chegam?)</li><li>Domínios de referência (quais domínios estão direcionando tráfego para meu site?)</li><li>Domínios de referência originais (quais foram os primeiros usuários de domínio antes de visitar meu site?)</li><li>Referenciadores (em quais URLs meus usuários estavam antes de clicar no meu site?)</li><li>Tipos de referenciadores (a qual categoria meus URLs de referência pertencem?)</li></ul> |
