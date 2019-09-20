---
description: A integração Genesis para o DFA aproveita a ID de configuração do DFA Floodlight (dfa_SPOTID), que melhora a consistência do relatório entre o DFA e o sistema de coleta de dados da Adobe.
keywords: DFA
seo-description: A integração Genesis para o DFA aproveita a ID de configuração do DFA Floodlight (dfa_SPOTID), que melhora a consistência do relatório entre o DFA e o sistema de coleta de dados da Adobe.
seo-title: Atualize o código de coleta de dados de seu site
solution: Analytics
title: Atualize o código de coleta de dados de seu site
topic: Conectores de dados
uuid: a97d1b62-f883-48b1-9516-4f889e701901
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Atualize o código de coleta de dados de seu site{#update-your-web-site-s-data-collection-code}

A integração Genesis para o DFA aproveita a ID de configuração do DFA Floodlight (dfa_SPOTID), que melhora a consistência do relatório entre o DFA e o sistema de coleta de dados da Adobe.

>[!NOTE]
>
>O termo Destaque foi alterado para Floodlight em uma versão recente do Google DFA. O parâmetro JavaScript `dfa_SPOTID` foi nomeado com base na terminologia do Spotlight, mas é usado para ambas as versões.

Para habilitar a integração do DFA em seu site, atualize o código de coleta de dados do JavaScript adicionando o seguinte:

* Módulo Integrate para DFA
* Adição a seu código de coleta

## Módulo Integrate para DFA {#section-fa00e42a732a4e27a4ab3dfcfeae1a5b}

The DFA integration leverages the Adobe Experience Cloud Integrate Module, which adds functionality to your core JavaScript data collection code ( `s_code.js`). O Módulo de integração é parte do arquivo .zip quando você baixa o código AppMeasurement para Javascript do Gerenciador [de](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)código. Entre em contato com seu consultor da Adobe somente se precisar de ajuda adicional para encontrá-lo.

Insert the Integrate Module code in the `Modules` section of your website's `s_code.js` file.

## Adição a seu código de coleta {#section-8f98c727f1ba414fb8b4f02d696b8791}

Com base em suas seleções ao ativar a integração do DFA no Assistente de integração, os Conectores de dados geram uma adição personalizada e a enviam por email para seu código de coleta de dados do JavaScript. Insira esse código na seção principal do arquivo `s_code.js` (não na função `doPlugins` nem em qualquer outra função).

O código de amostra exibido abaixo serve unicamente para fins ilustrativos; use o código enviado por email para você após concluir o Assistente de integração dos Conectores de dados.

O código de coleta consiste nos seguintes componentes:

* Configurações do DFA Integrate
* Plug-ins necessários para a integração

**Configurações do DFA Integrate**

```
/************************** DFA VARIABLES **************************/ 
var dfaConfig = { 
   CSID:              "1234567", 
   SPOTID:            "29876543", 
   tEvar:             "eVar17", 
   errorEvar:         "eVar59", 
   timeoutEvent:      "event76", 
   requestURL:         "http://fls.doubleclick.net/ 
json?spot=[SPOTID]&src=[CSID]&var=[VAR]&host=integrate.112.2o7.net%2 
Fdfa_echo%3Fvar%3D[VAR]%26AQE%3D1%26A2S%3D1&ord=[RAND]", 
 
   maxDelay:          "1500", 
   visitCookie:       "s_dfa", 
   clickThroughParam: "CID", 
   searchCenterParam: "s_kwcid", 
   newRsidsProp:      undefined 
}; 
/************************ END DFA Variables ************************/ 
```

O bloco de configurações do DFA Integrate define variáveis exigidas pela integração do DFA. Os valores para cada uma dessas variáveis vêm das seguintes fontes:

**CSID**: ID do cliente. Gerada pelo DFA depois que você conclui o Assistente de integração. Os Conectores de dados preenchem essa variável antecipadamente com sua CSID do DFA e também enviam esse valor no email de configuração depois que você conclui o Assistente de integração. Essa variável não é necessária se a Veiculação de anúncio avançada está habilitada em sua conta.

**SPOTID**: configuração do Floodlight (anteriormente chamada de ID do Spotlight). Os Conectores de dados preenchem essa variável antecipadamente com sua ID de configuração do DFA Floodlight, com base nas informações de conta do DFA que você especificou no Assistente de integração.

**tEvar**: variável de transferência. Os Conectores de dados preenchem essa variável antecipadamente com o nome da variável do Analytics que você especificou para a variável de view-through no Assistente de integração. Não altere esse valor sem uma coordenação cuidadosa com a equipe de engenharia da Adobe ou com os serviços de engenharia.

**errorEvar**: variável de erro. Os Conectores de dados preenchem essa variável antecipadamente com o nome da variável do Analytics que você especificou para a variável de falha de consulta do DFA no Assistente de integração.

**timeoutEvent**: evento de tempo limite. Os Conectores de dados preenchem essa variável antecipadamente com o nome da variável do Analytics que você especificou para a variável de evento de tempo limite no Assistente de integração.

**requestURL**: o host remoto do DFA no qual consultar informações de anúncios. Não altere esse valor a menos que seja instruído a isso pela Adobe.

**maxDelay**: especifica quanto tempo o código de coleta de dados do JavaScript aguarda por uma resposta do servidor do DFA Floodlight, em milissegundos. A Adobe recomenda fazer testes com esse valor para descobrir o valor ideal com base no tráfego do site. Por exemplo, o aumento desse valor geralmente coleta mais dados do DFA, mas aumenta o risco de perder os dados básicos do visitante caso o visitante deixe o site durante o período de atraso. A redução desse valor diminui o risco de perder dados de hit, mas pode diminuir a quantidade de dados do DFA enviados com os dados de hit da Adobe.

**visitCookie**: o nome do cookie usado para restringir as chamadas do DFA a uma vez por visita.

**clickThroughParam**: uma sequência de consulta, normalmente incluída em todos os anúncios, que notifica o módulo Integrate de que um clique acabou de ocorrer. A presença desse parâmetro na sequência de consulta causa a ocorrência da solicitação para os servidores do DFA Floodlight independentemente de o visitante já ter sido consultado nos últimos 30 minutos.

**newRsidsProp**: (Opcional) mapeado para uma variável de propriedade de tráfego não utilizada. A integração do DFA coleta e armazena esse valor no cookie de visita para identificar os conjuntos de relatórios que coletaram dados de um visitante específico. Essa propriedade só é necessária com implementações personalizadas com serviços de engenharia da Adobe.

**Plug-ins necessários para a integração**

A adição do código de coleta incorpora plug-ins adicionais que melhoram a operação da integração do DFA:

* Limita as consultas do DFA a uma vez por visita.
* Proporciona flexibilidade ao nome do cookie. Apesar de a maioria das organizações usar s_dfa, você pode usar qualquer nome de cookie válido para a integração do DFA.
* Elimina redirecionamentos desnecessários. Como os dados de view-through são coletados em tempo real, é possível que os servidores de coleta da Adobe e o DFA façam intercâmbio de dados em cada exibição de página. O plug-in bloqueia esses intercâmbios de dados quando as informações não são necessárias.

>[!CAUTION]
>
>Um dos mecanismos que o plug-in usa para eliminar consultas desnecessárias do DFA é um cookie de visita baseado em domínio. Um conjunto de relatórios de integração que abrange vários domínios aumenta os dados de click-through e view-through quando os visitantes cruzam domínios após um view-through ou click-through influenciado pelo DFA.

