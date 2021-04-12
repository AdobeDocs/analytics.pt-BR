---
title: Término da vida útil das fontes de dados de processamento completo
description: Motivos para o fim da vida útil e comparações entre a API de inserção de dados em massa e as fontes de dados de processamento completo.
exl-id: 24a44b7a-64fd-4a99-975f-4887f4638812
translation-type: tm+mt
source-git-commit: 03a2b346dc6940bc7471de454f73c58f5462a0bb
workflow-type: tm+mt
source-wordcount: '1208'
ht-degree: 31%

---

# Término da vida útil das fontes de dados de processamento completo

Por vários anos, as Fontes de dados de processamento completo permitiram enviar dados a nível de ocorrência para a Adobe Analytics. Esses dados foram processados da mesma forma que os dados coletados por meio das bibliotecas JavaScript e do SDK do aplicativo móvel. Em 2020, o Adobe lançou a [API de inserção de dados em massa](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md), que executa as mesmas funções que as Fontes de dados de processamento completo, mas com recursos adicionais. Este tópico fornece detalhes sobre a funcionalidade adicional fornecida pela API de inserção de dados em massa e descreve as diferenças nos formatos de arquivo.

A partir de 25 de março de 2021, o Adobe impedirá a criação de novas conexões das Fontes de dados de processamento completo. As conexões existentes continuarão a ser compatíveis até que o serviço seja totalmente descontinuado em 31 de julho de 2021.

## Por que vamos acabar com esse recurso?

A API de inserção de dados em massa (BDIA) fornece funcionalidade adicional enquanto cobre todos os casos de uso compatíveis com o processamento completo. Acreditamos que você será mais bem servido usando a API de inserção de dados em massa.

## Principais diferenças entre as fontes de dados de processamento completo e a API de inserção de dados em massa

* A inserção de dados em massa permite o envio de vários arquivos que podem ser processados em paralelo. É possível usar Grupos de visitantes para garantir a continuidade do visitante e a atribuição do eVar.
* A inserção de dados em massa tem validação de dados, bem como recursos de tratamento de erros, removendo assim parte do trabalho administrativo de envio de dados de ocorrência.
* A inserção de dados em massa é compatível com várias opções para IDs de visitante. Você pode enviar a ID do Analytics e a ID do Marketing Cloud (consulte [Serviço de identidade](https://experienceleague.adobe.com/docs/id-service/using/home.html) para saber mais). Além disso, você pode usar sua própria ID como uma [seed para gerar um ECID](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds).
* A inserção de dados em massa é compatível com as Variáveis de lista e de dados de contexto.
* A inserção de dados em massa não é compatível com dados de Activity Map.

## Principais diferenças no formato e conteúdo do arquivo

* A inserção de dados em massa tem alguns campos obrigatórios adicionais. Consulte a [documentação](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) para obter detalhes.
* Para garantir a continuidade do visitante e a atribuição, a inserção de dados em massa requer que as linhas nos arquivos sejam classificadas em ordem cronológica. Consulte [Grupos de visitantes](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups) para saber mais sobre a ordem da atividade do Visitante em todos os arquivos.
* A inserção de dados em massa requer que os arquivos sejam compactados em .csv no formato .gzip.
* O BDIA usa &quot;carimbo de data e hora&quot; em vez de &quot;data&quot;.

Para obter mais detalhes, consulte a seguinte comparação dos valores de campo disponíveis em Inserção de dados em massa (BDIA) e Fontes de dados de processamento completo (FPDS).

## Comparação de valores de campo disponíveis em BDIA e FPDS

| Variável BDIA | Variável de coluna do processamento completo | Descrição |
| --- | --- | --- |
| aamlh | Não suportado | Dica de localização do Adobe Audience Manager. |
| browserHeight | browserHeight | Altura do navegador em pixels (por exemplo, 768) |
| browserWidth | browserWidth | Largura do navegador em pixels (por exemplo, 1024) |
| campaign | campanha | Código de rastreamento de campanha de conversão |
| canal | canal | Sequência de caracteres de canal (por exemplo, seção de esportes) |
| colorDepth | colorDepth | Profundidade de cores do monitor em bits (por exemplo, 24) |
| connectionType | connectionType | Tipo de conexão do visitante (LAN ou modem) |
| contextData.key | Não suportado | Os pares de valores-chave são especificados em, nomeando o cabeçalho &quot;contextData.product&quot; ou &quot;contextData.color&quot; |
| cookiesEnabled | cookiesEnabled | `Y` ou  `N` se o visitante suporta cookies de sessão primária |
| currencyCode | currencyCode | Código da moeda da receita (por exemplo, `USD`) |
| customerID.[customerIDType].authState | Não suportado | O estado autenticado do visitante. Os valores suportados são: 0, 1, 2, UNKNOWN, AUTENTICATED, LOGGED_OUT ou &#39;&#39; (não diferencia maiúsculas de minúsculas). Duas aspas simples consecutivas (&#39;&#39;) fazem com que o valor seja omitido da string de consulta, o que significa 0 quando a ocorrência for feita. Observe que os valores numéricos authState suportados indicam o seguinte: 0 = UNKNOWN, 1 = AUTHENTICATED, 2 = LOGGED_OUT. O customerIDType pode ser qualquer sequência alfanumérica, mas deve ser considerada diferencia maiúsculas de minúsculas. |
| customerID.[customerIDType].id | Não suportado | A ID do cliente a ser usada. O customerIDType pode ser qualquer sequência alfanumérica, mas deve ser considerada diferencia maiúsculas de minúsculas. |
| customerID.[customerIDType].isMCSeed | Não suportado | Se essa é a propagação da ID de visitante do Marketing Cloud. Os valores suportados são: 0, 1, TRUE, FALSE, &#39;&#39; (não diferencia maiúsculas de minúsculas). Usar 0, FALSE ou duas aspas simples consecutivas (&#39;&#39;) faz com que o valor seja omitido da string de consulta. O customerIDType pode ser qualquer sequência alfanumérica, mas deve ser considerada diferencia maiúsculas de minúsculas. |
| eVarN | eVarN, ou seja `<eVar2>`...`<eVar>` | Nome do eVar de conversão. É possível ter até 75 eVars ( eVar 1 - eVar75 ) Você pode especificar o nome do eVar (eVar12) ou um nome amigável (Campanha publicitária 3). |
| events | events | [Sequência de eventos](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=en#vars), formatada com a mesma sintaxe da variável s.events . Por exemplo: scAdd,event1,event7 |
| hierN | hierN, ou seja `<hier2>`...`</hier2>` | Nome da hierarquia. É possível ter até 5 hierarquias ( hier1 - hier5 ). Você pode especificar o nome de hierarquia padrão `hier2` ou um nome amigável (Yankees). |
| homePage | homePage | S ou N, é a página atual da página inicial do visitante. |
| ipaddress | Não suportado | O endereço IP do visitante. |
| javaEnabled | javaEnabled | S ou N, o visitante tem o Java habilitado. |
| javaScriptVersion | javaScriptVersion | Versão do JavaScript (por exemplo, 1.3) |
| idioma | Não suportado | O idioma suportado do navegador. Por exemplo, `en-us`. |
| linkName | linkName | Nome do link. |
| linkType | linkType | Tipo de link. Os valores para os quais existe suporte incluem: `d: Download link`, `e: Exit link`, `o: Custom link`. |
| linkURL | linkURL | HREF do link. |
| listar Por exemplo, list2. | Não suportado | Uma lista delimitada de valores passados para uma variável e, em seguida, reportados como itens de linha individuais para relatório. |
| marketingCloudVisitorID | Não suportado | Marketing Cloud ID. Consulte [Identificação do visitante](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en#id-service-api) e o Serviço de ID do visitante do Marketing Cloud. |
| Não suportado | charSet | O conjunto de caracteres suportado para seu site. Por exemplo, UTF-8, ISO-8859-1, e assim por diante. |
| Não suportado | clickAction | Identificador de objeto para o mapa de cliques do visitante (oid) |
| Não suportado | clickActionType | Tipo de identificador de objeto para o mapa de cliques do visitante (oidt) |
| Não suportado | clickContext | Identificador de página para o mapa de cliques do visitante (pid) |
| Não suportado | clickContextType | Identificador de página para o mapa de cliques do visitante (pidt) |
| Não suportado | clickSourceID | Índice da fonte para o mapa de cliques do visitante (oi) |
| Não suportado | clickTag | Nome da tag do objeto para o mapa de cliques do visitante (ot) |
| Não suportado | scXmlVer | Número da versão da solicitação de XML de relatórios de marketing (por exemplo, 1.0). |
| Não suportado | fuso horário | Fuso horário do visitante, deslocamento do GMT em horas (por exemplo, -8). |
| pageName | pageName | Nome da página. |
| pageType | pageType | Tipo de página (por exemplo, &quot;Página de erro&quot;). |
| pageURL | pageURL | URL da página (por exemplo, https://www.example.com/index.html). |
| plugins | plugins | Lista separada por ponto e vírgula de nomes de plug-ins de navegadores. |
| produtos | produtos | Lista de todos os produtos na página. Separe os produtos com vírgula. Por exemplo: Esportes;Bola;1;5.95,Brinquedos; Superior;1:1.99. |
| prop1 - prop75 | propN, ou seja `<prop2>`...`</prop2>` | Sequência de caracteres de número de propriedade (por exemplo, Seção de esportes). |
| propN | propN | Valores da propriedade para suas propriedades. |
| purchaseID | purchaseID | Número da ID de compra. |
| referenciador | referenciador | URL para o referenciador da página. |
| reportSuiteID | s_account | Especifica os conjuntos de relatórios nos quais você deseja enviar dados. Você deve separar várias IDs de conjunto de relatórios com uma vírgula. |
| resolução | resolução | Resolução do monitor (por exemplo, 1024x768). |
| servidor | servidor | Sequência de caracteres do servidor. |
| estado | estado | Sequência de caracteres do estado de conversão. |
| carimbo de data e hora | data | Use o formato de data ISO 8601, YYY-MM-DDThh:mm:ss±UTC_offset (por exemplo, 2021-09-01T12:00:00-07:00 ) ou o Formato de hora Unix (o número de segundos decorridos desde 1° de janeiro de 1970). |
| trackingServer | Não suportado | Só pode ser fornecido por meio do cabeçalho da coluna. |
| transactionID | Não suportado | Valor comum usado para vincular as atividades de usuário multicanal juntamente com fins de relatório. Para obter mais informações, consulte o [Guia do Usuário das Fontes de Dados](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html?lang=en#data-sources). |
| userAgent | Não suportado | Sequência de agente do usuário |
| visitorID | visitorID | Analytics ID do visitante. Consulte [Identificação do visitante](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en). |
| CEP | CEP | CEP de conversão. |
