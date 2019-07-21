---
description: Dicas e práticas recomendadas para novos usuários dos conjuntos de relatórios virtuais.
keywords: Conjunto de relatórios virtuais
seo-description: Dicas e práticas recomendadas para novos usuários dos conjuntos de relatórios virtuais.
seo-title: Perguntas frequentes sobre VRS
solution: Analytics
title: Perguntas frequentes sobre VRS
topic: Reports and Analytics
uuid: 91225743-765 a -4145-9 ce 5-4268 e 80 ea 7 e 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Perguntas frequentes sobre VRS

Dicas e práticas recomendadas para novos usuários dos conjuntos de relatórios virtuais.

<table id="table_4D9DE70984674B65AD7D40E3D1479CD2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta </th> 
   <th colname="col2" class="entry"> Resposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Devo consolidar minha implementação de diversos conjuntos de relatórios em um único conjunto de relatórios “global” e, em seguida, usar os conjuntos de relatórios virtuais para expor diferentes segmentos de dados para meus usuários?</b> </td> 
   <td colname="col2"> <p>Talvez. Estas são algumas das circunstâncias sob as quais você deve <b>considerar manter os conjuntos de relatórios individuais</b>: </p> 
    <ul id="ul_493454A655DE48E0AF94130014203268"> 
     <li id="li_B37C2651D2804FD1B965286C85A765D5">Se você tiver variáveis/dimensões com uma grande quantidade de valores únicos, a consolidação em um único conjunto de relatórios pode sobressair os limites de valor único mensal no conjunto global, resultando em truncamento (“Baixo tráfego” como um item de linha nos relatórios). </li> 
     <li id="li_87ABC62EC73D4355A9F768AD1949D3C6">Se você precisar de relatórios em tempo real ou “Dados atuais” para segmentos individuais (ex: marcas, unidades comerciais etc.) dos seus dados. </li> 
     <li id="li_7252787B2D4C4756836DAEA0EEC0BF8B">Se os diversos conjuntos de relatórios tiverem requisitos exclusivos de controle (isto é, se usam as variáveis e os eventos do Adobe Analytics de modo diferente), observe que a consolidação em um conjunto de relatórios global não oferece variáveis adicionais ou eventos de rastreamento. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Quais configurações dos conjuntos de relatórios virtuais são herdadas do conjunto de relatórios pai? </b> </td> 
   <td colname="col2"> <p>Um conjunto de relatórios virtuais (VRS) herda a maioria dos níveis de serviço do conjunto de relatórios pai, como configurações de eVar, Regras de processamento, Classificações etc. </p> <p>As seguintes configurações <b>NÃO</b> foram herdadas: </p> 
    <ul id="ul_43B0637F095C480B82126C96BFF627FA"> 
     <li id="li_F3DF9D6B0B1A4A46B9D8B1CF2DA09BE3">ID do conjunto de relatórios </li> 
     <li id="li_A735D7BA4DA14DCB8F40D7898A324F1F">Nome do conjunto de relatórios </li> 
     <li id="li_BF66DD426EE7464CBF7F2EB56B0C3075">Grupos de permissões (os conjuntos de relatórios virtuais podem ser atribuídos aos seus próprios grupos de permissões) </li> 
    </ul> <p>Observação: isso não inclui a maioria das entidades criadas pelo usuário, como Marcadores, Painéis, Relatórios agendados etc.; esses itens não foram herdados do pai, podendo ser criados e usados especificamente no VRS (mais detalhes na próxima pergunta). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Qual é a diferença entre trabalhar com um conjunto de relatórios virtuais e com um conjunto de relatórios base na interface do usuário do Analytics?</b> </td> 
   <td colname="col2"> <p>Depois de criado, um conjunto de relatórios virtuais é tratado como um conjunto de relatórios base na interface do usuário, geralmente compatível com a maioria dos recursos estendidos. Por exemplo: </p> 
    <ul id="ul_D20435FD9B3546DFB611FD09035BACBB"> 
     <li id="li_4A331EB50B7F43E697F67B4A657B4450">Os conjuntos de relatórios virtuais aparecem no seletor de Conjunto de relatórios e podem ser selecionados individualmente, como qualquer outro conjunto de relatórios base. </li> 
     <li id="li_6E8C1E45C68943A1BA7C260FA62C40E0">Relatórios de DL, Marcadores, Painéis, Alvos, Alertas, Segmentos, Métricas calculadas etc. podem ser criados com base em um conjunto de relatórios virtuais e se comportam de modo independente do pai. </li> 
     <li id="li_5701D7F60BF8452CBEC8DFA2072CE8C2">Os conjuntos de relatórios virtuais podem ser adicionados individualmente aos Grupos de permissões, como qualquer outro conjunto de relatórios. </li> 
     <li id="li_764475FD352C434D92E876E30699F280">Os segmentos ainda podem ser aplicados quando se executam relatórios no contexto de um VRS; eles são empilhados automaticamente com os segmentos do conjunto de relatórios virtuais quando os dados de relatório são recuperados. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Como os conjuntos de relatórios virtuais são tratados no Admin Console e na API de administração? É possível salvar recursos neles, como conjuntos de relatórios base? </b> </td> 
   <td colname="col2"> <p>Não, os conjuntos de relatórios virtuais <b>não são compatíveis com a maioria dos recursos de Administração</b>. Como mencionado acima, um VRS herda a maioria dos níveis de serviço e recursos do pai (por exemplo, configurações de eVar, Regras de processamento, Classificações etc.); portanto, para fazer alterações nessas configurações herdadas em um VRS, é necessário alterar o conjunto de relatórios pai. </p> <p>Como resultado, os conjuntos de relatórios virtuais são mostrados na interface do usuário <b>somente aqui</b>: </p> 
    <ul id="ul_64CF126ACF39453A95BD9FC9D2CFA59B"> 
     <li id="li_08EBF87ADF13400C9DD3FFC2695F5CF9">O Gerente do conjunto de relatórios virtuais, no qual você cria e edita VRSs. <p>( <span class="ignoretag"> <span class="uicontrol"> Analytics</span> &gt; <span class="uicontrol">Componentes</span> &gt; <span class="uicontrol">Conjuntos de relatórios virtuais </span> </span>) </p> </li> 
     <li id="li_E2B3F61A3013402697DCF6E0D32A62DC"> A interface de Gerenciamento de usuários, na qual você edita grupos de permissões personalizados. Isso permite adicionar contas do VRS a um grupo de permissões e usá-las para criar um grupo que tem acesso somente a conjuntos de relatórios virtuais (se o Administrador quiser negar acesso ao pai e permitir que os usuários acessem somente segmentos específicos). <p>( <span class="ignoretag"> <span class="uicontrol"> Administrador</span> &gt; <span class="uicontrol">Gerenciamento de usuários </span> </span>) </p> </li> 
    </ul> <p>Observação: ao usar a API de serviços da Web e tentar salvar as configurações de Recurso de VRS, ocorre uma exceção. Os recursos podem ser definidos somente com um conjunto de relatórios base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Os conjuntos de relatórios virtuais são suportados na interface do usuário do SiteCatalyst 14?</b> </td> 
   <td colname="col2"> <p>Não; não expomos conjuntos de relatórios virtuais no SiteCatalyst 14. Eles não aparecem para seleção no Seletor de conjunto de relatórios e não podem ser selecionados. No entanto, expomos conjuntos de relatórios virtuais na interface do usuário do Admin Console do SiteCatalyst 14 ao editar um grupo. Nesse caso específico, os conjuntos de relatórios virtuais devem ser representados para que não sejam removidos acidentalmente de um grupo existente que já pode acessar um ou vários conjuntos de relatórios virtuais. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Eu marquei “Iniciar nova visita na inicialização”. Por que ainda vejo visitas muito maiores que inicializações?</b> </td> 
   <td colname="col2"> <p> Quando a opção <span class="uicontrol">iniciar nova visita na inicialização</span> está marcada, o tempo limite ainda é aplicado. Assim, se um usuário usar o aplicativo por dez minutos com um intervalo de um minuto entre cada ação, uma nova visita será iniciada na inicialização e nove visitas adicionais serão criadas quando a visita atingir o tempo limite. Para manter inicializações e visitas o mais próximo possível ao <span class="uicontrol">usar a opção Iniciar nova visita na inicialização</span>, você deve usar um tempo limite mais longo que o tempo limite da sessão definido no SDK. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Eu defini “Iniciar nova visita na inicialização” e um tempo limite mais longo que meu SDK. Por que minhas inicializações ainda são muito inferiores às visitas?</b> </td> 
   <td colname="col2"> <p> Se o tempo limite for maior que o valor definido no SDK, provavelmente o seu aplicativo está enviando ocorrências em segundo plano e estas estão sendo registradas como novas visitas. Verifique isso usando a dimensão de tipo de ocorrência no conjunto de relatórios principal para ver se há alguma ocorrência em segundo plano. </p> <p> <p>Observação: ocorrências em primeiro e segundo plano são diferenciadas somente na versão 4.13.6 e superior do SDK. Se estiver em uma versão anterior, todas as ocorrências serão mostradas em primeiro plano. Se tiver a versão correta do SDK, você deve ativar a configuração <span class="uicontrol">Impedir ocorrências em segundo plano de iniciar uma nova visita</span>. </p> </p> <p> <p>Observação: se não tiver desativado o processamento herdado para ocorrências em segundo plano no Admin Console, eles não serão mostrados no conjunto de relatórios principal, mas aparecerão no conjunto de relatórios virtual. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Que versão do SDK preciso ter para rastrear ocorrências em segundo plano?</b> </td> 
   <td colname="col2"> <p> Você deve ter a versão 4.13.6 ou superior do SDK. </p> </td> 
  </tr> 
 </tbody> 
</table>

