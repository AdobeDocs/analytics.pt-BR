---
description: Ative dimensões e métricas para usar no rastreamento de aplicativos móveis.
title: Relatório do aplicativo
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 13%

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

As métricas a seguir estão disponíveis:

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
* Rastrear beacons bluetooth (UUID, maior, menor e proximidade).

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

As métricas a seguir estão disponíveis:

* [!UICONTROL Fim da Sessão de Voz]
* [!UICONTROL Erro de Voz]
* [!UICONTROL Palavras de voz]

## Relatórios e atribuição herdados para ocorrências em segundo plano

Relatórios herdados significa que as ocorrências geradas quando um aplicativo está em segundo plano são tratadas como ocorrências em primeiro plano regulares. Elas são exibidas nos relatórios e afetam a atribuição. Normalmente, essa configuração herdada é desejável para manter a consistência com implementações herdadas.

A Adobe recomenda desativar os relatórios herdados para que as ocorrências em segundo plano não fiquem visíveis. Se quiser incluir ocorrências em segundo plano na análise, habilite a configuração [Conjunto de relatórios virtuais](/help/components/vrs/vrs-about.md) **[!UICONTROL Incluir ocorrências em segundo plano]**.
