---
description: Tabela de pesquisa para determinar o tipo de um hit com base no valor de page_event.
keywords: Data Feed;page;event;page_event;post_page_event
title: Pesquisa de evento da página
topic: Reports and analytics
uuid: 73af597c-5560-466e-94b2-ddd1d64797c8
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Pesquisa de evento da página

Tabela de pesquisa para determinar o tipo de um hit com base no valor de page_event.

| Tipo de ocorrência | `page_event` value | `post_page_event` value |
| --- | --- | --- |
| Exibições de página | 0: Todas as chamadas de exibição de página e `trackState` chamadas do SDK móvel | Mesmo valor que `post_page_event` |
| Rastreamento de link | 10: Links e `trackAction` chamadas personalizados no SDKs<br>11 móveis: Links de download<br>12: Links de saída | 100: Links e `trackAction` chamadas personalizados no SDKs<br>101 móveis: Links de download<br> 102: Links de saída |
| Vídeo Milestone | 31: Início da mídia<br> 32: Atualizações de mídia (sem processamento de outra variável)<br>33: Atualizações de mídia (com outras variáveis) | 76: Início da mídia<br> 77: Atualizações de mídia (sem processamento de outra variável)<br>78: Atualizações de mídia (com outras variáveis) |
| Vídeo de heartbeat | 50: Início do fluxo de mídia (não Primetime)<br>51: Fechamento do fluxo de mídia (não Primetime)<br>52: Depuração do fluxo de mídia (não Primetime)<br>53: O fluxo de mídia mantém-se ativo (não Primetime)<br>54: Início do anúncio de fluxo de mídia (não Primetime)<br>55: Fechamento de anúncio de fluxo de mídia (não Primetime)<br>56: Depuração de anúncio de fluxo de mídia (não Primetime)<br>60: Início do fluxo de mídia Primetime<br>61: Fechamento do fluxo de mídia Primetime<br>62: Depuração do fluxo de mídia Primetime<br>63: O fluxo de mídia Primetime mantém-se ativo<br>64: Início de anúncio do fluxo de mídia Primetime<br>65: Fechamento de anúncio de fluxo de mídia Primetime<br>66: Depuração anúncio de fluxo de mídia Primetime | Mesmo valor que `post_page_event` |
| Survey | 40: Qualquer chamada gerada pelo Survey | 80: Qualquer chamada gerada pelo Survey |
| Analytics para o Target | 70: Ocorrência inclui dados de atividade do Target | Mesmo valor que `post_page_event` |
