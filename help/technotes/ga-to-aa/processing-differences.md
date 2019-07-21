---
title: Diferenças de processamento e arquitetura entre plataformas do Analytics
description: Saiba como alguns dados são coletados e exibidos de forma diferente entre plataformas, como o Adobe Analytics e o Google Analytics.
translation-type: tm+mt
source-git-commit: a5f612ba5e8446a56bc2bd252a8781e8ab1de403

---


# Diferenças de processamento e arquitetura entre plataformas do Analytics

Embora o Adobe Analytics e o Google Analytics sejam ferramentas do Analytics, a maneira como os dados são coletados e processados entre plataformas é muito diferente. Use essa página para entender algumas das principais diferenças de como determinadas dimensões e métricas são coletadas, e por que elas podem exibir números diferentes em relatórios semelhantes.

## Taxa de rejeição

A Taxa de rejeição é um KPI comum usado para ajudar a medir a eficácia e a relevância das páginas iniciais na maioria das ferramentas de análise. Isso é comumente definido como visitas que entram no site, mas não incluem um clique para outra página.

* In Adobe Analytics, Bounce Rate is calculated using the formula **Bounces divided by Entries**.
* In Google Analytics, Bounce Rate is calculated using the formula **Single-page sessions divided by Sessions**.

Em ambas as plataformas, se várias ocorrências forem enviadas na mesma visita ou sessão, elas não serão consideradas uma rejeição. No Adobe Analytics, os links personalizados estão disponíveis e muito comuns, o que pode impedir que uma visita conte como uma rejeição. O Google Analytics normalmente não envia mais de uma solicitação de dados na mesma página.

Para obter melhor paridade entre as ferramentas de relatório, use a métrica de Visitas únicas à página no Adobe Analytics, em vez de Rejeições como parte de uma métrica calculada. A métrica Visitas únicas à página inclui o número total de visitas que incluíram apenas uma exibição de página, ou visitas que entram no site, mas não incluem um clique para outra página.

See the [Bounce Rate](../../components/c-variables/c-metrics/metrics-bounce-rate.md) metric in the Components user guide for more information.

## Visitas e Sessões

Visitas (chamadas de sessões no Google Analytics) são um grupo de exibições de página feitas pelo mesmo usuário em um curto período de tempo. As visitas em ambas as plataformas normalmente expiram após 30 minutos de inatividade. Ambas as plataformas permitem personalização quando uma visita expira. Há vários cenários que podem causar diferenças em cada plataforma.

* **Fim do dia:** Todas as sessões no Google Analytics expiram após 11:59 PM em um dia específico. Se o usuário ainda estiver ativo no site após 12 h, uma nova sessão será criada. O Adobe Analytics continua as visitas no dia seguinte como parte da mesma visita.
* **Diferentes campanhas:** Uma nova sessão do Google Analytics é iniciada se a fonte de campanha de um usuário for alterada. Se um novo valor de Código de rastreamento for visto no Adobe Analytics, ele será considerado parte da mesma visita.
* **Substituição da sessão manual:** Uma nova sessão do Google Analytics começa se você usar `sessionControl` para iniciar ou encerrar manualmente uma sessão. As visitas não podem ser terminadas manualmente no Adobe Analytics.
* **Detecção de visitas Outer no Adobe Analytics:** Uma nova visita do Adobe Analytics é iniciada automaticamente se um usuário atingir 12 horas de atividade contínua, hits 500 ocorrências ou 100 acessos em 100 segundos. Cada um desses critérios de detecção normalmente são acionados pela atividade do robô.

See the [Visits](../../components/c-variables/c-metrics/metrics-visit.md) metric in the Components user guide for more information.
