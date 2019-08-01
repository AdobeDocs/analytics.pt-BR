---
description: 'null'
keywords: DFA
seo-description: 'null'
seo-title: Pré-requisitos
solution: Analytics
title: Pré-requisitos
topic: Conectores de dados
uuid: b 5 f 5 e 30 c-e 269-41 a 4-9236-5 ddc 404 bfd 94
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Pré-requisitos{#prerequisites}

Antes de iniciar a integração dos Conectores de dados da Adobe para o DFA, faça o seguinte:

* Decida se fará a integração com a versão 1.5 da integração ou se aguardará a versão 2.0. Essa decisão depende de quais recursos serão utilizados em sua conta do DFA e do período no qual você deseja fazer a integração. Consulte [Sobre a versão 2.0](../dfa-data-connector-analytics/dfa-version-differences.md#concept-2c7d6a6ab8524dccad96ea0c17228664) para obter mais informações.
* Decida como os anunciantes do DFA serão mapeados para os conjuntos de relatórios do Adobe Analytics. Por exemplo, se você tiver vários anunciantes do DFA e vários conjuntos de relatórios, deverá decidir quais anunciantes associar a quais conjuntos de relatórios.
* Implemente o código de coleta de dados da Adobe em todas as páginas que você deseja rastrear usando a versão H.22 ou uma versão posterior do código de coleta de dados.
* Saiba a ID de anunciante de uma conta do DFA que faz parte da configuração do Floodlight que você deseja integrar. A integração importa automaticamente todos os anunciantes dentro da configuração do Floodlight.
* Saiba o nome de usuário e a senha de sua conta do DFA.
* Associe cada anunciante do DFA a apenas um conjunto de relatórios do Adobe Analytics. A associação com vários conjuntos de relatórios não é compatível com a integração padrão do Genesis para o DFA.
* Adicione um parâmetro de sequência de consulta de click-through à página de aterrissagem para cada posicionamento do DFA que fará parte da integração. Esse parâmetro de sequência de consulta é necessário para contar os click-throughs corretamente.
* Configure seus posicionamentos do DFA para que eles não redirecionem os visitantes por meio de vários domínios. Por exemplo, um posicionamento não deve direcionar os participantes para um microsite hospedado em www.xyz.com se o microsite os redireciona em seguida para outro site, www.fgh.com. Se a resposta da campanha abrange vários domínios, os dados de click-through e view-through podem ser adulterados e confusos.
* Identifique uma variável personalizada no Relatórios e análises para manter as informações de sua conta.
* Identifique uma eVar do Relatórios e análises para armazenar informações de view-through do DFA. Use essa eVar somente para essa integração do DFA.
* Identifique os eventos do Relatórios e análises nos quais você deseja armazenar dados de impressões e cliques. Você pode querer renomear esses eventos da maneira adequada.
* (Opcional) Identifique os eventos do Relatórios e análises que armazenarão dados de custo do DFA. Você pode querer renomear esses eventos da maneira adequada.
* (Opcional) Identifique uma variável personalizada e um evento de sucesso do Relatórios e análises que armazenarão erros e tempos limite do DFA. Essas variáveis ajudam a diagnosticar problemas que podem surgir com a integração.
* (Opcional) Crie uma conta de email especial para receber informações e notificações relacionadas à integração dos Conectores de dados para o DFA.

