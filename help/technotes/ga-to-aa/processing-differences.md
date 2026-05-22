---
title: Diferenças de processamento e arquitetura entre plataformas do Analytics
description: Saiba como alguns dados são coletados e exibidos de forma diferente entre plataformas como o Adobe Analytics e o Google Analytics.
feature: Third-party Integration
exl-id: 3e457915-3c2d-49f7-9b77-df18c04d49cd
TQID: 'https://experienceleague.adobe.com/pL36oKany2sKuJrEn4-oIja3O91PZ47YQGoNvhdt6y8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: a60fda7a-bb0b-4eb6-b9fe-77558cbee1fa
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 503
ht-degree: 96%

---

# Diferenças de processamento e arquitetura entre plataformas do Analytics

Embora o Adobe Analytics e o Google Analytics sejam ferramentas do Analytics, a forma como os dados são coletados e processados entre plataformas é muito diferente. Use esta página para entender algumas das principais diferenças em como determinadas dimensões e métricas são coletadas e por que elas podem exibir números diferentes em relatórios semelhantes.

## [!UICONTROL Taxa de rejeição &#x200B;]

A [!UICONTROL Taxa de devolução] é um KPI comum usado para ajudar a medir a eficácia e a relevância das páginas de destino na maioria das ferramentas de análise. Isso geralmente é definido como visitas que entram no site, mas não incluem um clique para outra página.

* No Adobe Analytics, a [!UICONTROL Taxa de rejeição] é calculada usando a fórmula **Rejeições divididas por Entradas**.
* No Google Analytics, a [!UICONTROL Taxa de rejeição] é calculada usando a fórmula **Sessões de página única divididas por Sessões**.

Em ambas as plataformas, se várias ocorrências forem enviadas na mesma visita ou sessão, não será considerado uma devolução. No Adobe Analytics, os links personalizados estão disponíveis e são bastante comuns, o que pode impedir que uma visita seja contada como uma devolução. O Google Analytics geralmente não envia mais de uma solicitação de dados na mesma página.

Para obter uma melhor paridade entre as ferramentas de relatórios, use a métrica [!UICONTROL Visitas de página única] no Adobe Analytics em vez de [!UICONTROL Rejeições] como parte de uma métrica calculada. A métrica [!UICONTROL Visitas de página única] inclui o número total de visitas que incluíram apenas uma exibição de página ou visitas que entram no site, mas não incluem um clique para outra página.

Consulte a métrica [Taxa de devolução](/help/components/metrics/bounce-rate.md) no guia do usuário Componentes para obter mais informações.

## [!UICONTROL Visitas e sessões]

[!UICONTROL Visitas] (conhecidas como sessões no Google Analytics) são um grupo de exibições de página feitas pelo mesmo usuário em um curto período. As [!UICONTROL visitas] em ambas as plataformas normalmente expiram após 30 minutos de inatividade. Ambas as plataformas permitem a personalização quando uma [!UICONTROL Visita] expira. Há vários cenários que podem causar diferenças em cada plataforma.

* **Fim do dia:** Todas as sessões no Google Analytics expiram depois das 23:00 horas de um determinado dia. :59Se o usuário ainda estiver ativo no site depois das 12 horas, uma nova sessão será criada. O Adobe Analytics continua as visitas no dia seguinte como parte da mesma visita.
* **Campanhas diferentes:** uma nova sessão no Google Analytics será iniciada se a origem da campanha de um usuário mudar. Se um novo valor de [!UICONTROL Código de rastreamento] for visto no Adobe Analytics, ele será considerado parte da mesma visita
* **Substituição manual de sessão:** uma nova sessão no Google Analytics será iniciada se você usar `sessionControl` para iniciar ou encerrar uma sessão manualmente. [!UICONTROL As visitas não podem ser encerradas manualmente no Adobe Analytics.]
* **Detecção de visitas atípicas no Adobe Analytics:** uma nova [!UICONTROL Visita] no Adobe Analytics é iniciada automaticamente se um usuário atinge 12 horas de atividade contínua, 2500 ocorrências ou 100 ocorrências em 100 segundos. Cada um desses critérios de detecção normalmente é acionado pela atividade do bot.

Consulte a métrica [Visitas](/help/components/metrics/visits.md) no guia do usuário Componentes para obter mais informações.
