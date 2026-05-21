---
description: Obtenha respostas de perguntas comuns sobre o Analysis Workspace.
title: Perguntas frequentes
feature: Workspace Basics
role: User, Admin
exl-id: cf7a9a73-bcbe-4bf5-b5dc-913199ab229c
TQID: https://experienceleague.adobe.com/Cp7KvN1Y7Mxr4iGWNF08TYBzJWqhVWVSHApX0989lZ4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 598
ht-degree: 89%

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
Agora você pode criar projetos no Analysis Workspace usando dados de [vários conjuntos de relatórios](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md).
+++

+++Como você implementa o Analysis Workspace?
Não é necessária nenhuma implementação específica. O Analysis Workspace está disponível para todas as empresas, com o Analytics Standard ou Premium. No entanto, as permissões padrão de conteúdo (como conjuntos de relatórios e componentes de projeto) se aplicam para preparar e compartilhar projetos. Consulte [Requisitos de administração e acesso](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md).
+++

+++Posso usar o Analysis Workspace para Data Warehouse?
O Analysis Workspace não é recomendado para a exportação de dados em massa. É um espaço de trabalho de visualização que cria projetos de análise semelhantes a painéis.
+++

+++Como posso otimizar o desempenho do Analysis Workspace?

Consulte [Otimizar o desempenho](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md).

+++

+++Como os dados entram em seu projeto do Analysis Workspace?

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dados no Analysis Workspace](https://experienceleague.adobe.com/pt-br/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/understanding-how-data-gets-into-your-analysis-workspace-project){target="_blank"} para assistir a um vídeo de demonstração.

+++

+++Como posso monitorar o uso do Espaço de trabalho?

Confira ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Rastreamento por log](https://experienceleague.adobe.com/pt-br/docs/analytics-learn/tutorials/administration/logs/usage-log-tracking-for-analysis-workspace){target="_blank"} para assistir a um vídeo de demonstração.

+++

+++Quando arrasto uma métrica, vejo a mensagem “Dados inválidos”. Como posso resolver esse problema?

Dados inválidos significa que a Adobe não pode retornar dados usando a combinação de dimensões e métricas usadas no relatório. Por exemplo, duas métricas empilhadas uma sobre a outra não podem retornar como dados, pois não há como exibir duas métricas desse modo. Em vez disso, coloque as métricas lado a lado.

+++

+++Quando arrasto uma métrica, não vejo nenhum dado real, apenas zeros. Como posso solucionar esse problema?

Se você criar um relatório de espaço de trabalho com êxito, mas não houver dados, você pode realizar as seguintes verificações:

* Verifique novamente o conjunto de relatórios e veja se ele está preenchido com dados.
* Se você aplicar um segmento no seu relatório, os critérios do segmento podem não corresponder a nenhum dado. Tente remover o segmento ou ajustar a definição do segmento.
* Verifique o intervalo de datas no canto superior direito e verifique se ele está definido como um valor que você esperaria.
* Acesse seu site e use o [Depurador](https://experienceleague.adobe.com/pt-br/docs/experience-platform/debugger/home) para verificar se os dados estão sendo coletados.


+++

+++Como usuário somente de leitura, que ações posso executar no Analysis Workspace?
Quando um projeto é compartilhado como somente de leitura, todas as funções e recursos de edição são completamente desabilitados, e os destinatários só podem alterar o menu suspenso para aplicar um filtro ao painel de forma predefinida.
+++
