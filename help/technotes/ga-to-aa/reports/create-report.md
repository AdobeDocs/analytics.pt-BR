---
title: Criar um relatório básico no Analysis Workspace
description: Saiba como criar um relatório básico no Analysis Workspace em um formato direcionado a usuários familiarizados com ferramentas de terceiros, como o Google Analytics.
translation-type: tm+mt
source-git-commit: 099662d021c1919f0760e79154536cfd0e23e959

---


# Criar um relatório básico na Analysis Workspace para usuários do Google Analytics

O Analysis Workspace (um dos principais recursos do Adobe Analytics) fornece uma área robusta para que o usuário obtenha informações sobre os dados coletados. Os relatórios são muito diferentes se compararmos o Google Analytics e o Adobe Analytics:

* A estrutura de relatórios no Google Analytics permite selecionar um tipo específico de dados, como localização geográfica ou tráfego de referência. A plataforma usa uma exibição de relatório pré-fabricada com base na melhor maneira antecipada de visualizar esses dados.
* A estrutura de relatórios no Analysis Workspace oferece uma tela em branco, proporcionando mais flexibilidade para atender às necessidades exatas de relatórios.

Como o Analysis Workspace funciona mais como uma tela do que relatórios pré-fabricados, recriar relatórios do Google Analytics é simplesmente uma questão de usar as visualizações e os componentes certos.

## Termos principais usados no Workspace

* **Painéis** são os componentes principais gerais do espaço de trabalho. Em quase todos os cenários, um painel de forma livre é usado.
* **Visualizações** constituem todos os painéis de forma livre. O objetivo delas é representar dados em diferentes formatos. Na maioria das vezes esse formato é uma tabela, mas outras vezes pode ser algo como um gráfico de rosca ou de linha. Muitos relatórios no Google Analytics são feitos do equivalente a duas visualizações: um gráfico de linha e uma tabela de forma livre.
* **Componentes** são colocados em uma visualização para retornar dados. Os componentes podem ser misturados de várias maneiras diferentes para atender às necessidades de relatórios.
   * **Dimensões** são valores variáveis e geralmente contêm texto. Os exemplos incluem nome de página, referenciador ou país. Eles são listados com mais frequência como linhas em uma tabela.
   * **Métricas** normalmente significam um evento ou conversão de algum tipo. Os exemplos incluem eventos comuns, como uma exibição de página, ou algo mais significativo, como uma compra ou um registro. Normalmente, são vistas como colunas em tabelas para mostrar o número de vezes que o evento ocorreu por dimensão.
   * **Segmentos** são um subconjunto de seus dados e se comportam de forma semelhante aos segmentos no Google Analytics. Eles possibilitam criar filtros personalizados, permitindo que você se concentre em uma parte específica dos seus dados.
   * **Intervalos de datas** permitem organizar os dados de acordo com quando um evento ocorreu. Elas são a espinha dorsal da exibição de tendências ao longo do tempo e são normalmente pareadas a uma métrica.

## Criar um relatório básico no Workspace

Crie um relatório Todas as páginas (semelhante ao do Google Analytics) arrastando os componentes certos para uma tela de espaço de trabalho.

1. Faça logon em [experiencecloud.adobe.com](https://experiencecloud.adobe.com) usando as credenciais da Adobe ID.
1. Clique no ícone de 9 quadrados no canto superior direito e clique no logotipo colorido do Analytics.
1. Na barra de navegação superior, clique em Workspace.
1. Clique no botão “Criar novo projeto”.
1. No pop-up modal, verifique se “Projeto em branco” está selecionado e clique em Criar.
1. À esquerda, uma lista de dimensões, métricas, segmentos e intervalos de datas é exibida. Localize a dimensão Páginas (em laranja) e arraste-a para a tela rotulada como “Solte uma dimensão aqui”.
1. Um relatório que mostra as principais páginas deste mês pode ser visto. O Analysis Workspace preenche o relatório automaticamente com a métrica [Ocorrências](/help/components/c-variables/c-metrics/metrics-occurrences.md).
1. Uma tabela no Google Analytics geralmente contém de 7 a 8 métricas. Localize a métrica Taxa de rejeição (verde colorido) e arraste-a ao lado do cabeçalho da métrica Ocorrências. Se você arrastar a métrica Taxa de rejeição e soltá-la ao lado de Ocorrências, ambas as métricas serão exibidas lado a lado.
1. Muitas métricas podem ser colocadas lado a lado arrastando-as para o lado dos cabeçalhos de métricas existentes. Consulte [Métricas usadas com frequência](common-metrics.md) para obter informações sobre como obter as métricas geralmente usadas no Google Analytics.

   ![Nova métrica](/help/technotes/ga-to-aa/assets/new_metric.png)

## Comece com um modelo de relatório criado previamente no Workspace

Crie o modelo de Consumo de conteúdo (semelhante ao relatório Todas as páginas no Google Analytics) acessando um modelo de projeto.

1. Clique no botão “Criar novo projeto”.
1. Localize e clique duas vezes no ícone “Consumo de conteúdo (Web)” listado em Todos os modelos.
1. Procure cada uma das visualizações que foram pré-criadas: Fluxo de página de entrada, Tabela de páginas principais, Fluxo de página de saída, Fluxo de seção de entrada do site e Tabela de seções principais do site.

   ![Seleção de modelo](/help/technotes/ga-to-aa/assets/content_consumption_template.png)

## Experimentar com a ferramenta

Como o Analysis Workspace é uma ferramenta de relatórios, ela não exerce impacto na coleta de dados. Se você arrastar componentes indiscriminadamente para um projeto para ver o que acontece, não haverá nenhuma repercussão. Arraste diferentes combinações de dimensões e métricas para o projeto do seu espaço de trabalho para ver o que está disponível.

Se você arrastar acidentalmente um componente inválido para o projeto do seu espaço de trabalho ou quiser voltar uma etapa, pressione ctrl+Z (Windows) ou cmd+Z (Mac) para desfazer a última ação realizada. Você também pode começar com uma tabulação limpa clicando em *[!UICONTROL Projeto] > [!UICONTROL Novo]* no menu superior esquerdo.

A Adobe incluiu muitas funcionalidades ao Analysis Workspace no menu de contexto do clique com o botão direito do mouse. A maioria das visualizações e componentes pode ser clicada com o botão direito do mouse para que você obtenha análises e interações mais detalhadas. Considere a possibilidade de clicar com o botão direito do mouse nos componentes do seu espaço de trabalho para ver quais opções estão disponíveis.

## Entenda quais dimensões e métricas usar

Se você estiver confortável com o Analysis Workspace e quiser recriar um relatório específico geralmente exibido no Google Analytics, localize o relatório na respectiva página:

* [Relatórios em Tempo real](realtime-reports.md)
* [Relatórios de público-alvo](audience-reports.md)
* [Relatórios de aquisição](acquisition-reports.md)
* [Relatórios de comportamento](behavior-reports.md)
* [Relatórios de conversões](conversions-reports.md)
