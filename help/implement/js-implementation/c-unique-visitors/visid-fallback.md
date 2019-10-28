---
description: Se os demais métodos de ID de visitante falharem, a Adobe definirá um cookie de fallback ou uma combinação de um endereço de IP e agente do usuário para identificar o visitante.
keywords: Implementação do Analytics
seo-description: Se os demais métodos de ID de visitante falharem, a Adobe definirá um cookie de fallback ou uma combinação de um endereço de IP e agente do usuário para identificar o visitante.
seo-title: Métodos de ID de Fallback
solution: Analytics
title: Métodos de ID de Fallback
topic: Desenvolvedor e implementação
uuid: f242d481-81f0-4287-be4f-52fd03eb01fc
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Métodos de ID de Fallback

Se os demais métodos de ID de visitante falharem, a Adobe definirá um cookie de fallback ou uma combinação de um endereço de IP e agente do usuário para identificar o visitante.

## Método de identificação do visitante de fallback {#section_2BA15E4FA6034C3EBF43859406343EB6}

O AppMeasurement para o JavaScript 1.x e JavaScript H.25.3, lançado em janeiro de 2013, contém um novo método de identificação de visitante de fallback para os visitantes cujo navegador bloqueia o cookie definido pelos servidores de coleta de dados da Adobe (chamado de `s_vi`). Anteriormente, se não fosse possível definir um cookie, os visitantes eram identificados com o uso de uma combinação do endereço IP e a sequência do agente de usuário durante a coleta de dados.

Com esta atualização, se o cookie padrão `s_vi` estiver indisponível, um cookie de fallback será criado com uma ID exclusiva gerado aleatoriamente. Este cookie, chamado de `s_fid`, é definido com uma expiração de 2 anos e usado como método de identificação de fallback que está avançando. Esta alteração deve resultar em maior precisão nas contagens de visitas e visitantes, nas situações em que o cookie primário (`AMCV_` ou `s_vi`) não pode ser definido.

O total de visitas inclui todos os visitantes identificados pelo cookie `s_vi` ou por meio de um método de fallback.

## Endereço IP, Agente do usuário, Endereço IP de gateway {#section_104819D74C594ECE879144FCC5DEF4BF}

. Se não for possível definir `AMCV_` ou `s_vi` e os cookies `s_fid`, os visitantes serão identificados por meio de uma combinação de endereço IP e Agente do usuário.
