---
description: A Adobe usa um cookie para rastrear navegadores/dispositivos únicos.
keywords: Analytics Implementation
subtopic: Visitors
title: Identificar visitantes únicos
topic: Developer and implementation
uuid: ed4dee75-ecfb-4715-8122-461983c7dd8f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Identificar visitantes únicos

A Adobe usa um cookie para rastrear navegadores/dispositivos únicos.

## Ordem da ID de visitante do Analytics {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

O Adobe Analytics fornece vários mecanismos para identificar visitantes. A tabela a seguir lista as diferentes maneiras pelas quais um visitante pode ser identificado no Analytics (em ordem de preferência):

| Pedido usado | Parâmetro do Query (método de coleta) | Apresentar quando |
|---|---|---|
| 1 | vid (s.visitorID) | s.visitorID está definido |
| 2 | aid (cookie s_vi) | O visitante tinha um cookie s_vi antes da implantação do serviço de ID de visitante ou o período de carência da ID de visitante está configurado. |
| 3 | mid (cookie AMCV_ definido pelo serviço de ID de visitante da Experience Cloud) | O navegador do visitante aceita cookies (originais) |
| 4 | fid (cookie de fallback) | O navegador do visitante aceita cookies (originais) |
| 5 | Endereço IP, Agente do usuário, Endereço IP de gateway | O navegador do visitante não aceita cookies. |

Em muitos cenários, você pode ver 2 ou 3 IDs diferentes em uma chamada, mas o Analytics usará a primeira ID presente na tabela anterior como a ID oficial do visitante. Por exemplo, se você estiver enviando uma ID de visitante personalizada (incluída no parâmetro de consulta &quot;vid&quot;), essa ID será usada antes de outras IDs que possam estar presentes nessa mesma ocorrência.

>[!NOTE] Cada ID de visitante do Analytics está associada a um perfil de visitante nos servidores da Adobe. Os perfis do visitante são excluídos depois de pelo menos 13 meses de inatividade, independentemente de qualquer expiração de cookie da ID do visitante.

## ID de visitante personalizada

Você pode implementar um método personalizado para identificar os visitantes, configurando a variável s.visitorID.

A ID de visitante personalizada pode ser usada em sites que possuem uma maneira única de identificar visitantes. Um exemplo disso é uma ID gerada quando um usuário faz logon no site usando um nome de usuário e senha.

Se você tiver a capacidade de derivar e gerenciar o [!UICONTROL visitor IDs] dos usuários, poderá usar os seguintes métodos para definir a ID:

| Método | Descrição |
|---|---|
| variável [s.visitorID](../implement/vars/config-vars/visitorid.md) | Se o JavaScript for usado no navegador, ou se você estiver usando outra biblioteca do AppMeasurement, poderá definir a ID do visitante em uma variável de coleção de dados. |
| Parâmetro de string de Query na solicitação de imagem | Isso permite que você passe o arquivo para a Adobe [!UICONTROL visitor ID] pelo [!UICONTROL vid query string] parâmetro em uma solicitação de imagem codificada. |
| API de inserção de dados | Em dispositivos que usam protocolos sem fio que não aceitam o JavaScript, é possível enviar uma publicação XML com o elemento XML `<visitorid/>` para os seus servidores; basta usar os servidores de coleta da Adobe. |
| Regravação de URL e VISTA | Algumas arquiteturas de implantação oferecem suporte para o uso da regravação de URL para manter o estado da sessão quando um cookie não pode ser definido. Em tais casos, os serviços de engenharia da Adobe podem implementar uma regra [!DNL VISTA], que procura o valor da sessão no URL da página e, em seguida, o formato e local nos valores [!UICONTROL visid]. |
>[!CAUTION]
>**As IDs de visitante personalizadas devem ser suficientemente granulares/exclusivas **: uma implementação inválida de IDs de visitante personalizadas pode levar a dados incorretos e a um desempenho de relatório insatisfatório. Se a ID de visitante personalizada não for suficientemente exclusiva ou granular, ou se for definida incorretamente para um valor padrão comum, como a string &quot;NULL&quot; ou &quot;0&quot;, as ocorrências de muitos visitantes diferentes serão vistas pelo Adobe Analytics como um único visitante. Essa situação resulta em dados incorretos, onde as contagens de visitantes são muito baixas e os segmentos não funcionam corretamente para o visitante. Uma ID de visitante personalizada insuficientemente granular também impede que os dados sejam distribuídos corretamente entre nós no cluster de relatórios do Analytics. Nessa situação, um nó fica sobrecarregado e não pode processar as solicitações de relatório em tempo hábil. Eventualmente, ocorrerá falha em todos os relatórios do conjunto de relatórios.<br>As IDs de visitante personalizadas mal implementadas podem não afetar imediatamente o desempenho do relatório, pois o Analytics pode lidar com dados desequilibrados por vários meses; no entanto, com o tempo, um valor de ID de visitante personalizada mal implementada pode se tornar problemático a ponto de exigir que o Analytics desative o processamento dos conjuntos de relatórios afetados.</br><br>Os implementadores devem seguir a diretriz de que um único valor de ID de visitante personalizada nunca deve ser creditado por mais de 1% do tráfego do conjunto de relatórios. Embora a diretriz de 1% seja suficiente para a maioria dos conjuntos de relatórios, o limite real que pode causar impacto no desempenho dos relatórios pode ser inferior a 1% para conjuntos de relatórios muito grandes.</br>

## ID de visitante do Analytics

Quando um usuário visita seu site, um cookie persistente é definido pelo servidor da Web da Adobe, incluindo-o na resposta HTTP ao navegador. Esse cookie é definido no domínio especificado da coleta de dados.

Quando uma solicitação é enviada para o servidor de coleção de dados da Adobe, o cabeçalho é verificado para procurar um cookie da ID do visitante (`s_vi`.) Se este cookie estiver na solicitação, ele é usado para identificar o visitante. Se o cookie não está na solicitação, o servidor gera uma ID de visitante exclusiva, a configura como um cookie no cabeçalho de resposta HTTP e a envia com a solicitação. O cookie é armazenado no navegador e é enviado de volta ao servidor de coleta de dados durante visitas subsequentes ao site, o que permite que o visitante seja identificado durante as visitas.

### Cookies de terceiros e registros CNAME {#section_61BA46E131004BB2B75929C1E1C93139}

Alguns navegadores, como o Apple Safari, não armazenam cookies configurados no cabeçalho HTTP provenientes de domínios que não correspondem ao domínio do site (como um cookie utilizado em um contexto de terceiro, ou um cookie de terceiro). Por exemplo, se você está em `mysite.com` e o servidor de coleta de dados for `mysite.omtrdc.net`, o cookie retornado no cabeçalho HTTP de `mysite.omtrdc.net` pode ser rejeitado pelo navegador.

Para evitar isso, vários clientes implementaram registros de CNAME para seus servidores de coleção de dados como parte de uma [implementação de cookie primária](https://docs.adobe.com/content/help/pt-BR/core-services/interface/ec-cookies/cookies-first-party.translate.html). Se um registro CNAME é configurado para mapear um nome de host no domínio do cliente para o servidor de coleção de dados (por exemplo, mapear `metrics.mysite.com` para `mysite.omtrdc.net`), o cookie da ID de visitante é armazenado, pois o domínio de coleção de dados agora corresponde ao domínio do site. Isso aumenta a probabilidade do cookie da ID de visitante ser armazenado, mas apresenta uma sobrecarga, pois é necessário configurar registros de CNAME e manter certificados SSL para servidores de coleção de dados.

### Cookies em dispositivos móveis {#section_7D05AE259E024F73A95C48BD1E419851}

Quando os dispositivos móveis são rastreados com cookies, há algumas configurações que você pode usar para modificar como a medição ocorre. O tempo de vida padrão do cookie é de 5 anos, mas você pode usar a variável de parâmetro de consulta de CL (`s.cookieLifetime`) para alterar esse padrão. Para definir o local do cookie para implementações cname, use a string de consulta CDP `s.cookieDomainPeriods`. O padrão é 2 se nenhum valor for especificado. e o local padrão é domain.com. Para implementações que não usam CNAME, o local do cookie da ID do visitante fica no domínio 207.net.

## Serviço de identidade

The Identity Service replaces the legacy Analytics visitor ID mechanism, and is required by [!UICONTROL Heartbeat] video measurement, Analytics for Target, and future Experience Cloud core services and integrations.

Consulte [Serviço de identidade](https://marketing.adobe.com/resources/help/pt_BR/mcvid/) para obter a documentação do produto sobre este serviço.

## Identificar dispositivos móveis

A maioria dos dispositivos móveis aceita cookies de navegador. No entanto, nos casos em que os dispositivos não aceitam cookies, outro método é usado para identificar exclusivamente os dispositivos sem fio.

A Adobe identificou diversos cabeçalhos HTTP de assinantes de ID que identificam exclusivamente a maioria dos dispositivos móveis. Esses cabeçalhos geralmente incluem o número de telefone do dispositivo (ou uma versão com hash do número) ou outros identificadores. A maioria dos dispositivos atuais tem um ou mais cabeçalhos que identificam exclusivamente o dispositivo, e todos os servidores de coleta de dados da Adobe usam esses cabeçalhos no lugar de uma ID de Visitante.

In a typical image request, a &#39;1&#39; in the path ( `/b/ss/rsid/1`) causes Adobe servers to return a gif image and to attempt to set a persistent [!UICONTROL visitor ID] cookie ( `AMCV_` or `s_vi`). Entretanto, se o dispositivo for reconhecido como um dispositivo móvel com base nos cabeçalhos HTTP, um &quot;5&quot; será transmitido no lugar do &quot;1&quot;, o que indica que uma imagem no formato wbmp deve ser retornada e que nossa lista de cabeçalhos sem fio reconhecidos (não um cookie) deve ser usada para identificar o dispositivo.

A tabela a seguir lista a ordem dos métodos de ID usados com base no valor do tipo de imagem de retorno (&#39;1&#39; ou &#39;5&#39;) no caminho:

<table id="table_07B0E55D5DAA4552A5CBC6937D47A857"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuração </th> 
   <th colname="col2" class="entry"> Ordem do método de ID </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> /1/</code> </td> 
   <td colname="col2"> <p>Padrão: </p> 
    <ul id="ul_E37E9919658A492C92187BAA18D33AB6"> 
     <li id="li_1A9E39C7CFB24C68AA07C8E85D33A858">ID de visitante personalizada </li> 
     <li id="li_0DC8D17828C848BEB614C6E47C090064">Cookie </li> 
     <li id="li_52706792FAD14F459266E3A672F92EA1">Cabeçalho da ID do assinante </li> 
     <li id="li_ECAD713D22314338BB5C92167DC0BB02"> Endereço IP-Agente do usuário-Endereço IP do Gateway </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> /5/ /5.1/ /5.5/</code> </td> 
   <td colname="col2"> <p>O dispositivo foi identificado como um dispositivo sem fio ou <code> /5/</code> foi enviado manualmente na solicitação de imagem: </p> 
    <ul id="ul_624BEDFA3E1243CF9B42081D8B8EFFFB"> 
     <li id="li_D65761D23B684DB59BC23E92C9098122">ID de visitante personalizada </li> 
     <li id="li_ADBA806B74CA43EFA8612301E06106C6">Cabeçalho da ID do assinante </li> 
     <li id="li_79DFD0DEAA1242C09A03E8134A40F799">Cookie </li> 
     <li id="li_A462B9120FC6443480D62F37D456747E">Endereço IP-Agente do usuário-Endereço IP do Gateway </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Você também pode passar um &#39;1&#39; ou um &#39;5&#39; em solicitações de imagem manuais, mas esteja ciente de que esses códigos são mutuamente exclusivos, portanto, transmitir sempre o &#39;5&#39; não aproveita um cookie quando ele é suportado. Você pode incorporar seu próprio mecanismo para determinar se um dispositivo suporta cookies e, em caso positivo, transmitem um &quot;1&quot; para a imagem, em vez de um &quot;5&quot;. O aprimoramento da precisão nessa situação é limitado ao número de dispositivos móveis que suportam cookies.

### Cabeçalhos da ID de assinante {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

O método de ID de assinante geralmente é mais confiável do que um cookie para identificação de usuário devido à exclusão de cookies, a problemas de aceitação de cookies e a problemas de gerenciamento de cookies do gateway.

Você pode melhorar a probabilidade de identificar um visitante ao ser incluído na lista branca da operadora que seus visitantes móveis usam. Para obter acesso à ID de visitante da operadora, entre em contato com a operadora para adicionar seu domínio à lista branca. Se você estiver na lista branca de uma operadora, também terá acesso aos cabeçalhos da ID do assinante que, de outra forma, não poderá acessar.

A lista de cabeçalhos a seguir é usada para identificar dispositivos sem fio. O algoritmo para processar os cabeçalhos é para

1. extraia a chave do cabeçalho HTTP (o nome do cabeçalho, como &quot;X-Up-Calling-Line-ID&quot;)
1. cortar todos os caracteres não alfabéticos (A-Z e a-z)
1. converter a chave do cabeçalho em minúsculas
1. compare o final da chave com os da tabela a seguir para encontrar uma correspondência:

| Cabeçalho | Tipo | Exemplo |
|---|---|---|
| callinglineid | ID | X-Up-Calling-Line-ID: 8613802423312 |
| subno | ID | x-up-subno: swm_10448371100_vmag.mycingular.net |
| clientid | ID | ClientID: eGtUpsqEO19zVHmbOkgaPVI-@sprintpcs.com |
| uid | ID | x-jphone-uid: a2V4Uh21XQH9ECNN |
| clid | ID | X-Hts_clid: 595961714786 |
| deviceid | ID | rim-device-id: 2005/22 |
| encamindedfor | ID ou endereço IP | X-Forwarded-For: 127.0.0.1 |
| msisdn | ID ou endereço IP | X-Wap-msisdn: 8032618185 |
| clientip | Endereço IP | Client-ip: 10.9.41.2 |
| wapipaddr | Endereço IP | X-WAPIPADDR: 10.48.213.162 |
| huaweinasip | Endereço IP | x-huawei-NASIP: 211 139 172,70 |
| userip | Endereço IP | UserIP: 70 214 81 241 |
| ipaddress | Endereço IP | X-Nokia-ipaddress: 212.97.227.125 |
| subscriberinfo | Endereço IP | X-SUBSCRIBER-INFO: IP=10.103.132.128 |

Por exemplo, &quot;callinglineid&quot; corresponderia a &quot;X-Up-Calling-Line-ID&quot; e &quot;nokia-callinglineid&quot;. O tipo de cabeçalho informa o que esperar no cabeçalho. A ordem da prioridade do cabeçalho é listada aqui (se houver um cabeçalho &quot;callinglineid&quot;, ele será usado em vez de &quot;subno&quot;).

You can use [Dynamic Variables](../implement/vars/page-vars/dynamic-variables.md) to extract specific values from a header.

## Métodos de ID de Fallback

Se os demais métodos de ID de visitante falharem, a Adobe definirá um cookie de fallback ou uma combinação de um endereço de IP e agente do usuário para identificar o visitante.

### Método de identificação do visitante de fallback {#section_2BA15E4FA6034C3EBF43859406343EB6}

O AppMeasurement para JavaScript 1.x e JavaScript H.25.3 (lançado em janeiro de 2013) contém um novo método de identificação de visitante de fallback para os visitantes cujo navegador bloqueia o cookie definido pelos servidores de coleta de dados da Adobe (chamado de `s_vi`). Anteriormente, se não fosse possível definir um cookie, os visitantes eram identificados com o uso de uma combinação do endereço IP e a sequência do agente de usuário durante a coleta de dados.

Com esta atualização, se o cookie padrão `s_vi` estiver indisponível, um cookie de fallback será criado com uma ID exclusiva gerado aleatoriamente. Este cookie, chamado de `s_fid`, é definido com uma expiração de 2 anos e usado como método de identificação de fallback que está avançando. Esta alteração deve resultar em maior precisão nas contagens de visitas e visitantes, nas situações em que o cookie primário (`AMCV_` ou `s_vi`) não pode ser definido.

O total de visitas inclui todos os visitantes identificados pelo cookie `s_vi` ou por meio de um método de fallback.

### Endereço IP, Agente do usuário, Endereço IP de gateway {#section_104819D74C594ECE879144FCC5DEF4BF}

. Se não for possível definir `AMCV_` ou `s_vi` e os cookies `s_fid`, os visitantes serão identificados por meio de uma combinação de endereço IP e Agente do usuário.
