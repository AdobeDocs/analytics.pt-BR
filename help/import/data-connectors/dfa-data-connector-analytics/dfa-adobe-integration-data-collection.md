---
description: A figura a seguir mostra como funciona a coleta de dados.
keywords: DFA
seo-description: A figura a seguir mostra como funciona a coleta de dados.
seo-title: Coleta de dados em tempo real da Adobe Integration
solution: Analytics
title: Coleta de dados em tempo real da Adobe Integration
topic: Conectores de dados
uuid: 5 dce 319 c -7 d 4 b -4475-8 e 6 d-dc 5 c 972 a 82 e 9
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Integração da Adobe: coleta de dados em tempo real{#adobe-integration-real-time-data-collection}

A figura a seguir mostra como funciona a coleta de dados.

![](assets/DFA_data_collection.png)

A parte de coleta de dados da integração da Adobe começa quando o visitante chega à página de aterrissagem (1). O código de coleta de dados da Adobe em execução na página de aterrissagem não tem conhecimento do histórico do visitante com os anúncios apresentados. A equipe do Google DFA coordenou um serviço em execução no servidor do DFA Floodlight para permitir que o código da Adobe consulte informações do anúncio sobre o visitante atualmente no site (2). Para obter esses dados, ele atrasa temporariamente o beacon de imagem da Adobe e solicita os dados do servidor Floodlight.

Quando os dados chegam, ou demoram muito, ele dispara a notificação para os servidores de rastreamento da Adobe (3).

O módulo Integrate é um módulo JavaScript central especial da Adobe que causa o atraso do beacon de imagem da Adobe, aguardando a solicitação de um terceiro por um período específico ( *`s.maxDelay`*). *`s.maxDelay`* define quanto tempo o módulo Integrate aguardará pelos dados do servidor do DFA Floodlight antes de disparar a tag de imagem para o navegador do visitante. Esse comportamento é importante para que os dados básicos do visitante ainda sejam coletados, mesmo quando os servidores do DFA Floodlight estiverem inativos ou muito sobrecarregados. Se os dados do Floodlight chegarem antes de o *`s.maxDelay`* expirar, os dados de rastreamento da Adobe serão disparados imediatamente e conterão os dados adicionais do DFA.

Quando o tempo limite é atingido, o código da página pode especificar um evento do Relatórios e análises da Adobe para uso como um evento de tempo limite. Esse evento é útil no diagnóstico de problemas com a integração ou no ajuste do *`s.maxDelay`*. Em casos de ocorrências de tempos limite em excesso, aumente o *`s.maxDelay`*. *`s.maxDelay`* pode ser definido muito alto, no entanto, nesse caso, os visitantes podem ter o potencial de deixar o site antes do *`s.maxDelay`* tempo expirar. For more discussion on this topic, see [Tuning s.maxDelay](../dfa-data-connector-analytics/dfa-integration/dfa-tuning-s-maxlelay.md#concept-6deb28eee18e414db220d6009d449f0d).

Às vezes, o servidor Floodlight responde com erros sobre o visitante. Isso normalmente ocorre quando o servidor Floodlight não sabe nada sobre o visitante, pois o visitante ainda não viu nenhum anúncio ou não tem um cookie de visitante do DFA. O código da página pode especificar uma variável de conversão personalizada (eVar) que coletará esses erros e poderá ajudar na solução de problemas de implementação ou apontar problemas na transação do Google. Os erros mais comuns são Sem histórico, Sem cookie, Erro de consulta e Cancelou a inscrição, conforme descrito na tabela a seguir:

| Erro | Nome | Descrição |
|---|---|---|
| nh | Sem histórico | O visitante não visualizou ou clicou em nenhum anúncio. |
| nc | Sem cookie | O visitante não tem um cookie de visitante do DFA. |
| qe | Erro de consulta | Houve um erro na consulta de dados do servidor Floodlight. |
| oo | Cancelou a inscrição | O visitante cancelou a inscrição nas impressões/no rastreamento de cliques do Google. |

