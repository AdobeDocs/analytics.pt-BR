---
description: Recursos e links para a API de relatórios.
title: API em relatórios do Analytics
uuid: 68ec3490-6e47-4606-860d-dd5e89c574a1
feature: API
role: Developer
exl-id: 003a8b83-6ef0-4313-903a-b76078558d55
source-git-commit: a9d892ab8caaeb797fbbd9b5aa136c5dab76f8bd
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 73%

---

# API em relatórios do Analytics

A documentação das APIs do Adobe Analytics está em [Adobe I/O](https://adobe.io/analytics-apis/docs).

## Comparação de APIs do Analytics

| **Tipo de API** | **Completamente processados** | **Tempo real** | **Livestream** | **Data Warehouse** |
| --- | --- | --- | --- | --- |
| **Descrição** | Dados completamente processados e finalizados, disponíveis em todas as interfaces do Analytics. | Métricas parcialmente processadas e limitadas, disponíveis em segundos de coleta. | Dados de ocorrências parcialmente processadas, disponíveis em segundos de coleta. | Dados completamente processados e finalizados, usados para extrair grandes exportações de dados. |
| [**Latência**](/help/technotes/latency.md) | 30 a 90 minutos | Segundos -10 minutos | Segundos -10 minutos | Mais de 90 minutos |
| **Conclusão do processamento** | Máximo | Parcial | Parcial | Máximo |
| **Interfaces de relatórios** | Analysis Workspace, Reports &amp; Analytics, Report Builder, API | Relatório em tempo real no Reports &amp; Analytics, Report Builder, 1.4 API | Somente API | Data Warehouse, API |
| **Granularidade de dados** | Resumo | Resumo | Nível de ocorrência | Resumo |
| **Processamento do perfil do visitante** | Sim | Não | Não | Sim |
| **Suporte ao segmento** | Sim | Não | Não | Parcial |
