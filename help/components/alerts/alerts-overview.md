---
description: Entenda como usar alertas para obter um controle granular das notificações e uma integração com a detecção de anomalias.
title: Visão geral de alertas
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
TQID: 'https://experienceleague.adobe.com/FDzJzBjxMc-EkhW0k0NiENt-g53sRnzXQDs1XQWFseI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b0ca67c6-0a35-482c-ad91-baac1bcb26d6
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 435
ht-degree: 53%

---

# Visão geral de alertas

Os alertas no Adobe Analytics permitem que você receba uma notificação com base em porcentagens alteradas ou pontos de dados específicos.

Dependendo do pacote do Adobe Analytics, também é possível usar alertas que são acionados com base em limites de anomalias. Esses alertas (também conhecidos como *Alertas inteligentes*) fornecem controles granulares que se integram à [Detecção de anomalias](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md), acionando quando você mais precisa deles.

Os alertas inteligentes permitem:

* Visualizar a frequência de disparo de um alerta.
* Enviar alertas por email ou SMS com links para projetos do Analysis Workspace gerados automaticamente.
* Criar alertas *empilhados* que capturam várias métricas em um único alerta.
* Criar alertas com base em:
   * As anomalias nas métricas existentes estão acima ou abaixo dos valores limite esperados.

     [A detecção de anomalias](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) cria um valor esperado além de um limite superior e inferior usando dados históricos. Se o valor da métrica real ultrapassar o limite superior ou ficar abaixo do limite inferior definido como o valor do limite, esse evento será considerado uma anomalia no nível de confiança do limite e acionará o alerta. Um limite mais alto (por exemplo: 99% ou 99,9%) implica uma banda mais ampla, o que resulta em menos alertas causados por anomalias mais extremas. Um limite mais baixo (por exemplo: 90%) implica uma faixa mais estreita, o que resulta em mais alertas causados por anomalias menos extremas.
   * Alterações nas métricas em uma porcentagem específica.
   * Métricas acima, abaixo ou igual a um valor específico. (disponível somente para clientes do Adobe Analytics com um pacote Select, Prime ou Ultimate)

Este [tutorial em vídeo](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/data-science/intelligent-alerts) fornece uma visão geral básica dos alertas.


## Pesquisa de anomalias para alertas

>[!NOTE]
>
>O uso de alertas com detecção de anomalias (também conhecidos como _Alertas inteligentes_) está disponível somente para organizações com um pacote do Adobe Analytics Prime ou Ultimate.

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
>Usar dados com carimbo de data e hora para criar alertas pode fazer com que os alertas disparem incorretamente. A Adobe recomenda o uso de dados sem carimbo de data/hora para criar alertas.

## Gerenciar alertas

Você pode gerenciar alertas existentes no gerenciador de alertas. Você pode executar várias tarefas de gerenciamento de alertas, como marcar, renomear, excluir e muito mais.

Para obter mais informações sobre como gerenciar alertas existentes no Adobe Analytics, consulte [Gerenciar alertas](/help/components/alerts/alert-manager.md).
