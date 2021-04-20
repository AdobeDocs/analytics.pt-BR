---
description: Perguntas frequentes sobre o conector de dados do DFA.
keywords: DFA
title: Perguntas frequentes
feature: Data Connectors
uuid: 59d187e9-1ec1-4cf3-8831-b981f87c9372
exl-id: fc695d81-0d45-4a9f-a02d-8a14aadc43c7
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 97%

---

# Perguntas frequentes {#frequently-asked-questions}

## Por que o assistente do Data Connectors não aceita minhas credenciais de logon? {#section-f019b3de18774df3954af7881aa564fa}

Se você verificou se as credenciais de logon são válidas, confirme que o nome de usuário fornecido para a integração está habilitado para acesso por API. O assistente de Data Connectors usa a API do DFA para validar credenciais de logon, bem como para ativar e desativar configurações específicas da Adobe na API do DFA. O acesso por API é uma configuração que deve ser ativada na interface do DFA por um administrador. Em seguida, certifique-se de que você tenha permissão para acessar a ID de anunciante ou a ID de configuração do Floodlight selecionada no assistente.

## Por que não vejo nenhum dado das métricas carregadas durante a noite (impressões do DFA, cliques do DFA etc.)? {#section-465fd22ae6b447ffb6baf20b57daa433}

Se você está usando a versão 1.5 da integração, pode ser porque sua integração ainda não recebeu uma ID do site do cliente. Uma ID do site do cliente (CSID) é necessária para que ocorra o intercâmbio noturno e para solicitar dados do servidor de anúncio do DFA. As CSIDs podem levar até 3 dias a partir da data da integração para que seu intercâmbio seja feito com o Google. Depois que a CSID for recebida do Google, você será notificado da nova CSID pelo endereço de email da integração, juntamente com o código JavaScript mais recente.

Se você não tiver recebido o email de configuração e as métricas não estiverem fluindo após mais de 3 dias, o problema mais provável é que a CSID já foi atribuída a outra integração. O Google mantém um mapeamento 1 a 1 entre a CSID e o conjunto de relatórios, o que significa que, se uma integração em um conjunto de relatórios usa a mesma ID de anunciante de outra integração em outro conjunto de relatórios, somente a primeira integração receberá uma CSID. Para alterar para qual conjunto de relatórios ou ID de anunciante uma CSID é mapeada, um ticket deve ser aberto com o Suporte do Google.

Por exemplo, suponhamos que há uma integração no conjunto de relatórios A com a ID de anunciante Z que recebe uma CSID. Se outra integração é configurada posteriormente no conjunto de relatórios B com a ID de anunciante Z, essa nova integração NÃO receberá a CSID novamente. Para isso, será necessário um ticket do Google. Por outro lado, se uma integração é configurada no conjunto de relatórios A com a ID de anunciante Z, e posteriormente outra integração é configurada no conjunto de relatórios A, a ID de anunciante Z é configurada. Somente a primeira integração receberá os dados da integração; no entanto, neste caso, a primeira integração poderá ser desativada, e os dados fluirão para a segunda integração.

>[!NOTE]
>
>As CSIDs não são usadas na versão 2.0 da integração, portanto o processo de negociação da CSID não se aplica.

## Estou usando a versão 2.0 da integração, e as métricas de custo não estão aparecendo para meus anúncios do DFA. O que pode estar acontecendo?  {#section-805748111bbe4bbf918d6dbbb2641fff}

As métricas de custo devem ser ativadas no DFA do Google e fornecidas na interface do DFA, bem como ativadas no assistente dos Data Connectors. A primeira coisa a verificar é se você mapeou um evento do Analytics para o custo de mídia do DFA e informou um código de moeda. Se você mapeou o evento de custo de média e concluiu e salvou o assistente, o indicador omnitureCostData do DFA será ativado na API do DFA. Isso avisará o Google de que as métricas devem ser enviadas no arquivo noturno. Você pode verificar novamente na interface do DFA se o omnitureCostData está habilitado por meio das propriedades no Floodlight integrado. Por fim, após verificar esses dois lugares, verifique se os anúncios que fazem parte do Floodlight integrado especificam dados de custo e estruturas de custo. Se os dados de custo não forem fornecidos na interface do DFA, eles não serão exibidos no Analytics.

## Por que alguns anúncios não mostram nenhuma impressão do DFA ou view-throughs, mas mostram cliques e click-throughs?  {#section-39b2eeeefd7f43d1a373df0b987bacef}

Há alguns anúncios que só registram dados de cliques, chamados rastreadores de cliques. Esse tipo de anúncio não informa dados de última impressão a partir do momento em que o servidor Floodlight é consultado. Para verificar se um determinado anúncio é um anúncio rastreador de cliques ou anúncio somente de cliques, entre em contato com o órgão do DFA ou com o representante do Suporte do Google.

## Por que não há click-throughs para anúncios que mostram cliques do DFA? {#section-758c1f1fc5b54bfc9294dcdc71bbd96a}

Pode haver muitas respostas para essa pergunta.

Primeiro, verifique se o anúncio em questão tem um URL de página de aterrissagem que (a) está marcado com o código da Adobe para o mesmo conjunto de relatórios no qual você está vendo a discrepância e (b) contém o parâmetro de sequência de consulta *`clickThroughParam`*.

Em segundo lugar, verifique se possui uma integração funcional seguindo as etapas em [Confirmar uma integração do DFA bem-sucedida](../dfa-data-connector-analytics/dfa-integration.md). Se aparecer um código de rastreamento do DFA com o hit da Adobe na página inicial, esse click-through deverá aparecer no relatório de campanhas do DFA. Se não estiver visualizando o relatório, verifique se os conjuntos de relatórios correspondem entre a variável *`s.account`* da página inicial e o conjunto de relatórios que está sendo visualizado no Reports &amp; Analytics. Se eles coincidirem, busque por códigos de rastreamento no relatório da eVar de View Through no formato DFA:XXX:XXX:XXX:llXXX:XXX:XXX:XXX:XXX.

Eles indicam falhas da regra do VISTA do DFA em processar os dados brutos do DFA. Esse problema pode ser resolvido abrindo um tíquete de suporte por meio do Representante de conta do Adobe.

Se nenhuma das soluções acima explicar o problema, consulte [Comparação de discrepâncias de métricas](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md) para explorar outras possibilidades.
