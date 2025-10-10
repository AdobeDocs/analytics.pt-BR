---
title: Perguntas frequentes sobre a migração para o Adobe Analytics
description: Obtenha respostas para perguntas frequentes ao mudar de uma plataforma de terceiros para a Adobe.
feature: Third-party Integration
exl-id: 1201909e-b20c-48c5-b287-393da8e22d78
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 73%

---

# Perguntas frequentes sobre a migração para o Adobe Analytics

**Como posso migrar os dados históricos da minha plataforma de terceiros para o Adobe Analytics?**

Cada plataforma do Analytics tem diferentes maneiras de coletar, manipular e armazenar dados. Em vez de migrar dados históricos, a Adobe recomenda estabelecer uma data limite clara para começar a coletar e usar dados no Adobe Analytics. As datas limites usadas com frequência são o início de um ano fiscal, o início de um ano civil ou o início de um mês. Se os usuários quiserem exibir dados históricos, eles poderão fazer logon na plataforma de terceiros para obter necessidades específicas de relatórios históricos.

Se a organização estiver convencida de que os dados históricos foram transmitidos para o Adobe, entre em contato com a equipe de conta da Adobe. Um consultor de implementação pode trabalhar com a organização para traduzir uma exportação de dados do Google Analytics em uma fonte de dados que pode ser assimilada pelos servidores de coleta de dados da Adobe.

Para mover dados históricos, recomendamos usar o [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=pt-BR), que pode trazer qualquer fonte de dados omnicanal.

**Estou acostumado com uma lista suspensa de segmentação em muitos dos meus relatórios. Como posso recriar isso no [!UICONTROL Analysis Workspace]?**

Os filtros suspensos são um recurso flexível e robusto do [!UICONTROL Analysis Workspace] que permite uma lista suspensa de segmentação. Em um projeto do espaço de trabalho:

1. Use ctrl+clique (Windows) ou cmd+clique (Mac) nos componentes que deseja incluir no filtro suspenso. Você não está limitado a apenas segmentos; qualquer componente pode ser incluído em um filtro suspenso.
2. Arraste o grupo de componentes para o espaço de trabalho chamado &#39;Solte um segmento aqui&#39;. Antes de soltar, pressione a tecla Shift.

Os usuários que acessam este projeto [!UICONTROL Workspace] agora podem usar este filtro suspenso para aplicar segmentos ou outros componentes ao projeto. Consulte [Visão geral dos painéis](/help/analyze/analysis-workspace/c-panels/panels.md) no guia Ferramentas do Adobe Analytics para obter mais informações.

**Estou acostumado a clicar em um item de dimensão para ver um detalhamento. Como posso replicar esse fluxo de trabalho fácil no Analysis Workspace?**

Os itens de dimensão no [!UICONTROL Analysis Workspace] também têm um fluxo de trabalho de detalhamento simples. Para acessá-lo, clique com o botão direito do mouse. Clique com o botão direito do mouse em um item de dimensão, clique em [!UICONTROL Detalhamento] e selecione o componente desejado. Aplique o mesmo detalhamento a vários itens de dimensão usando ctrl+clique (Windows) ou cmd+clique (Mac) em cada valor.
