---
description: 'null'
keywords: DFA
title: Perguntas frequentes
topic: Data connectors
uuid: 59d187e9-1ec1-4cf3-8831-b981f87c9372
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Perguntas frequentes {#frequently-asked-questions}

## Por que o assistente do Data Connectors não aceita minhas credenciais de logon? {#section-f019b3de18774df3954af7881aa564fa}

Se você verificou que as credenciais de logon são válidas, verifique se o nome de usuário fornecido para a integração está habilitado para acesso à API. O assistente de Data Connectors usa a API do DFA para validar credenciais de logon, bem como para ativar e desativar configurações específicas da Adobe na API do DFA. O Acesso à API é uma configuração que deve ser ativada na interface do DFA por um administrador. Em seguida, verifique se você tem permissão para acessar a ID do anunciante ou a ID de configuração do Floodlight selecionada no assistente.

## Por que não vejo nenhum dado das métricas carregadas durante a noite (impressões do DFA, cliques do DFA etc.)? {#section-465fd22ae6b447ffb6baf20b57daa433}

Se você estiver usando a versão 1.5 da integração, isso pode ocorrer porque sua integração ainda não recebeu uma ID do site do cliente. Uma ID do site do cliente (CSID) é necessária para que ocorra a troca noturna e para solicitar dados do servidor de anúncios do DFA. As CSIDs podem levar até 3 dias a partir da data de integração para serem trocadas com o Google. Depois que a CSID for recebida do Google, você será notificado da nova CSID pelo endereço de email da integração, juntamente com o código JavaScript mais recente.

Se tiver mais de 3 dias e você não tiver recebido o email de configuração e as métricas não estiverem fluindo, o problema mais provável é que a CSID já tenha sido atribuída a outra integração. O Google mantém um mapeamento de 1 a 1 entre CSID e Report Suite, o que significa que, se uma integração em um conjunto de relatórios usar a mesma ID de anunciante de outra integração em outro conjunto de relatórios, somente a primeira será atribuída a uma CS ID. Para alterar para qual conjunto de relatórios ou ID de anunciante uma CSID está mapeada, um ticket deve ser aberto com o Suporte do Google.

Por exemplo, considere que há uma integração no conjunto de relatórios A com a ID de anunciante Z que recebe uma CSID. Se outra integração for configurada posteriormente no conjunto de relatórios B com o anunciante Z, essa integração mais recente NÃO será atribuída à CSID novamente. Isso exigiria um ingresso do Google. Por outro lado, veja o exemplo de uma integração no conjunto de relatórios A, com a ID de anunciante Z e, posteriormente, outra integração no conjunto de relatórios A, o anunciante Z é configurado. Apenas a primeira integração receberá dados para a integração; no entanto, nesse caso, a primeira integração pode ser desativada e os dados fluirão para a segunda integração.

>[!NOTE] As CSIDs não são usadas na versão 2.0 da integração, portanto o processo de negociação da CSID não se aplica.

## Estou usando a versão 2.0 da integração e as métricas de custo não estão aparecendo nos meus anúncios do DFA. O que pode estar acontecendo? {#section-805748111bbe4bbf918d6dbbb2641fff}

As métricas de custo devem ser ativadas no DFA do Google e fornecidas na interface do DFA, bem como ativadas no assistente dos Data Connectors. O primeiro ponto a ser verificado é que você mapeou um evento do Analytics para o custo de mídia do DFA e forneceu um código de moeda. Se você mapeou o evento de custo de mídia e concluiu e salvou o assistente, o sinalizador omnitureCostData do DFA será ativado na API do DFA. Isso indicará ao Google que as métricas devem ser enviadas no arquivo noturno. Você pode verificar por meio da interface do DFA se o omnitureCostData está ativado, observando as propriedades no Floodlight integrado. Por fim, depois de verificar esses dois lugares, verifique se os anúncios que fazem parte do Floodlight integrado especificam os dados de custo e as estruturas de custo. Se os dados de custo não forem fornecidos na interface do DFA, eles não serão exibidos no Analytics.

## Por que alguns anúncios não mostram nenhuma impressão do DFA ou view-throughs, mas mostram cliques e click-throughs? {#section-39b2eeeefd7f43d1a373df0b987bacef}

Há alguns anúncios que só registram dados de cliques, chamados de rastreadores de cliques. Esse tipo de anúncio não retorna os dados da última impressão a partir de quando o servidor Floodlight é consultado. Para verificar se um determinado anúncio é um anúncio de rastreador de cliques ou apenas de cliques, entre em contato com sua agência do DFA ou com seu representante de suporte do Google.

## Por que não há click-throughs para anúncios que mostram cliques do DFA? {#section-758c1f1fc5b54bfc9294dcdc71bbd96a}

Pode haver muitas respostas para isso.

Primeiro, verifique se o anúncio em questão tem um URL de página de aterrissagem que (a) está marcado com o código da Adobe para o mesmo conjunto de relatórios no qual você está vendo a discrepância e (b) contém o parâmetro de sequência de consulta *`clickThroughParam`*.

Em segundo lugar, verifique se possui uma integração funcional seguindo as etapas em [Confirmar uma integração do DFA bem-sucedida](../dfa-data-connector-analytics/dfa-integration.md). Se aparecer um código de rastreamento do DFA com o hit da Adobe na página de aterrissagem, esse click-through deverá aparecer no relatório de campanhas do DFA. Se não estiver visualizando o relatório, verifique se os conjuntos de relatórios correspondem entre a variável *`s.account`* da página inicial e o conjunto de relatórios que está sendo visualizado no Reports &amp; Analytics. Se eles corresponderem, verifique os códigos de rastreamento no relatório eVar de Visualização por meio que se parecem com DFA:XXX:XXX:XXX:llXXX:XXX:XXX:XXX:XXX.

Elas indicam falhas da regra VISTA do DFA para compilar os dados brutos do DFA. Esse problema pode ser solucionado abrindo um ticket de suporte através do representante de conta da Adobe.

Se nenhuma das soluções acima explicar o problema, consulte [Comparação de discrepâncias de métricas](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md) para explorar outras possibilidades.
