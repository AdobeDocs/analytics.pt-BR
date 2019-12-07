---
description: Tabela de pesquisa para determinar o tipo de um hit com base no valor de page_event.
keywords: Data Feed;page;event;page_event;post_page_event
title: Pesquisa de evento da página
topic: Reports and analytics
uuid: 73af597c-5560-466e-94b2-ddd1d64797c8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Pesquisa de evento da página

Tabela de pesquisa para determinar o tipo de um hit com base no valor de page_event.

| Tipo de ocorrência | `page_event` valor | `post_page_event` valor |
| --- | --- | --- |
| Exibições de página | 0: Todas as chamadas de exibição de página e `trackState` chamadas do SDK móvel | Mesmo valor que `post_page_event` |
| Rastreamento de link | 10: Links e `trackAction` chamadas personalizados no SDKs<br>11 móveis: Links<br>de download 12: Links de saída | 100: Links personalizados e `trackAction` chamadas no SDK<br>101 móvel: Baixar links<br>102: Links de saída |
| Vídeo marco | 31: Início<br>da mídia 32: Atualizações de mídia (sem processamento de outra variável)<br>33: Atualizações de mídia (com outras variáveis) | 76: Início<br>da mídia 77: Atualizações de mídia (sem processamento de outra variável)<br>78: Atualizações de mídia (com outras variáveis) |
| Vídeo de heartbeat | 50: Início do fluxo de mídia (não Primetime)<br>51: Fechamento do fluxo de mídia (não Primetime)<br>52: Depuração de fluxo de mídia (não Primetime)<br>53: Mantenha vivo o fluxo de mídia (não Primetime)<br>54: Início do anúncio de fluxo de mídia (não Primetime)<br>55: Fluxo de mídia e fechamento (não Primetime)<br>56: Depuração de fluxo de mídia e depuração (não Primetime)<br>60: Início<br>do fluxo de mídia Primetime: Fechamento<br>do fluxo de mídia Primetime: Depuração<br>do fluxo de mídia Primetime 63: O fluxo de mídia Primetime mantém vivo<br>64: Início<br>do fluxo de mídia Primetime: Fluxo de mídia Primetime e fechamento<br>66: Depuração de fluxo de mídia Primetime | Mesmo valor que `post_page_event` |
| Survey | 40: Qualquer chamada gerada pelo Survey | 80: Qualquer chamada gerada pelo Survey |
| Analytics para o Target | 70: Ocorrência inclui dados de atividade do Target | Mesmo valor que `post_page_event` |
