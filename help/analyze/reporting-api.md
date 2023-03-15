---
description: Recursos e links para a API de relatórios.
title: API em relatórios do Analytics
uuid: 68ec3490-6e47-4606-860d-dd5e89c574a1
feature: API
role: Developer
exl-id: 003a8b83-6ef0-4313-903a-b76078558d55
source-git-commit: 8f25dfefbc6fba1fb525d2e9e0fce654e21ef362
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 100%

---

# API em relatórios do Analytics

A documentação das APIs do Adobe Analytics está no [Adobe Developer](https://developer.adobe.com/analytics-apis/docs/2.0/).

## Comparação de APIs do Analytics

| **Tipo de API** | **Completamente processados** | **Tempo real** | **Livestream** | **Data Warehouse** |
| --- | --- | --- | --- | --- |
| **Descrição** | Dados completamente processados e finalizados, disponíveis em todas as interfaces do Analytics. | Métricas parcialmente processadas e limitadas, disponíveis em segundos de coleta. | Dados de ocorrências parcialmente processadas, disponíveis em segundos de coleta. | Dados completamente processados e finalizados, usados para extrair grandes exportações de dados. |
| [**Latência**](/help/technotes/latency.md) | 30 a 90 minutos | Segundos -10 minutos | Segundos -10 minutos | 90+ minutos |
| **Conclusão do processamento** | Máximo | Parcial | Parcial | Máximo |
| **Interfaces de relatórios** | Analysis Workspace, Reports &amp; Analytics, Report Builder, API | Relatório em tempo real no Reports &amp; Analytics, Report Builder, API 1.4 | Somente API | Data Warehouse, API |
| **Granularidade de dados** | Resumo | Resumo | Nível de ocorrência | Resumo |
| **Processamento do perfil do visitante** | Sim | Não | Não | Sim |
| **Suporte de segmento** | Sim | Não | Não | Parcial |
