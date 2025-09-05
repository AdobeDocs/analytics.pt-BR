---
title: Métricas de qualidade de serviços de mídia de transmissão
description: Métricas disponíveis ao habilitar a [!UICONTROL Qualidade de mídia] para um conjunto de relatórios.
feature: Metrics
exl-id: a64829b5-d45b-44c6-80c3-5acf1a6d9919
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 1%

---

# Métricas de qualidade de serviços de mídia de transmissão

*Esta página descreve as métricas disponíveis quando você habilita a [!UICONTROL Qualidade de Mídia] para um conjunto de relatórios. Consulte [Dimensões de qualidade dos serviços de mídia de streaming](../dimensions/sm-quality.md) para ver as dimensões disponíveis.*

As métricas de qualidade dos serviços de mídia de transmissão fornecem funcionalidade de relatórios complementar para a coleta de dados por meio de bibliotecas de serviços de mídia de transmissão. O uso dessas métricas exige o **[!UICONTROL Complemento de mídia do Adobe Analytics para streaming]**. Entre em contato com a equipe de conta da Adobe para obter mais detalhes.

Quando você habilita a **[!UICONTROL Qualidade de mídia]** em [Relatórios de mídia](/help/admin/tools/manage-rs/edit-settings/media-management.md), as seguintes métricas estão disponíveis:

| Nome da métrica | Descrição | Enviado com | Variável de dados de contexto |
| --- | --- | --- | --- |
| Taxa média de bits | Uma média ponderada de todos os valores de taxa de bits para a duração da reprodução de uma sessão de reprodução. | Fechamento de mídia | `a.media.qoe.bitrateAverage` |
| Fluxos afetados pela alteração na taxa de bits | Um booleano que é acionado se a taxa de bits for alterada pelo menos uma vez durante uma sessão de reprodução. | Fechamento de mídia | `a.media.qoe.bitrateChange` |
| Alterações na taxa de bits | O número de vezes que a taxa de bits mudou. | Fechamento de mídia | `a.media.qoe.bitrateChangeCount` |
| Fluxos afetados pelo buffer | Um booleano que é acionado se o vídeo entrar em um estado de Buffer pelo menos uma vez. | Fechamento de mídia | `a.media.qoe.buffer` |
| Eventos de buffer | O número de vezes que o vídeo foi armazenado em buffer durante uma sessão de reprodução. | Fechamento de mídia | `a.media.qoe.bufferCount` |
| Duração total do buffer | A quantidade de tempo que um vídeo passou armazenando em buffer em todos os eventos de buffer, em segundos. | Fechamento de mídia | `a.media.qoe.bufferTime` |
| Quedas antes do início | Um booleano que é acionado se um usuário sair antes do início do conteúdo principal de um vídeo. | Fechamento de mídia | `a.media.qoe.dropBeforeStart` |
| Quadros soltos | Um número inteiro que representa o número total de quadros que foram descartados durante uma sessão de reprodução. | Fechamento de mídia | `a.media.qoe.droppedFrameCount` |
| Fluxos afetados por quedas de quadros | Um booleano que é acionado quando qualquer quadro é descartado durante uma sessão de reprodução. | Fechamento de mídia | `a.media.qoe.droppedFrames` |
| Fluxos afetados pelo erro | Um booleano que é acionado quando um vídeo apresenta um erro a qualquer momento durante uma sessão de reprodução. | Fechamento de mídia | `a.media.qoe.error` |
| Eventos de erro | Um número inteiro que representa o número total de erros encontrados durante uma sessão de reprodução. | Fechamento de mídia | `a.media.qoe.errorCount` |
| Hora de início | O tempo gasto para iniciar um vídeo, em milissegundos. O Adobe converte e armazena esse valor em segundos. | Fechamento de mídia | `a.media.qoe.timeToStart` |
