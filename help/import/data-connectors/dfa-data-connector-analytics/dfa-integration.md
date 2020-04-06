---
description: 'A configuração da integração do DFA envolve as seguintes tarefas '
keywords: DFA
title: Integração do DFA
topic: Data connectors
uuid: 972a9d62-24fd-4463-a34c-5ec0b926e81e
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Integração do DFA {#dfa-integration}

A configuração da integração do DFA envolve as seguintes tarefas:

## Configurar a integração do DFA {#configure-the-dfa-integration}

Siga as etapas da integração dos Data Connectors do DFA.

As páginas de configuração fornecem uma visão geral da integração, juntamente com links úteis para obter mais informações. Há tarifas da Adobe e do DoubleClick associadas a essa integração. Entre em contato com os representantes de vendas apropriados para ambas as organizações e certifique-se de entender a estrutura de tarifas.

1. Faça logon no [!DNL Adobe Analytics].
1. Clique em **[!UICONTROL Admin]** > **[!UICONTROL Data Connectors]**.

   ![](assets/data_connectors.png)

1. Localize **[!UICONTROL DoubleClick DFA]** e clique em **[!UICONTROL Add New]**.

   ![Resultado da etapa](assets/wizard-01.png)

   Em cada página do Assistente de integração, forneça as informações necessárias e clique em **[!UICONTROL Next]**. A tabela a seguir explica as informações necessárias para concluir a integração por meio do assistente.

<table id="table_8F6F7F304C36431DA5FD6E5D54F60FC0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Página do Assistente # </th> 
   <th colname="col2" class="entry"> Campo </th> 
   <th colname="col3" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> Nome da integração </td> 
   <td colname="col3"> O nome da integração que o Genesis exibe na lista Integração ativa do conjunto de relatórios. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> Endereço de email de integração </td> 
   <td colname="col3"> O endereço de email que recebe todas as notificações relacionadas a essa integração. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Nome do usuário </td> 
   <td colname="col3"> O nome de usuário da API do DFA a ser usado com essa integração. Para habilitar um usuário para o logon da API, verifique o atributo da API na interface do DFA. Depois de ativar o logon da API, um campo de senha é exibido para fornecer uma senha para o usuário. Essa senha é inserida junto com o nome de usuário no assistente para autenticação. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Senha </td> 
   <td colname="col3"> A senha da API do DFA. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> ID do anunciante </td> 
   <td colname="col3"> <p>A ID do anunciante do DFA ou a ID de configuração principal do Floodlight. Os Data Connectors usam essa ID para identificar o anunciante do DFA a ser monitorado (versão 1.5 da integração). Essa ID do anunciante não é usada na versão 2.0 da integração; a ID de configuração principal do Floodlight será bloqueada e usada. Consulte as instruções no ecrã </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 3 </td> 
   <td colname="col2"> Variável de anúncio do DFA </td> 
   <td colname="col3"> A eVar do Analytics que recebe os dados de atributos, impressões e cliques da campanha do DFA. Normalmente, essa é a eVar do código de rastreamento ( <span class="varname"> s.campaign </span>), mas você pode escolher qualquer eVar disponível. Os Data Connectors também adicionam as seguintes classificações relacionadas ao DFA à eVar selecionada: <p><b>Campanhas</b>: Uma coleção de anúncios veiculados em vários sites que possuem mensagens comuns. </p> <p><b>Nome</b>do site: O site onde o anúncio foi veiculado. </p> <p><b>Nome</b>do anúncio: O nome do anúncio, conforme definido em sua conta do DFA. </p> <p><b>Nome</b>de posicionamento do site: O site e a página onde o anúncio foi veiculado. </p> <p><b>Ferramenta</b>Delivery: DoubleClick for Advertisers. </p> <p><b>Canal</b>: Anúncio em banner. </p> <p><b>Estrutura</b>de Custo: CPM, CPC ou Fixo, com base na estrutura de custo do anúncio. </p> <p><b>Nome</b>criativo: O nome do anúncio associado a uma ID de anúncio/disposição/criação. </p> <p><b>DFA &gt; Desduplicação do SearchCenter</b>: especifica que o DFA deve colocar valores em variáveis do SearchCenter quando ocorrem click-throughs ou view-throughs do DFA </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> Impressões </td> 
   <td colname="col3"> O Evento personalizado que recebe os dados da métrica de impressões do DFA. As impressões indicam o número de vezes que o anúncio foi veiculado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> Cliques </td> 
   <td colname="col3"> Selecione o Evento personalizado que recebe os dados de métrica de cliques do DFA. A métrica de Cliques indica o número de vezes que os visitantes clicaram no anúncio conforme medido pelo redirecionamento do DFA. A métrica de cliques correlaciona-se com a métrica de click-throughs do Analytics. <p>Observação: as métricas de Cliques do DFA e de Click-throughs do Analytics podem não ser exatamente iguais devido a diferenças no modo de coleta dos dados.  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Variável de Visualização-through </td> 
   <td colname="col3"> <p>A eVar do Analytics que recebe dados de Visualização do DFA. A variável de Visualização ajuda você a ver como as visualizações afetam as taxas de conversão do site. </p> <p>Os Data Connectors adicionam as mesmas classificações relacionadas ao DFA a essa eVar, assim como fazem com a variável de anúncio do DFA (veja acima). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Tempo desde a última Visualização (variável de período de tempo de visualização por período) </td> 
   <td colname="col3"> A eVar do Analytics que recebe os dados de Tempo desde a última Visualização do DFA. O Tempo desde a última Visualização indica o tempo decorrido desde a última visualização do anúncio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Visualização-throughs </td> 
   <td colname="col3"> O Evento personalizado que recebe dados de métrica de Visualização-throughs do DFA. Use o evento de View-throughs com a variável de view-through para ver quais campanhas não influenciaram um click-through direto, mas podem ter desempenhado um papel em direcionar tráfego para o site em algum momento subsequente. <p>Os Data Connectors renomeiam o evento personalizado selecionado para “View Throughs”. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> Falha no Query do DFA </td> 
   <td colname="col3"> (Opcional) A eVar do Analytics que recebe quaisquer códigos de mensagem de falha de query do DFA reportados. Os possíveis códigos de mensagem do DFA incluem: 
    <ul id="ul_85FC7FB19F7F4ADF83ABCA6DDB44CE19"> 
     <li id="li_0A3181DED5A149588A0D3F1584E2FE8B"><b>nc</b>: Nenhum cookie DoubleClick. </li> 
     <li id="li_D397AA73AD5E4086A18B87F271E4EC14"><b>oo</b>: O usuário opt out. </li> 
     <li id="li_5AC1D0C8049340B4AD857D88E275CBD6"><b>nh</b>: Sem histórico de campanhas. </li> 
     <li id="li_73A8C5E905C54E2BB531A1FCDBC6AA1A"><b>qe</b>: Erro de Query (tempo limite, servidor inativo etc.) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> Evento de tempo limite </td> 
   <td colname="col3"> <p>O evento de contador do Analytics que aumenta cada vez que o temporizador <span class="varname"> s.maxDelay </span> expira e nenhuma resposta é recebida dos servidores do DFA. Use esse evento para configurar a variável do <span class="varname"> s.maxDelay </span> Ajuste do s.maxDelay</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Atualizações de site para a integração do DFA {#web-site-updates-for-the-dfa-integration}

Depois que o Genesis configurar seu conjunto de relatórios do Analytics para a integração do DFA, faça o seguinte para configurar seu site e o ambiente do DFA para respaldar a integração:

### Verificar o espaço do cookie no domínio {#verify-cookie-space-on-the-domain}

A integração dos Data Connectors para o DFA exige a definição de um cookie no domínio da página.

Embora seja raro, alguns domínios atingiram a capacidade máxima de cookies para alguns navegadores da Web. Para não afetar a experiência de navegação de um visitante em seu site, consulte suas operações de rede, a equipe de desenvolvimento ou o grupo de engenharia a fim de verificar se a adição de outro cookie ao domínio das páginas usadas para a integração do DFA afetará a experiência do usuário. Também será necessário selecionar um nome para o cookie.

### Atualize seu parâmetro de sequência de consulta do DFA {#update-your-dfa-query-string-parameter}

Se você já tiver rastreado campanhas de anúncio com o Adobe Analytics antes da integração do DFA, é possível que todas as campanhas (email, pesquisa ou banner) usem o mesmo parâmetro de sequência de query para identificar a ID de campanha de referência na landing page.

Para entender quando solicitar dados de view-through e de click-through dos dados do DFA para suas campanhas de anúncios do DFA, os Data Connectors precisam identificar quando um visitante clicou em um anúncio de banner de campanha do DFA. Para tornar isso possível, adicione um parâmetro de string de consulta diferenciado ao URL da página de aterrissagem da campanha do anúncio do DFA para que os Data Connectors possam distinguir entre as páginas de campanha de anúncios do DFA e outras páginas de campanhas de anúncios que possam existir em seu site. O plug-in `dfa_overrideParam` do JavaScript usado para o DFA.

>[!CAUTION]
>
>Apesar de a variável de campanha poder ser usada para outras campanhas, não a use para campanhas do DFA. Se você definir a variável de Campanha como uma landing page de campanha do DFA, a Adobe não poderá vincular impressões e cliques a click-throughs de campanha do DFA. Uma vez por visita, os servidores de coleta da Adobe verificam nos servidores do DFA se há um click-through ou visualização anterior. Por causa disso, inclua o plug-in do DFA somente em páginas de aterrissagem comuns a fim de evitar redirecionamentos desnecessários que possam retardar os tempos de carregamento de página, especialmente para usuários com conexões de Internet mais lentas.

## Atualize o código de coleta de dados de seu site {#update-your-web-site-s-data-collection-code}

A integração Genesis para o DFA aproveita a ID de configuração do DFA Floodlight (dfa_SPOTID), que melhora a consistência do relatório entre o DFA e o sistema de coleta de dados da Adobe.

>[!NOTE] O termo Spotlight foi alterado para Floodlight em uma versão recente do DFA do Google. O parâmetro JavaScript `dfa_SPOTID` foi nomeado com base na terminologia do Spotlight, mas é usado para ambas as versões.

Para habilitar a integração do DFA em seu site, atualize seu código de coleta de dados do JavaScript adicionando o seguinte:

* Módulo Integrate para DFA
* Adição ao código de coleta

### Módulo Integrate para DFA {#section-fa00e42a732a4e27a4ab3dfcfeae1a5b}

A integração do DFA aproveita o módulo Integrate da Adobe Experience Cloud, que adiciona funcionalidade a seu código central de coleta de dados do JavaScript ( `s_code.js`). O módulo Integrate é parte do arquivo .zip de quando você baixa o código do AppMeasurement para Javascript por meio do Gerenciador de código. Entre em contato com seu consultor da Adobe somente se precisar de ajuda adicional para encontrar o módulo.

Insira o código do módulo Integrate na seção `Modules` do arquivo `s_code.js` de seu site.

### Adição a seu código de coleta {#section-8f98c727f1ba414fb8b4f02d696b8791}

Com base em suas seleções ao ativar a integração do DFA no Assistente de integração, os Data Connectors geram uma adição personalizada e a enviam por email para seu código de coleta de dados do JavaScript. Insira esse código na seção principal do arquivo `s_code.js` (não na função `doPlugins` nem em qualquer outra função).

O código de amostra exibido abaixo serve unicamente para fins ilustrativos; use o código enviado por email para você após concluir o Assistente de integração dos Data Connectors.

O código de coleta consiste nos seguintes componentes:

* Configurações do DFA Integrate
* Plug-ins necessários para integração

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

O Bloco de configurações do DFA Integrate define variáveis exigidas pela integração do DFA. Os valores para cada uma dessas variáveis vêm das seguintes fontes:

**CSID**: ID do cliente. Gerado pelo DFA após concluir o Assistente de integração. Os Data Connectors preenchem essa variável antecipadamente com sua CSID do DFA e também enviam esse valor no email de configuração depois que você conclui o Assistente de integração. Essa variável não é necessária se o Serviço de publicidade avançada estiver ativado em sua conta.

**SPOTID**: Configuração do Floodlight (anteriormente chamada de ID do Spotlight). Os Data Connectors preenchem essa variável antecipadamente com sua ID de configuração do DFA Floodlight, com base nas informações de conta do DFA que você especificou no Assistente de integração.

**tEvar**: Variável de transferência. Os Data Connectors preenchem essa variável antecipadamente com o nome da variável do Analytics que você especificou para a variável de view-through no Assistente de integração. Não altere esse valor sem uma coordenação cuidadosa com os serviços de engenharia ou engenharia da Adobe.

**errorEvar**: Variável de erro. Os Data Connectors preenchem essa variável antecipadamente com o nome da variável do Analytics que você especificou para a variável de falha de consulta do DFA no Assistente de integração.

**timeoutEvent**: Evento de tempo limite. Os Data Connectors preenchem essa variável antecipadamente com o nome da variável do Analytics que você especificou para a variável de evento de tempo limite no Assistente de integração.

**requestURL**: O host remoto do DFA para query para obter informações sobre anúncios. Não altere esse valor a menos que a Adobe tenha instruções para isso.

**maxDelay**: Especifica o tempo que o código de coleta de dados JavaScript aguarda por uma resposta do servidor do DFA Floodlight, em milissegundos. A Adobe recomenda fazer testes com esse valor para descobrir o valor ideal com base no tráfego do site. Por exemplo, aumentar esse valor geralmente coleta mais dados do DFA, mas aumenta o risco de perder os dados básicos do visitante se o visitante deixar o site durante o período de atraso. A redução desse valor diminui o risco de perda de dados de ocorrência, mas pode reduzir a quantidade de dados do DFA enviados com os dados de ocorrência da Adobe.

**visitCookie**: O nome do cookie usado para restringir chamadas do DFA a uma vez por visita.

**clickThroughParam**: Uma string de query, normalmente incluída em todos os anúncios, que informa ao módulo Integrate que um clique acabou de ocorrer. A presença desse parâmetro na string do query faz com que a solicitação ocorra nos servidores do DFA Floodlight, independentemente do visitante já ter sido consultado nos últimos 30 minutos.

**newRsidsProp**: (Opcional) Mapeado para uma variável de propriedade Tráfego não utilizada. A integração do DFA coleta e armazena esse valor no cookie de visita para identificar os conjuntos de relatórios que coletaram dados de um determinado visitante. Essa propriedade só é necessária com implementações personalizadas com os serviços de engenharia da Adobe.

**Plug-ins necessários para a integração**

A adição do código de coleta incorpora plug-ins adicionais que melhoram a operação da integração do DFA:

* Limita query do DFA a uma vez por visita
* Oferece flexibilidade de nome de cookie. Embora a maioria das organizações use s_dfa, você pode usar qualquer nome de cookie válido para a integração do DFA.
* Elimina redirecionamentos desnecessários. Como os dados de visualização são coletados em tempo real, os servidores de coleta da Adobe e o DFA podem trocar dados em cada visualização de página. O plug-in bloqueia essas trocas de dados quando as informações não são necessárias.

>[!CAUTION]
>
>Um dos mecanismos que o plug-in usa para eliminar consultas desnecessárias do DFA é um cookie de visita baseado em domínio. Um conjunto de relatórios de integração que abrange vários domínios aumenta os dados de click-through e view-through quando os visitantes cruzam domínios após um view-through ou click-through influenciado pelo DFA.

## Confirmação de uma integração do DFA bem-sucedida {#confirming-a-successful-dfa-integration}

Depois de fazer todas as atualizações necessárias no site, você pode usar um visualizador de tráfego de rede, como o Charles*, as ferramentas de desenvolvedor do Chrome ou o Firebug*, para confirmar se o DFA está se comunicando com os servidores de coleta da Adobe.

Depois de implantar o arquivo `s_code.js` habilitado para o DFA, use o visualizador de tráfego de rede para exibir as solicitações entre o DFA e os servidores de coleta de dados da Adobe e procure o seguinte:

* Uma solicitação para o serviço `fls.doubleclick.net/json` do DFA. Esse serviço pode responder de forma diferente dependendo da versão do DFA que você está usando. Com a versão 1.5 da integração do DFA:

   * Um redirecionamento HTTP 302 para [!DNL ad.doubleclick.net]. Isso enviará uma tag Location: na resposta que contém informações sobre o visitante do anúncio.
   * Essa tag Location causa um redirecionamento para [!DNL integrate.112.2o7.net/dfa_echo]. Esse serviço traduz as informações sobre o visitante de anúncio em uma sequência codificada JSON (JavaScript Object Notati on). Esses dados são retornados com uma resposta 200 OK HTTP.

* Com a versão 2.0 da integração do DFA (Advanced Ad Serving ativado):

   * [!DNL fls.doubleclick.net] responderá diretamente com 200 OK.

Em ambos os casos, uma solicitação bem-sucedida resultará em uma solicitação para os servidores de coleta de dados da Adobe que contêm o parâmetro vX, onde X é o número da eVar de Visualização. Esse valor de parâmetro assume a forma: DFA-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX. Essa string contém dados sobre o último clique e a última impressão do visitante atual.

## Ajuste do s.maxDelay {#tuning-s-maxdelay}

Uma implementação bem-sucedida do DFA envolve a otimização do s.maxDelay para seu site específico.

Em geral, a decisão de aumentar ou diminuir o *`s.maxDelay`* envolve uma compensação entre a obtenção de mais dados de visitantes do DFA e a ameaça de coleta de dados de visitantes da Adobe. Aumentar o *`s.maxDelay`* gera maior obtenção de dados de visitantes do DFA, mas (quando excessivamente alto) pode pôr em risco a coleta de dados de visitantes da Adobe. A diminuição do s.maxDelay garante a coleta de dados de visitantes da Adobe, mas pode perder dados de visitantes do DFA.

*`s.maxDelay`* envolve mais do que apenas o tempo em comunicação de rede para contatar o DFA; também representa atrasos no navegador para disparar e avaliar o JavaScript no qual essas comunicações se baseiam. Isso ocorre porque o módulo Integrate inicia o temporizador *`s.maxDelay`* depois de ter inserido o elemento HTML no DOM que extrai os dados do servidor do DFA Floodlight. O tempo necessário para que o navegador realmente inicie a solicitação HTTP com base nesse novo elemento HTML varia com base em outras imagens ou arquivos JavaScript que estão sendo carregados simultaneamente, na velocidade do computador do visitante e em implementações específicas do navegador. Além disso, quando os dados JSON são recuperados do servidor DFA Floodlight, o JavaScript deve ser avaliado pelo navegador. Isso novamente é controlado completamente pelo navegador e pode ser atrasado se houver grandes quantidades de código JavaScript em execução simultânea ou muitas solicitações assíncronas do JavaScript.

Tendo isso em mente, o *`s.maxDelay`* precisa ser definido dependendo da complexidade da página de aterrissagem, além da quantidade de atraso de rede com o DFA. Em alguns sites, uma maneira possível de diminuir a complexidade é acionar o código de coleta da Adobe no início do carregamento da página, para que haja menos atividade no navegador no momento em que o servidor Floodlight é solicitado.

A variável Timeout é absolutamente necessária no ajuste do *`s.maxDelay`*, pois aumenta cada vez que o tempo limite do s.maxDelay é atingido. Ao decidir se aumenta ou diminui o *`s.maxDelay`*, recomendamos seguir este processo:

1. Colete vários dias de dados com *`s.maxDelay`* definido com um valor específico.
1. Execute um [!DNL Daily Unique Visitors Report] para o intervalo de tempo em questão.
1. Execute o [!DNL Timeout Event Report] para verificar o número de tempos limite atingidos. Lembre-se de que o tempo limite só é coletado uma vez por visitante.

Agora com os números em mãos, calcule

```
Timeout Percentage = [Step 3] / [Step 2] * 100
```

Observe que a porcentagem de tempo limite está considerando todos os visitantes do site. Alguns desses visitantes não teriam sido associados ao DFA de forma alguma, e por isso o tempo limite é enganoso. Para melhorar esse cálculo, outra análise pode considerar somente visitantes exclusivos a páginas com o parâmetro `clickThroughParam` definido (por exemplo, `?CID=1`). Isso mostrará mais precisão.

Se a porcentagem de tempo limite estiver muito baixa, considere diminuir o *`s.maxDelay`*. Se estiver muito alta, aumente o *`s.maxDelay`*. Ao diminuir o *`s.maxDelay`*, execute novamente o [!DNL Timeout Report] para garantir que as ocorrências de excedência do tempo limite não tenham aumentado drasticamente. Ao aumentar o *`s.maxDelay`*, você executará um [!DNL Page Views Report] para garantir que as exibições de página não estejam desaparecendo por causa de dados perdidos. Cada vez que alterar o *`s.maxDelay`*, observe os dados por vários dias para garantir que eles representem uma tendência e não apenas uma flutuação dia após dia.

A configuração otimizada para o *`s.maxDelay`* é o ponto no qual a porcentagem de excedência de tempo limite é minimizada enquanto as exibições de páginas não caem.

Espera-se que os tempos limite diminuam quando você muda para a versão 2.0 da integração, devido às eliminações de redirecionamentos 302. As descobertas iniciais com clientes beta mostraram uma redução consistente das ocorrências de tempo limite e, consequentemente, maior coleta de dados do DFA.
