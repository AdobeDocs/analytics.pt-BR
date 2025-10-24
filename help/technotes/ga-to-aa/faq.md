---
title: Perguntas frequentes sobre a migração para o Adobe Analytics
description: Obtenha respostas para perguntas frequentes ao mudar de uma plataforma de terceiros para a Adobe.
feature: Third-party Integration
exl-id: 1201909e-b20c-48c5-b287-393da8e22d78
source-git-commit: 58d53d6013abcd7d99f2c3cb640d6a648a4ef360
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 53%

---

# Perguntas frequentes sobre a migração para o Adobe Analytics

**Como posso migrar os dados históricos da minha plataforma de terceiros para o Adobe Analytics?**

Cada plataforma do Analytics tem diferentes maneiras de coletar, manipular e armazenar dados. Em vez de migrar dados históricos, a Adobe recomenda estabelecer uma data limite clara para começar a coletar e usar dados no Adobe Analytics. As datas limites usadas com frequência são o início de um ano fiscal, o início de um ano civil ou o início de um mês. Se os usuários quiserem exibir dados históricos, eles poderão fazer logon na plataforma de terceiros para obter necessidades específicas de relatórios históricos.

Se a organização estiver convencida de que os dados históricos foram transmitidos para o Adobe, entre em contato com a equipe de conta da Adobe. Um consultor de implementação pode trabalhar com a organização para traduzir uma exportação de dados do Google Analytics em uma fonte de dados que pode ser assimilada pelos servidores de coleta de dados da Adobe.

Para mover dados históricos, recomenda-se usar o [Customer Journey Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-overview), que pode trazer qualquer fonte de dados omnicanal.

**Estou acostumado com uma lista suspensa de segmentação em muitos dos meus relatórios. Como posso recriar isso no [!UICONTROL Analysis Workspace]?**

Os filtros suspensos são um recurso flexível e robusto do [!UICONTROL Analysis Workspace] que permite uma lista suspensa de segmentação. Em um projeto do espaço de trabalho:

1. Use o ***ctrl***+***click*** (Windows) ou o ***cmd***+***click*** (Mac) nos componentes que você deseja incluir no filtro suspenso. Você não está limitado a apenas segmentos. Qualquer componente pode ser incluído em um filtro suspenso.
2. Arraste o grupo de componentes para o espaço de trabalho chamado *Solte um segmento aqui*. Antes de soltar, segure **[!UICONTROL shift]**.

Os usuários que acessam este projeto [!UICONTROL Workspace] agora podem usar este filtro suspenso para aplicar segmentos ou outros componentes ao projeto. Consulte [Visão geral dos painéis](/help/analyze/analysis-workspace/c-panels/panels.md) no guia Ferramentas do Adobe Analytics para obter mais informações.

**Estou acostumado a clicar em um item de dimensão para ver um detalhamento. Como posso replicar esse fluxo de trabalho fácil no Analysis Workspace?**

Os itens de dimensão no [!UICONTROL Analysis Workspace] também têm um fluxo de trabalho de detalhamento simples. Acesse o detalhamento usando o menu de contexto em um item de dimensão. Em seguida, selecione **[!UICONTROL Detalhamento]** e o componente desejado. Aplique o mesmo detalhamento a vários itens de dimensão usando ***ctrl***+***select*** (Windows) ou ***cmd***+***select*** (Mac) em cada valor.
