---
description: O novo sistema de Alertas inteligentes permite um controle mais detalhado dos alertas e integra a detecção de anomalias ao sistema de alertas.
title: Visão geral de Alertas inteligentes
feature: Alerts
role: User, Admin
exl-id: 49d47896-bf93-4960-b647-2765c935eb25
source-git-commit: d48f74d4fa642e34de601466737f16fc228a8199
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 52%

---

# Visão geral de Alertas inteligentes

Os Alertas inteligentes (ou apenas &quot;alertas&quot;) no Adobe Analytics permitem que você seja notificado imediatamente quando ocorrerem eventos anormais em seus dados.

Você pode definir que os alertas sejam acionados com base em limites de anomalias, porcentagens alteradas ou pontos de dados específicos. Os alertas fornecem controles granulares que se integram a [Detecção de anomalias](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md), acionando quando você mais precisa deles.

Os Alertas inteligentes permitem:

* Criar alertas com base em anomalias (limites de 90%, 95%, 99%, 99,75% e 99,9%; % de alteração; acima/abaixo)
* Visualizar a frequência de disparo de um alerta
* Enviar alertas por email ou SMS com links para projetos do Analysis Workspace gerados automaticamente
* Criar alertas “empilhados”, capazes de capturar várias métricas de um só alerta

O tutorial em vídeo a seguir fornece uma visão geral básica dos alertas: [Alertas inteligentes](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=pt-BR) (5:34)

## Pesquisa de anomalias para alertas

Se um alerta usar a detecção de anomalias, o período de treinamento varia de acordo com a granularidade selecionada para o alerta.

* Granularidade mensal: 15 meses + mesmo intervalo do ano passado
* Granularidade semanal: 15 semanas + mesmo intervalo do ano passado
* Granularidade diária: 35 dias + mesmo intervalo do ano passado
* Granularidade por hora: 336 horas

Para obter mais informações, consulte [Técnicas estatísticas usadas na Detecção de anomalias](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Criar alertas

Para obter informações sobre como criar alertas no Adobe Analytics, consulte [Criar alertas](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

>[!IMPORTANT]
>
>Usar dados com carimbo de data e hora para criar alertas pode fazer com que os alertas disparem incorretamente. A Adobe recomenda o uso de dados sem carimbo de data e hora para criar Alertas inteligentes.

## Gerenciar alertas

Você pode gerenciar alertas existentes no Gerenciador de alertas. Você pode executar várias tarefas de gerenciamento em alertas, como marcar, renomear, excluir e muito mais.

Para obter mais informações sobre como gerenciar alertas existentes no Adobe Analytics, consulte [Gerenciar alertas](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-manager.md).
