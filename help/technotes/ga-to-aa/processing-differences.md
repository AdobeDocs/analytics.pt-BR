---
title: Diferenças de processamento e arquitetura entre plataformas do Analytics
description: Saiba como alguns dados são coletados e exibidos de forma diferente entre plataformas como o Adobe Analytics e o Google Analytics.
translation-type: tm+mt
source-git-commit: 3211598c2ff43493b329a9be4fb6877ae29cf08b
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 66%

---


# Diferenças de processamento e arquitetura entre plataformas do Analytics

Embora o Adobe Analytics e o Google Analytics sejam ferramentas do Analytics, a forma como os dados são coletados e processados entre plataformas é muito diferente. Use esta página para entender algumas das principais diferenças em como determinadas dimensões e métricas são coletadas e por que elas podem exibir números diferentes em relatórios semelhantes.

## [!UICONTROL Taxa de rejeição ]

[!UICONTROL A Taxa de devolução é um KPI comum usado para ajudar a medir a eficácia e a relevância das páginas de aterrissagem na maioria das ferramentas de análise. ] Isso geralmente é definido como visitas que entram no site, mas não incluem um clique para outra página.

* In Adobe Analytics, [!UICONTROL Bounce Rate] is calculated using the formula **Bounces divided by Entries**.
* In Google Analytics, [!UICONTROL Bounce Rate] is calculated using the formula **Single-page sessions divided by Sessions**.

Em ambas as plataformas, se várias ocorrências forem enviadas na mesma visita ou sessão, não será considerado uma devolução. No Adobe Analytics, os links personalizados estão disponíveis e são bastante comuns, o que pode impedir que uma visita seja contada como uma devolução. O Google Analytics geralmente não envia mais de uma solicitação de dados na mesma página.

To achieve better parity between reporting tools, use the [!UICONTROL Single Page Visits] metric in Adobe Analytics instead of [!UICONTROL Bounces] as part of a calculated metric. The [!UICONTROL Single Page Visits] metric includes the total number of visits that only included one-page view, or visits that enter the website but do not include a click to another page.

Consulte a métrica [Taxa de devolução](/help/components/c-variables/c-metrics/metrics-bounce-rate.md) no guia do usuário Componentes para obter mais informações.

## [!UICONTROL Visitas e sessões]

[!UICONTROL Visitas] (conhecidas como sessões no Google Analytics) são um grupo de visualizações de página feitas pelo mesmo usuário em um curto período de tempo. [!UICONTROL As visitas em ambas as plataformas normalmente expiram após 30 minutos de inatividade. ] Both platforms allow customization on when a [!UICONTROL Visit] expires. Há vários cenários que podem causar diferenças em cada plataforma.

* **Fim do dia:** todas as sessões no Google Analytics expiram depois das 23:59 em um determinado dia. Se o usuário ainda estiver ativo no site depois das 12 horas, uma nova sessão será criada. O Adobe Analytics continua as visitas no dia seguinte como parte da mesma visita.
* **Campanhas diferentes:** uma nova sessão no Google Analytics será iniciada se a origem da campanha de um usuário mudar. If a new [!UICONTROL Tracking Code] value is seen in Adobe Analytics, it is considered part of the same visit.
* **Substituição manual de sessão:** uma nova sessão no Google Analytics será iniciada se você usar `sessionControl` para iniciar ou encerrar uma sessão manualmente. [!UICONTROL As visitas não podem ser encerradas manualmente no Adobe Analytics.]
* **Detecção de visitas anteriores no Adobe Analytics:** Uma nova [!UICONTROL Visita] no Adobe Analytics start automaticamente se um usuário atingir 12 horas de atividade contínua, 2500 ocorrências ou 100 ocorrências em 100 segundos. Cada um desses critérios de detecção normalmente é acionado pela atividade do bot.

Consulte a métrica [Visitas](/help/components/c-variables/c-metrics/metrics-visit.md) no guia do usuário Componentes para obter mais informações.
