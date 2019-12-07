---
description: A Adobe usa um cookie para rastrear navegadores/dispositivos únicos.
keywords: Analytics Implementation
subtopic: Visitors
title: Identificar visitantes únicos
topic: Developer and implementation
uuid: ed4dee75-ecfb-4715-8122-461983c7dd8f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Identificar visitantes únicos

A Adobe usa um cookie para rastrear navegadores/dispositivos únicos.

## Ordem da ID de visitante do Analytics {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

O Adobe Analytics fornece vários mecanismos para identificar visitantes. A tabela a seguir lista as diferentes maneiras de identificar um visitante no Analytics (na ordem de preferência):

| Ordem utilizada | Parâmetro de consulta (método de coleta) | Presente quando |
|---|---|---|
| ![](assets/step1_icon.png) | [vid (s.visitorID)](/help/implement/js-implementation/c-unique-visitors/visid-custom.md) | s.visitorID está definido |
| ![](assets/step2_icon.png) | [aid (cookie s_vi)](/help/implement/js-implementation/c-unique-visitors/visid-analytics.md) | O visitante tinha um cookie s_vi antes da implantação do serviço de ID de visitante ou o período de carência da ID de visitante está configurado. |
| ![](assets/step3_icon.png) | [mid (cookie AMCV_ definido pelo serviço de ID de visitante da Experience Cloud)](https://marketing.adobe.com/resources/help/en_US/mcvid/) | O navegador do visitante aceita cookies (originais) |
| ![](assets/step4_icon.png) | [fid (cookie de recuperação de falhas no H.25.3 ou posterior, ou AppMeasurement para JavaScript)](/help/implement/js-implementation/c-unique-visitors/visid-fallback.md) | O navegador do visitante aceita cookies (originais) |
| ![](assets/step5_icon.png) | [Endereço IP, Agente do usuário, Endereço IP de gateway](/help/implement/js-implementation/c-unique-visitors/visid-fallback.md#section_104819D74C594ECE879144FCC5DEF4BF) | O navegador do visitante não aceita cookies. |

Em vários cenários, você pode observar 2 ou 3 IDs diferentes em uma chamada, mas o Analytics utilizará a primeira ID presente na tabela anterior como sendo a ID de visitante oficial. Por exemplo, se estiver configurando uma ID de visitante personalizada (incluída no parâmetro de consulta "vid"), essa ID será utilizada antes de outras IDs que podem estar presentes na mesma ocorrência.

> [!NOTE] Cada ID de visitante do Analytics está associada a um perfil de visitante nos servidores da Adobe. Os perfis do visitante são excluídos depois de pelo menos 13 meses de inatividade, independentemente de qualquer expiração de cookie da ID do visitante.
