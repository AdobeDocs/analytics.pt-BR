---
description: Ative dimensões e métricas para usar no rastreamento de aplicativos móveis.
title: Relatório do aplicativo
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
TQID: https://experienceleague.adobe.com/oF-tETs2-MWjSLoo5bVUmrr2nS4N1o2shD4DkMDAVLU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: c77ba355-6681-41fe-b719-563d3f507fdbid: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 543
ht-degree: 11%

---

# Relatório do aplicativo

A interface do App Reporting permite ativar dimensões e métricas de ciclo de vida dedicadas ao uso no rastreamento de aplicativos móveis.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de Relatórios]** > **[!UICONTROL Editar Configurações]** > **[!UICONTROL Gerenciamento de Aplicativos]** > **[!UICONTROL Relatórios de Aplicativos]**

>[!IMPORTANT]
>
>Após ativar qualquer um desses recursos, eles não poderão ser desativados. Ativar um determinado recurso torna suas respectivas dimensões e métricas permanentemente disponíveis no Analysis Workspace.

## [!UICONTROL Relatórios de aplicativos]

As dimensões e métricas de [!UICONTROL Relatórios de Aplicativos] são usadas para as seguintes finalidades:

* **Aquisição**: rastrear URLs de referência para campanhas de download de aplicativo.
* **Ciclo de vida**: nível básico de relatórios fornecido pela medição enviada em cada inicialização do aplicativo.
* **Ações do aplicativo**: relatórios e definição de caminho com base em ações no aplicativo.
* **Valor vitalício**: entenda como os usuários acumulam valor ao longo do tempo usando KPIs do aplicativo (como compras, exibições de anúncios, conclusões de vídeo, compartilhamentos sociais, carregamentos de fotos).
* **Eventos cronometrados**: meça o tempo decorrido (tempo no aplicativo e total) entre as principais ações do aplicativo (como o tempo antes da primeira compra).

Quando você habilita os [!UICONTROL Relatórios de Aplicativos], as seguintes dimensões estão disponíveis:

* [!UICONTROL Nome da Ação] (com as dimensões [Entrada](/help/components/dimensions/entry-dimensions.md) e [Saída](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Id Do Aplicativo]
* [!UICONTROL Conteúdo de aquisição]
* [!UICONTROL Medium de aquisição]
* [!UICONTROL Nome da aquisição]
* [!UICONTROL Source de aquisição]
* [!UICONTROL Termo de aquisição]
* [!UICONTROL Dia da Semana (SDK)]
* [!UICONTROL Dias desde a primeira utilização]
* [!UICONTROL Dias desde a última utilização]
* [!UICONTROL Nome do dispositivo (SDK)]
* [!UICONTROL Hora do dia (SDK)]
* [!UICONTROL Data da primeira inicialização]
* [!UICONTROL Número de Lançamento]
* [!UICONTROL Valor vitalício (evar)]
* [!UICONTROL Versão do Sistema Operacional (SDK)]
* [!UICONTROL Resolução (SDK)]

As seguintes métricas estão disponíveis:

* [!UICONTROL Tempo da ação no aplicativo]
* [!UICONTROL Tempo da ação total]
* [!UICONTROL Falhas]
* [!UICONTROL Primeiras inicializações]
* [!UICONTROL Inicializações]
* [!UICONTROL Valor vitalício (evento)]
* [!UICONTROL Duração total da sessão]
* [!UICONTROL Atualizações]

## [!UICONTROL Acompanhamento de localização]

As dimensões [!UICONTROL Rastreamento de localização] são usadas para as seguintes finalidades:

* Rastrear dados de latitude e longitude
* Identificar, criar e visualizar pontos de interesse específicos. Os pontos de interesse devem ser definidos no arquivo de configuração do SDK móvel.
* Rastrear sinais do bluetooth (UUID, maior, menor e proximidade).

Quando você habilita o [!UICONTROL Rastreamento de localização], as seguintes dimensões estão disponíveis:

* [!UICONTROL Beacon Principal] (com as dimensões [Entrada](/help/components/dimensions/entry-dimensions.md) e [Saída](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Menor sinal] (com as dimensões [Entrada](/help/components/dimensions/entry-dimensions.md) e [Saída](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Proximidade do sinal] (com [Entrada](/help/components/dimensions/entry-dimensions.md) e [Saída](/help/components/dimensions/exit-dimensions.md) dimensões)
* [!UICONTROL UUID do sinal] (com as dimensões [Entrada](/help/components/dimensions/entry-dimensions.md) e [Saída](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Localização (abaixo de 10 km)]
* [!UICONTROL Localização (abaixo de 100 m)]
* [!UICONTROL Localização (abaixo de 1 m)]
* [!UICONTROL Nome do ponto de interesse]
* [!UICONTROL Distância até o centro do ponto de interesse]
* [!UICONTROL ID do Ponto de Interesse]

## [!UICONTROL Voz e Chatbots]

As dimensões e métricas [!UICONTROL Voice and Chatbots] permitem medir assistentes de voz, como Alexa ou Google Home. Ele também permite medir bots de bate-papo caseiros. As propriedades de medição incluem:

* **Ciclo de vida**: nível básico de relatórios para qualquer aplicativo, como o número de inicializações e o tipo de plataforma.
* **Conversas**: mede intenções, respostas e outras métricas e dimensões relacionadas à conversa.

Quando você habilita o [!UICONTROL Voice and Chatbots], as seguintes dimensões estão disponíveis:

* [!UICONTROL Recursos de Dispositivo de Voz] (com [Entrada](/help/components/dimensions/entry-dimensions.md) e [Saída](/help/components/dimensions/exit-dimensions.md) dimensões)
* [!UICONTROL Autenticação de Voz]
* [!UICONTROL Tipo de Erro de Voz]
* [!UICONTROL Intenção de Voz]
* [!UICONTROL Resposta do Aplicativo de Voz]
* [!UICONTROL Idioma de Voz]

As seguintes métricas estão disponíveis:

* [!UICONTROL Fim da Sessão de Voz]
* [!UICONTROL Erro de Voz]
* [!UICONTROL Palavras de voz]

## Relatórios e atribuições herdados para ocorrências em segundo plano

Relatórios herdados significa que as ocorrências geradas quando um aplicativo está em segundo plano são tratadas como ocorrências em primeiro plano regulares. Elas são exibidas nos relatórios e afetam a atribuição. Normalmente, essa configuração herdada é desejável para manter a consistência com implementações herdadas.

A Adobe recomenda desativar os relatórios herdados para que as ocorrências em segundo plano não fiquem visíveis. Se quiser incluir ocorrências em segundo plano na análise, habilite a configuração [Conjunto de relatórios virtuais](/help/components/vrs/vrs-about.md) **[!UICONTROL Incluir ocorrências em segundo plano]**.
