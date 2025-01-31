---
description: Perguntas frequentes sobre o Espaço de trabalho
title: Perguntas frequentes e solução de problemas no Espaço de trabalho
feature: Workspace Basics
role: User, Admin
exl-id: cf7a9a73-bcbe-4bf5-b5dc-913199ab229c
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 81%

---

# Perguntas frequentes

+++Quais são os pré-requisitos para usar o Analysis Workspace?
[Enviar dados para o Adobe Analytics usando a extensão do Adobe Analytics](/help/implement/launch/validate-publish-prod.md): usar o Analysis Workspace exige uma implementação funcional. Verifique se sua organização está enviando dados para a Adobe antes de usar a ferramenta. Outras implementações, como implementações manuais herdadas, também podem funcionar.
+++

+++Quais são os requisitos de administração e acesso para o Analysis Workspace?
Consulte [Requisitos de administração](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md).
+++

+++O uso do Analysis Workspace afetará a coleta de dados?
Como o Analysis Workspace é uma ferramenta de relatórios, ela não exerce impacto na coleta de dados. Se você arrastar componentes indiscriminadamente para um projeto para ver o que acontece, não haverá nenhuma repercussão. Arraste diferentes combinações de dimensões e métricas para o projeto do seu Workspace para ver o que está disponível. Se você arrastar acidentalmente um componente inválido para o projeto do seu Workspace ou quiser voltar uma etapa, pressione ctrl + Z (Windows) ou cmd + Z (Mac) para desfazer a última ação realizada. Você também pode começar com uma tabulação limpa clicando em **[!UICONTROL Projeto]** > **[!UICONTROL Novo]** no menu superior esquerdo.
+++

+++Quantos conjuntos de relatórios podem ser exibidos em um projeto do Analysis Workspace?
Agora você pode criar projetos no Analysis Workspace usando dados de [vários conjuntos de relatórios](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html?lang=pt-BR).
+++

+++Como você implementa o Analysis Workspace?
Não é necessária nenhuma implementação específica. O Analysis Workspace está disponível para todas as empresas, com o Analytics Standard ou Premium. No entanto, as permissões padrão de conteúdo (como conjuntos de relatórios e componentes de projeto) se aplicam para preparar e compartilhar projetos. Consulte [Requisitos de administração e acesso](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md).
+++

+++Posso usar o Analysis Workspace para Data Warehouse?
O Analysis Workspace não é recomendado para a exportação de dados em massa. É um espaço de trabalho de visualização que cria projetos de análise semelhantes ao painel.
+++

+++Como posso otimizar o desempenho do Analysis Workspace?

Consulte [Otimizar o desempenho](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md).

+++

+++Como os dados entram em seu projeto do Analysis Workspace?


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Data into Analysis Workspace](https://video.tv.adobe.com/v/31072?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


+++

+++Como posso rastrear o uso do Workspace?


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Rastreamento de log](https://video.tv.adobe.com/v/29768?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


+++

+++Quando arrasto uma métrica, vejo a mensagem “Dados inválidos”. Como resolver esse problema?

Dados inválidos significa que a Adobe não pode retornar dados usando a combinação de dimensões e métricas usadas no relatório. Por exemplo, duas métricas empilhadas uma sobre a outra não podem retornar como dados, pois não há como exibir duas métricas desse modo. Em vez disso, coloque as métricas lado a lado.

+++

+++Quando arrasto uma métrica, não vejo nenhum dado real, apenas zeros. Como posso solucionar esse problema?

Se você criar um relatório de espaço de trabalho com êxito, mas não houver dados, você pode realizar as seguintes verificações:

* Verifique novamente o conjunto de relatórios e veja se ele está preenchido com dados.
* Se você aplicar um segmento no seu relatório, os critérios do segmento podem não corresponder a nenhum dado. Tente remover o segmento ou ajustar a definição do segmento.
* Verifique o intervalo de datas no canto superior direito e verifique se ele está definido como um valor que você esperaria.
* Acesse seu site e use o [Depurador](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=pt-BR) para verificar se os dados estão sendo coletados.


+++

+++Como usuário somente leitura, que ações posso executar no Analysis Workspace?
Quando um projeto é compartilhado como somente leitura, todas as funções e recursos de edição são completamente desativados e os recipients só podem alterar a lista suspensa para aplicar um filtro ao painel de uma maneira predefinida.
+++