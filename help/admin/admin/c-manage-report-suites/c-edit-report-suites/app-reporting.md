---
description: Ative dimensões e métricas para usar no rastreamento de aplicativos móveis.
title: Relatório do aplicativo
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 20%

---

# Relatório do aplicativo

A interface do App Reporting permite ativar dimensões e métricas de ciclo de vida dedicadas ao uso no rastreamento de aplicativos móveis.

**[!UICONTROL Analytics]** > **[!UICONTROL Administração]** > **[!UICONTROL Conjuntos de relatórios]** > **[!UICONTROL Editar configurações]** > **[!UICONTROL Gerenciamento de aplicativos]** > **[!UICONTROL Relatórios de aplicativos]**

>[!IMPORTANT]
>
>Após ativar qualquer um desses recursos, eles não poderão ser desativados. Ativar um determinado recurso torna suas respectivas dimensões e métricas permanentemente disponíveis no Analysis Workspace.

## [!UICONTROL Relatórios do aplicativo]

[!UICONTROL Relatórios do aplicativo] dimensões e métricas são usadas para os seguintes fins:

* **Aquisição**: Rastreie URLs de referência para campanhas de download de aplicativos.
* **Ciclo de vida**: nível básico de relatórios fornecido pela medição enviada em cada inicialização do aplicativo.
* **Ações do aplicativo**: relatórios e definição de caminho com base em ações no aplicativo.
* **Valor vitalício**: entenda como os usuários acumulam valor ao longo do tempo usando KPIs do aplicativo (como compras, visualizações de anúncios, conclusões de vídeo, compartilhamentos sociais, uploads de fotos).
* **Eventos cronometrados**: meça o tempo decorrido (tempo no aplicativo e tempo total) entre as principais ações do aplicativo (como tempo antes da primeira compra).

Quando você habilita [!UICONTROL Relatórios do aplicativo], as seguintes dimensões estão disponíveis:

* [!UICONTROL Nome da ação] (com [Entrada](/help/components/dimensions/entry-dimensions.md) e [Sair](/help/components/dimensions/exit-dimensions.md) dimensões)
* [!UICONTROL ID do aplicativo]
* [!UICONTROL Conteúdo da aquisição]
* [!UICONTROL Meio da aquisição]
* [!UICONTROL Nome da aquisição]
* [!UICONTROL Fonte da aquisição]
* [!UICONTROL Termo de aquisição]
* [!UICONTROL Dia da semana (SDK)]
* [!UICONTROL Dias desde a primeira utilização]
* [!UICONTROL Dias desde a última utilização]
* [!UICONTROL Nome do dispositivo (SDK)]
* [!UICONTROL Horário do dia (SDK)]
* [!UICONTROL Data da primeira inicialização]
* [!UICONTROL Número de lançamento]
* [!UICONTROL Valor da duração (evar)]
* [!UICONTROL Versão do sistema operacional (SDK)]
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

## [!UICONTROL Rastreamento de localização]

[!UICONTROL Rastreamento de localização] dimensões são usadas para os seguintes fins:

* Rastrear dados de latitude e longitude
* Identificar, criar e visualizar pontos de interesse específicos. Os pontos de interesse devem ser definidos no arquivo de configuração do SDK móvel.
* Rastrear beacons bluetooth (UUID, maior, menor e proximidade).

Quando você habilita [!UICONTROL Rastreamento de localização], as seguintes dimensões estão disponíveis:

* [!UICONTROL Beacon principal] (com [Entrada](/help/components/dimensions/entry-dimensions.md) e [Sair](/help/components/dimensions/exit-dimensions.md) dimensões)
* [!UICONTROL Beacon secundário] (com [Entrada](/help/components/dimensions/entry-dimensions.md) e [Sair](/help/components/dimensions/exit-dimensions.md) dimensões)
* [!UICONTROL Proximidade do sinal] (com [Entrada](/help/components/dimensions/entry-dimensions.md) e [Sair](/help/components/dimensions/exit-dimensions.md) dimensões)
* [!UICONTROL UUID do sinal] (com [Entrada](/help/components/dimensions/entry-dimensions.md) e [Sair](/help/components/dimensions/exit-dimensions.md) dimensões)
* [!UICONTROL Localização (abaixo de 10 km)]
* [!UICONTROL Localização (abaixo de 100 m)]
* [!UICONTROL Localização (abaixo de 1 m)]
* [!UICONTROL Nome do ponto de interesse]
* [!UICONTROL Distância até o centro do ponto de interesse]
* [!UICONTROL ID do ponto de interesse]

## [!UICONTROL Voz e Chatbots]

[!UICONTROL Voz e Chatbots] dimensões e métricas permitem medir assistentes de voz, como Alexa ou Google Home. Ele também permite medir bots de bate-papo caseiros. As propriedades de medição incluem:

* **Ciclo de vida**: Nível básico de relatórios para qualquer aplicativo, como o número de inicializações e o tipo de plataforma.
* **Conversas**: Mede intenções, respostas e outras métricas e dimensões relacionadas à conversa.

Quando você habilita [!UICONTROL Voz e Chatbots], as seguintes dimensões estão disponíveis:

* [!UICONTROL Recursos do dispositivo de voz] (com [Entrada](/help/components/dimensions/entry-dimensions.md) e [Sair](/help/components/dimensions/exit-dimensions.md) dimensões)
* [!UICONTROL Autenticação de voz]
* [!UICONTROL Tipo de Erro de Voz]
* [!UICONTROL Intenção de voz]
* [!UICONTROL Resposta do aplicativo de voz]
* [!UICONTROL Idioma de voz]

As métricas a seguir estão disponíveis:

* [!UICONTROL Sessão de fim de voz]
* [!UICONTROL Erro de voz]
* [!UICONTROL Pronunciamentos de voz]

## Relatórios e atribuição herdados para ocorrências em segundo plano

Relatórios herdados significa que as ocorrências geradas quando um aplicativo está em segundo plano são tratadas como ocorrências em primeiro plano regulares. Elas são exibidas nos relatórios e afetam a atribuição. Normalmente, essa configuração herdada é desejável para manter a consistência com implementações herdadas.

O Adobe recomenda desabilitar os relatórios herdados para que as ocorrências em segundo plano não fiquem visíveis. Se quiser incluir ocorrências em segundo plano na análise, você pode ativar o [Conjunto de relatórios virtual](/help/components/vrs/vrs-about.md) configuração **[!UICONTROL Incluir ocorrências em segundo plano]**.
