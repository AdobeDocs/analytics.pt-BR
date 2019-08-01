---
description: 'No momento, há três versões da integração do DFA: 1.0, 1.5 e 2.0.'
keywords: DFA
seo-description: 'No momento, há três versões da integração do DFA: 1.0, 1.5 e 2.0.'
seo-title: Diferenças entre versões
solution: Analytics
title: Diferenças entre versões
topic: Conectores de dados
uuid: e 0 ae 70 f 0-369 d -451 a -9752-02660 d 270660
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Diferenças entre versões{#version-differences}

No momento, há três versões da integração do DFA: 1.0, 1.5 e 2.0.

A tabela a seguir resume os recursos de cada versão da integração.

| Recurso | Versão 1.0 | Versão 1.5 | Versão 2.0 |
|---|---|---|---|
| Métricas noturnas de cliques e impressões do DFA | Sim | Sim | Sim |
| Rastreamento de click-through e view-through | Sim | Sim | Sim |
| A integração recebe dados em um nível de anunciante | Não | Sim | Sim |
| A integração recebe dados em um nível de configuração do Floodlight | Não | Não | Sim |
| Métricas de custo | Não | Não | Sim |
| Métricas de criação | Não | Não | Sim |
| Sequências de consulta acima de 2.000 bytes | Não | Sim | Sim |
| Usa o módulo Integrate para uma coleta de dados de terceiros ideal | Não | Sim | Sim |
| Rastreamento de tempo limite e erros | Não | Sim | Sim |
| Sem necessidade de negociação da ID do cliente | Não | Não | Sim |

## Sobre a versão 1.5 {#section-b5a3e967cfa141ea8f740612336181be}

A versão 1.5 da integração introduz o módulo Integrate ao JavaScript da página de aterrissagem. O módulo Integrate possibilita solicitações de tamanho fixo ao servidor de anúncios do DFA (ad.doubleclick.net), o que supera os limites de solicitação de 2.000 bytes da integração anterior. Ela também introduz um tempo limite que pode ser configurado, *`s.maxDelay`*, para continuar coletando dados de visitante da Adobe quando ocorrerem quedas de rede. Erros e tempos limite também podem ser capturados em variáveis do Analytics.

A ilustração a seguir mostra interações de rede na página de aterrissagem na versão 1.5.

![](assets/DFA_About_1_5.png)

Na versão 1.5, o módulo Integrate (2) solicita dados do servidor Floodlight (3). O servidor Floodlight redirecionará para o servidor de anúncios do DFA, que apresentará dados sobre o visitante da mesma forma que a versão 1.0. Ele fará um redirecionamento 302 (4) para um serviço de tradução especial no integrate.112.2o7.net, que transformará a estrutura de resposta em um objeto JSON. O módulo Integrate consome esse objeto JSON e passa a informação para o rastreamento da Adobe (5).

A migração da versão 1.0 para a versão 1.5 da integração envolve uma alteração de JavaScript. Para obter esse JavaScript, faça logon em sua conta Adobe Online Marketing Suite, escolha o produto Genesis, clique em Editar na integração do DFA e trabalhe com o assistente. Desde que uma ID do cliente tenha sido atribuída anteriormente, você imediatamente receberá o novo código JavaScript por email depois de salvar a integração. Quando receber o código, também será necessária a nova versão do s_code central, que contém o módulo Integrate. Esse código pode ser solicitado do gerente da conta ou do consultor de implementação.

Um recurso importante do novo código JavaScript é que não há alteração de implementação necessária entre as versões 1.5 e 2.0.

## Sobre a versão 2.0 {#section-afd56de0c56c4489bb5ddc5798d6709a}

A versão mais recente da integração do DFA traz dados para uma configuração do Floodlight. Antes da versão 2.0, as integrações individuais eram associadas a um único anunciante do DFA. Com essa mudança, as métricas de cliques, impressões e custo de toda a configuração do Floodlight serão incluídas no conjunto de relatórios integrados. Também é possível rastrear view-throughs entre sites, quando os dois sites estão dentro da mesma configuração do Floodlight.

As métricas de custo de mídia também estão disponíveis a partir da versão 2.0 da integração. Para habilitar as métricas de custo de mídia para uma integração, você deve escolher um evento do Relatórios e análises para custo de mídia no assistente do Genesis, bem como especificar a moeda dos números da métrica na interface do DFA.

As ocorrências de tempo limite devem diminuir com a integração 2.0, já que os redirecionamentos 302 foram eliminados. A eliminação desses saltos deve diminuir as ocorrências de tempo limite e aumentar a quantidade de dados do DFA que você pode integrar.

Se uma configuração do Floodlight é uma configuração compartilhada no DFA, a atualização da versão 1. 5 para a versão 2.0 faz com que os dados de conversão de todos os anunciantes compartilhados dentro da configuração do Floodlight sejam incluídos no conjunto de relatórios.

## Atualização para a versão 2.0 {#section-f0bf90b9a7a1434ab1540b6c0999f4c7}

A tabela a seguir descreve os proprietários para migração para versões mais recentes da integração:

| Migração | Proprietário | Tarefas |
|---|---|---|
| Versão 1.0 para 1.5 | Cliente | Implementar a versão 1.5 do JavaScript com o módulo Integrate. |
| Versão 1.5 para 2.0 | Cliente | O cliente inicia uma discussão com o Google a respeito de períodos de atualização. Após a aprovação, o Google habilita a Veiculação de anúncios avançada. |

