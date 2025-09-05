---
description: Entenda como usar alertas para obter um controle granular das notificações e uma integração com a detecção de anomalias.
title: Visão geral dos alertas
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 96%

---

# Visão geral de alertas

Os alertas no Adobe Analytics permitem que você receba uma notificação com base em porcentagens alteradas ou pontos de dados específicos.

Dependendo do pacote do Adobe Analytics, também é possível usar alertas que são acionados com base em limites de anomalias. Esses alertas (também conhecidos como “Alertas inteligentes”) fornecem controle granular que se integra à [Detecção de anomalias](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) e são acionados quando você mais precisa.

Os alertas inteligentes permitem:

* Visualizar a frequência de disparo de um alerta
* Enviar alertas por email ou SMS com links para projetos do Analysis Workspace gerados automaticamente
* Criar alertas “empilhados”, capazes de capturar várias métricas de um só alerta
* Criar alertas com base em anomalias (ao atingir limites de 90%, 95%, 99%, 99,75% e 99,9%; após alterações de porcentagem; quando os níveis estão acima ou abaixo do limite) (Disponível somente para clientes do Adobe Analytics com um pacote Select, Prime ou Ultimate)

O tutorial em vídeo a seguir fornece uma visão geral básica dos alertas: [Alertas](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=pt-BR) (5:34)

## Pesquisa de anomalias para alertas

>[!NOTE]
>
>O uso de alertas com a detecção de anomalias (também conhecidos como _Alertas inteligentes_) está disponível somente para organizações com um pacote do Adobe Analytics Prime ou Ultimate.

Se um alerta usar a detecção de anomalias, o período de treinamento varia de acordo com a granularidade selecionada para o alerta.

* Granularidade mensal: 15 meses + mesmo intervalo do ano passado
* Granularidade semanal: 15 semanas + mesmo intervalo do ano passado
* Granularidade diária: 35 dias + mesmo intervalo do ano passado
* Granularidade por hora: 336 horas

Consulte [Técnicas estatísticas usadas na detecção de anomalias](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) para mais informações.

## Criar alertas

Para obter informações sobre como criar alertas no Adobe Analytics, consulte [Criar alertas](/help/components/alerts/alert-builder.md).

>[!IMPORTANT]
>
>Usar dados com carimbo de data e hora para criar alertas pode fazer com que os alertas acionem incorretamente. A Adobe recomenda o uso de dados sem carimbo de data/hora para criar alertas.

## Gerenciar alertas

Você pode gerenciar alertas existentes no gerenciador de alertas. É possível executar várias tarefas de gerenciamento em alertas, como aplicar tags, renomear, excluir e mais.

Para obter mais informações sobre como gerenciar alertas existentes no Adobe Analytics, consulte [Gerenciar alertas](/help/components/alerts/alert-manager.md).
