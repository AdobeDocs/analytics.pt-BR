---
description: A Adobe usa um cookie para rastrear navegadores/dispositivos únicos.
keywords: Implementação do Analytics
seo-description: A Adobe usa um cookie para rastrear navegadores/dispositivos únicos.
seo-title: Identificar visitantes únicos
solution: Analytics
subtopic: Visitantes
title: Identificar visitantes únicos
topic: Desenvolvedor e implementação
uuid: ed 4 dee 75-ecfb -4715-8122-461983 c 7 dd 8 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Identificar visitantes únicos

A Adobe usa um cookie para rastrear navegadores/dispositivos únicos.

## Ordem da ID de visitante do Analytics {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

O Adobe Analytics fornece vários mecanismos para identificar visitantes. A tabela a seguir lista as diferentes maneiras de identificar um visitante no Analytics (na ordem de preferência):

| Ordem utilizada | Parâmetro de consulta (método de coleta) | Presente quando |
|---|---|---|
| ![](assets/step1_icon.png) | [vid (s.visitorID)](../../../implement/js-implementation/c-unique-visitors/visid-custom.md#concept_4A2000F4B6ED41E99CA6118A6D74ECE8) | s.visitorID está definido |
| ![](assets/step2_icon.png) | [aid (cookie s_vi)](../../../implement/js-implementation/c-unique-visitors/visid-analytics.md#concept_74F6B4B9B2FA415AB5D029A1F8F099BC) | O visitante tinha um cookie s_vi antes da implantação do serviço de ID de visitante ou o período de carência da ID de visitante está configurado. |
| ![](assets/step3_icon.png) | [mid (cookie AMCV_ definido pelo serviço de ID de visitante da Experience Cloud)](https://marketing.adobe.com/resources/help/en_US/mcvid/) | O navegador do visitante aceita cookies (originais) |
| ![](assets/step4_icon.png) | [fid (cookie de recuperação de falhas no H.25.3 ou posterior, ou AppMeasurement para JavaScript)](../../../implement/js-implementation/c-unique-visitors/visid-fallback.md#concept_EBCBF9EB390E45A2BA20DB6BE931C505) | O navegador do visitante aceita cookies (originais) |
| ![](assets/step5_icon.png) | [Endereço IP, Agente do usuário, Endereço IP de gateway](../../../implement/js-implementation/c-unique-visitors/visid-fallback.md#section_104819D74C594ECE879144FCC5DEF4BF) | O navegador do visitante não aceita cookies. |

Em vários cenários, você pode observar 2 ou 3 IDs diferentes em uma chamada, mas o Analytics utilizará a primeira ID presente na tabela anterior como sendo a ID de visitante oficial. Por exemplo, se estiver configurando uma ID de visitante personalizada (incluída no parâmetro de consulta "vid"), essa ID será utilizada antes de outras IDs que podem estar presentes na mesma ocorrência.

>[!NOTE]
>
>Cada ID de visitante do Analytics está associada a um perfil de visitante em servidores da Adobe. Os perfis do visitante são excluídos depois de pelo menos 13 meses de inatividade, independentemente de qualquer expiração de cookie da ID do visitante.
