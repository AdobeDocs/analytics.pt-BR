---
title: Métricas de metadados de vídeo de serviços de mídia de transmissão
description: Métricas disponíveis ao habilitar [!UICONTROL Metadados de vídeo] para um conjunto de relatórios.
feature: Metrics
exl-id: b2f60a34-e139-4498-bf71-74d291759ef2
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 5%

---

# Métricas de metadados de vídeo de serviços de mídia de transmissão

*Esta página descreve as métricas disponíveis quando você habilita os [!UICONTROL Metadados de vídeo] para um conjunto de relatórios. Consulte [Dimensões de metadados de vídeo de serviços de mídia de streaming](../dimensions/sm-video-metadata.md) para obter as dimensões disponíveis.*

As métricas de metadados de vídeo dos serviços de mídia de transmissão fornecem funcionalidade de relatórios complementar para a coleta de dados por meio de bibliotecas de serviços de mídia de transmissão. O uso dessas métricas exige o **[!UICONTROL Complemento de mídia do Adobe Analytics para streaming]**. Entre em contato com a equipe de conta da Adobe para obter mais detalhes.

Ao habilitar os **[!UICONTROL Metadados de vídeo]** em [Relatórios de mídia](/help/admin/tools/manage-rs/edit-settings/media-management.md), a seguinte métrica estará disponível:

| Nome da métrica | Descrição | Enviado com | Variável de dados de contexto |
| --- | --- | --- | --- |
| Autorizado | Um booleano que é acionado quando o usuário é autorizado por meio da autenticação da Adobe. | Início da mídia, Fechamento da mídia | `a.media.pass.auth` |

{style="table-layout:auto"}
