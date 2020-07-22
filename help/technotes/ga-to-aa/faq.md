---
title: Perguntas frequentes
description: Obtenha respostas para perguntas frequentes ao mudar de uma plataforma de terceiros para a Adobe.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 66%

---


# Perguntas frequentes

**Como posso migrar meus dados históricos da minha plataforma de terceiros para a Adobe Analytics?**

Cada plataforma do Analytics tem diferentes maneiras de coletar, manipular e armazenar dados. Em vez de migrar dados históricos, a Adobe recomenda estabelecer uma data limite clara para começar a coletar e usar dados no Adobe Analytics. As datas limites usadas com frequência são o início de um ano fiscal, o início de um ano civil ou o início de um mês. Se os usuários quiserem exibir dados históricos, eles poderão fazer logon na plataforma de terceiros para obter necessidades específicas de relatórios históricos.

Se a organização estiver convencida de que os dados históricos foram transmitidos para a Adobe, entre em contato com o Gerente de conta da organização. Um consultor de implementação pode trabalhar com a organização para traduzir uma exportação de dados do Google Analytics em uma fonte de dados que pode ser assimilada pelos servidores de coleta de dados da Adobe.

A Adobe não recomenda a portabilidade de dados históricos, pois é um processo complexo e de alto custo para a organização. A identificação do visitante também é impossível de ser diretamente enviada para a Adobe, já que as informações do visitante são armazenadas em diferentes cookies e formatos entre plataformas.

**Estou acostumado com uma lista suspensa de segmentação em muitos dos meus relatórios. How can I recreate that in[!UICONTROL Analysis Workspace]?**

Dropdown filters are a flexible and robust feature in [!UICONTROL Analysis Workspace] that allows a segmentation dropdown. Em um projeto do espaço de trabalho:

1. Use ctrl+clique (Windows) ou cmd+clique (Mac) nos componentes que deseja incluir na lista suspensa. Você não está limitado a apenas segmentos; qualquer componente pode ser incluído em um filtro suspenso.
2. Arraste o grupo de componentes para o espaço de trabalho chamado &#39;Solte um segmento aqui&#39;. Antes de soltar, pressione a tecla Shift.

Users accessing this [!UICONTROL Workspace] project can now use this dropdown to apply segments or other components to the project. See [Panels Overview](/help/analyze/analysis-workspace/c-panels/panels.md) in the Adobe Analytics Tools guide for more information.

**Estou acostumado a clicar em um item de dimensão para ver uma análise. Como posso replicar esse fluxo de trabalho fácil na Analysis Workspace?**

Os itens de dimensão no [!UICONTROL Analysis Workspace] também têm um fluxo de trabalho de detalhamento fácil. Para acessá-la, clique com o botão direito do mouse em vez de clicar com o botão esquerdo do mouse. Right-click on a dimension item, click **[!UICONTROL Breakdown], then select the desired component. Você pode aplicar o mesmo detalhamento a vários itens de dimensão usando ctrl+clique (Windows) ou cmd+clique (Mac) em cada valor.
