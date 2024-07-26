---
title: Métricas de metadados de vídeo de mídia de transmissão
description: Métricas disponíveis ao habilitar [!UICONTROL Metadados de vídeo] para um conjunto de relatórios.
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 5%

---

# Métricas de metadados de vídeo de mídia de transmissão

*Esta página descreve as métricas disponíveis quando você habilita os [!UICONTROL Metadados de vídeo] para um conjunto de relatórios. Consulte [dimensões de metadados de vídeo de streaming de mídia](../dimensions/sm-video-metadata.md) para dimensões disponíveis.*

As métricas de metadados de vídeo de mídia de transmissão fornecem funcionalidade de relatórios complementar para a coleção de dados por meio de bibliotecas de coleção de mídia de transmissão. O uso dessas métricas exige o **[!UICONTROL Complemento de Coleção de Mídia de Streaming Adobe]**. Entre em contato com a equipe de conta do Adobe para obter mais detalhes.

Ao habilitar os **[!UICONTROL Metadados de vídeo]** em [Relatórios de mídia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), a seguinte métrica estará disponível:

| Nome da métrica | Descrição | Enviado com | Variável de dados de contexto |
| --- | --- | --- | --- |
| Autorizado | Um booleano que é acionado quando o usuário é autorizado por meio da autenticação Adobe. | Início da mídia, Fechamento da mídia | `a.media.pass.auth` |

{style="table-layout:auto"}
