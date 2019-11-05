---
title: Diferenças de processamento e arquitetura entre plataformas do Analytics
description: Saiba como alguns dados são coletados e exibidos de forma diferente entre plataformas como o Adobe Analytics e o Google Analytics.
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Diferenças de processamento e arquitetura entre plataformas do Analytics

Embora o Adobe Analytics e o Google Analytics sejam ferramentas do Analytics, a forma como os dados são coletados e processados entre plataformas é muito diferente. Use esta página para entender algumas das principais diferenças em como determinadas dimensões e métricas são coletadas e por que elas podem exibir números diferentes em relatórios semelhantes.

## Taxa de rejeição 

A Taxa de rejeição é um KPI comum que é usado para ajudar a medir a eficácia e a relevância das páginas iniciais na maioria das ferramentas de análise. Isso é geralmente definido como visitas que entram no site, mas não incluem um clique para outra página.

* No Adobe Analytics, a Taxa de rejeição é calculada usando a fórmula **Rejeições divididas por Entradas**.
* No Google Analytics, a Taxa de rejeição é calculada usando a fórmula Sessões de página **única divididas por Sessões**.

Em ambas as plataformas, se várias ocorrências forem enviadas na mesma visita ou sessão, não será considerado uma rejeição. No Adobe Analytics, os links personalizados estão disponíveis e são bastante comuns, o que pode impedir que uma visita seja contada como uma rejeição. O Google Analytics geralmente não envia mais de uma solicitação de dados na mesma página.

Para obter uma melhor paridade entre as ferramentas de relatório, use a métrica Visitas únicas à página no Adobe Analytics em vez de Rejeições como parte de uma métrica calculada. A métrica Visitas únicas à página inclui o número total de visitas que incluíram apenas uma exibição de página ou visitas que entram no site, mas não incluem um clique para outra página.

Consulte a métrica Taxa de [rejeição](/help/components/c-variables/c-metrics/metrics-bounce-rate.md) no guia do usuário Componentes para obter mais informações.

## Visitas e sessões

Visitas (conhecidas como sessões no Google Analytics) são um grupo de exibições de página feitas pelo mesmo usuário em um curto período de tempo. As visitas em ambas as plataformas normalmente expiram após 30 minutos de inatividade. Ambas as plataformas permitem a personalização quando uma visita expira. Há vários cenários que podem causar diferenças em cada plataforma.

* **** Fim do dia: Todas as sessões no Google Analytics expiram depois das 23:59 em um determinado dia. Se o usuário ainda estiver ativo em seu site depois das 12 horas, uma nova sessão será criada. O Adobe Analytics continua as visitas no dia seguinte como parte da mesma visita.
* **** Campanhas diferentes: Uma nova sessão no Google Analytics será iniciada se a fonte da campanha de um usuário mudar. Se um novo valor de Código de rastreamento for visto no Adobe Analytics, ele será considerado parte da mesma visita.
* **** Substituição manual de sessão: Uma nova sessão no Google Analytics é iniciada se você usar `sessionControl` para iniciar ou encerrar uma sessão manualmente. As visitas não podem ser encerradas manualmente no Adobe Analytics.
* **** Detecção de visitas anteriores no Adobe Analytics: Uma nova visita no Adobe Analytics é iniciada automaticamente se um usuário atingir 12 horas de atividade contínua, 2500 ocorrências ou 100 ocorrências em 100 segundos. Cada um desses critérios de detecção é normalmente acionado pela atividade do robô.

Consulte a métrica [Visitas](/help/components/c-variables/c-metrics/metrics-visit.md) no guia do usuário Componentes para obter mais informações.
