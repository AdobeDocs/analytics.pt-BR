---
description: Se os demais métodos de ID de visitante falharem, a Adobe definirá um cookie de fallback ou uma combinação de um endereço de IP e agente do usuário para identificar o visitante.
keywords: Analytics Implementation
title: Métodos de ID de Fallback
topic: Developer and implementation
uuid: f242d481-81f0-4287-be4f-52fd03eb01fc
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Métodos de ID de Fallback

Se os demais métodos de ID de visitante falharem, a Adobe definirá um cookie de fallback ou uma combinação de um endereço de IP e agente do usuário para identificar o visitante.

## Método de identificação do visitante de fallback {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement for JavaScript 1.x and JavaScript H.25.3 (released January 2013) contain a new fallback visitor identification method for visitors whose browser blocks the cookie set by Adobe's data collection servers (called `s_vi`). Anteriormente, se não fosse possível definir um cookie, os visitantes eram identificados com o uso de uma combinação do endereço IP e a sequência do agente de usuário durante a coleta de dados.

Com esta atualização, se o cookie padrão `s_vi` estiver indisponível, um cookie de fallback será criado com uma ID exclusiva gerado aleatoriamente. Este cookie, chamado de `s_fid`, é definido com uma expiração de 2 anos e usado como método de identificação de fallback que está avançando. Esta alteração deve resultar em maior precisão nas contagens de visitas e visitantes, nas situações em que o cookie primário (`AMCV_` ou `s_vi`) não pode ser definido.

O total de visitas inclui todos os visitantes identificados pelo cookie `s_vi` ou por meio de um método de fallback.

## Endereço IP, Agente do usuário, Endereço IP de gateway {#section_104819D74C594ECE879144FCC5DEF4BF}

. Se não for possível definir `AMCV_` ou `s_vi` e os cookies `s_fid`, os visitantes serão identificados por meio de uma combinação de endereço IP e Agente do usuário.
