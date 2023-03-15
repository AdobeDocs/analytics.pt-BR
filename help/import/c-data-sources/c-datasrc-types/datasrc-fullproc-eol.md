---
title: Fim da vida útil do processamento completo
description: Motivos para o fim da vida útil e comparações entre a API de inserção de dados em massa e as fontes de dados de processamento completo.
feature: Data Sources
exl-id: 24a44b7a-64fd-4a99-975f-4887f4638812
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 100%

---

# Fim da vida útil do processamento completo

Por vários anos, as fontes de dados de processamento completo permitiram enviar dados de nível de ocorrência para o Adobe Analytics. Estes dados foram processados da mesma forma que os dados coletados pelas bibliotecas do JavaScript e pelo SDK do aplicativo móvel. Em 2020, o Adobe lançou o [API de inserção de dados em massa](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md), que executa as mesmas funções das Fontes de dados de processamento completo, mas com recursos adicionais. Este tópico fornece detalhes sobre a funcionalidade adicional fornecida pela API de inserção de dados em massa e descreve as diferenças nos formatos de arquivo.

A partir de 25 de março de 2021, o Adobe impediu a criação de novas conexões de fontes de dados de processamento completo. As conexões existentes eram compatíveis até que o serviço fosse totalmente descontinuado em 31 de janeiro de 2022. Além de nossa documentação padrão, estamos fornecendo uma apresentação das [etapas necessárias para enviar dados por meio da API de inserção de dados em massa](https://adobe.ly/aabdia).

## Por que terminamos a vida útil desse recurso?

A API de inserção de dados em massa (BDIA) fornece funcionalidade adicional enquanto cobre todos os casos de uso compatíveis do processamento completo. É melhor você usar a API de inserção de dados em massa.

## Principais diferenças entre as fontes de dados de processamento completo e a API de inserção de dados em massa

* A inserção de dados em massa permite o envio de vários arquivos que podem ser processados em paralelo. É possível usar Grupos de visitantes para garantir a continuidade do visitante e a atribuição do eVar.
* A inserção de dados em massa tem validação de dados, bem como recursos de tratamento de erros, removendo assim parte do trabalho administrativo de envio de dados de ocorrência.
* A inserção de dados em massa é compatível com várias opções de IDs de visitante. É possível enviar a ID do Analytics e a Experience Cloud ID (Consulte [Serviço de identidade](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR) para saber mais). Além disso, você pode usar sua própria ID como uma [seed para gerar uma ECID](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds).
* A inserção de dados em massa é compatível com as Variáveis de lista e de dados de contexto.
* A inserção de dados em massa não é compatível com dados do Activity Map.

## Principais diferenças no formato e conteúdo do arquivo

* A inserção de dados em massa tem alguns campos obrigatórios adicionais. Consulte a [documentação](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) para obter mais detalhes.
* Para garantir a continuidade do visitante e a atribuição, a inserção de dados em massa requer que as linhas nos arquivos sejam classificadas em ordem cronológica. Consulte [Grupos de visitantes](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups) para saber mais sobre a ordem da atividade do visitante em todos os arquivos.
* A inserção de dados em massa requer que os arquivos sejam compactados em .csv no formato .gzip.
* O BDIA usa &quot;carimbo de hora&quot; em vez de &quot;data&quot;.

Para obter mais detalhes, consulte a seguinte comparação dos valores de campo disponíveis em Inserção de dados em massa (BDIA) e Fontes de dados de processamento completo (FPDS).

## Comparação de valores de campo disponíveis em BDIA e FPDS

| Variável BDIA | Variável de coluna do processamento completo | Descrição |
| --- | --- | --- |
| aamlh | Não suportado | Dica de localização do Adobe Audience Manager. |
| browserHeight | browserHeight | Altura do navegador em pixels (por exemplo, 768) |
| browserWidth | browserWidth | Largura do navegador em pixels (por exemplo, 1024) |
| campaign | campaign | Código de rastreamento da campanha de conversão |
| canal | canal | Sequência de canal (por exemplo, seção de esportes) |
| colorDepth | colorDepth | Profundidade de cores do monitor em bits (por exemplo, 24) |
| connectionType | connectionType | Tipo de conexão do visitante (LAN ou modem) |
| contextData.key | Não suportado | Os pares de valores-chave são especificados ao nomear o cabeçalho como &quot;contextData.product&quot; ou &quot;contextData.color&quot; |
| cookiesEnabled | cookiesEnabled | `Y` ou `N` caso o visitante suporte cookies de sessão primária |
| currencyCode | currencyCode | Código de moeda da receita (por exemplo, `USD`). |
| customerID.[customerIDType].authState | Não suportado | O estado autenticado do visitante. Os valores suportados são: 0, 1, 2, UNKNOWN, AUTHENTICATED, LOGGED_OUT ou &#39;&#39; (não diferencia maiúsculas de minúsculas). Duas aspas simples consecutivas (&#39;&#39;) fazem com que o valor seja omitido da sequência de consulta, que se traduz em 0 quando a ocorrência é feita. Observe que os valores numéricos authState suportados indicam o seguinte: 0 = UNKNOWN, 1 = AUTHENTICATED, 2 = LOGGED_OUT. O customerIDType pode ser qualquer sequência alfanumérica, mas deve ser considerada como a que diferencia maiúsculas de minúsculas. |
| customerID.[customerIDType].id | Não suportado | A ID do cliente a ser usada. O customerIDType pode ser qualquer sequência alfanumérica, mas deve ser considerada como a que diferencia maiúsculas de minúsculas. |
| customerID.[customerIDType].isMCSeed | Não suportado | Se esta é ou não a seed para o ID de visitante do Experience Cloud. Os valores suportados são: 0, 1, TRUE, FALSE, &#39;&#39; (não diferencia maiúsculas de minúsculas). Usar 0, FALSE ou duas aspas simples consecutivas (&#39;&#39;) faz com que o valor seja omitido da sequência de consulta. O customerIDType pode ser qualquer sequência alfanumérica, mas deve ser considerada como a que diferencia maiúsculas de minúsculas. |
| eVarN | eVarN, ou seja `<eVar2>`...`<eVar>` | Nome do eVar de conversão. É possível ter até 75 eVars ( (eVar1 - eVar75 ) Você pode especificar o nome do eVar (eVar12) ou um nome amigável (Campanha publicitária 3). |
| events | events | [Sequência de eventos](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=pt-BR#vars), formatada com a mesma sintaxe da variável s.events. Por exemplo: scAdd, event1, event7 |
| hierN | hierN, ou seja `<hier2>`...`</hier2>` | Nome da hierarquia. É possível ter até 5 hierarquias ( hier1 - hier5 ). Você pode especificar o nome de hierarquia padrão `hier2` ou um nome amigável (Yankees). |
| homePage | homePage | S ou N, é a página atual da página inicial do visitante. |
| ipaddress | Não suportado | O endereço IP do visitante. |
| javaEnabled | javaEnabled | S ou N, o visitante tem o Java habilitado. |
| javaScriptVersion | javaScriptVersion | Versão do JavaScript (por exemplo, 1.3) |
| idioma | Não suportado | O idioma suportado do navegador. Por exemplo, `en-us`. |
| linkName | linkName | Nome do link. |
| linkType | linkType | Tipo de link. Os valores compatíveis incluem: `d: Download link`, `e: Exit link`, `o: Custom link`. |
| linkURL | linkURL | HREF do link. |
| listn Por exemplo, list2. | Não suportado | Uma lista delimitada de valores passados para uma variável e, em seguida, reportados como itens de linha individuais para relatório |
| marketingCloudVisitorID | Não suportado | Experience Cloud ID. Consulte a [Identificação do visitante](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR#id-service-api) e o Serviço de ID de visitante do Experience Cloud |
| Não suportado | charSet | O caractere suportado definido para o seu site. Por exemplo, UTF-8, ISO-8859-1, e assim por diante. |
| Não suportado | clickAction | Identificador de objeto para o mapa de cliques do visitante (oid) |
| Não suportado | clickActionType | Tipo de identificador de objeto para o mapa de cliques do visitante (oidt) |
| Não suportado | clickContext | Identificador de página para o mapa de cliques do visitante (pid) |
| Não suportado | clickContextType | Identificador de página para o mapa de cliques do visitante (pidt) |
| Não suportado | clickSourceID | Índice da fonte para o mapa de cliques do visitante (oi) |
| Não suportado | clickTag | Nome da tag do objeto para o mapa de cliques do visitante (ot) |
| Não suportado | scXmlVer | Número da versão da solicitação de XML de relatórios de marketing (por exemplo, 1.0). |
| Não suportado | fuso horário | Fuso horário do visitante, deslocamento do GMT em horas (por exemplo, -8). |
| pageName | pageName | Nome da página |
| pageType | pageType | Tipo de página (por exemplo, &quot;Página de erro&quot;). |
| pageURL | pageURL | URL da página (por exemplo, https://www.example.com/index.html). |
| plugins | plugins | Lista de nomes de plug-ins de navegadores separada por ponto e vírgula. |
| produtos | produtos | Lista de todos os produtos na página. Separe os produtos com uma vírgula. Por exemplo: Esportes;Bola;1;5.95,Brinquedos; Superior;1:1.99. |
| prop1 - prop75 | propN, ou seja `<prop2>`...`</prop2>` | Propriedade# sequência (por exemplo, Seção de esportes). |
| propN | propN | Valores da propriedade para suas propriedades. |
| purchaseID | purchaseID | Número da ID de compra. |
| referenciador | referenciador | URL para o referenciador da página. |
| reportSuiteID | s_account | Especifica os conjuntos de relatórios nos quais você deseja enviar dados. Separe as várias IDs de conjunto de relatórios com uma vírgula. |
| resolução | resolução | Resolução do monitor (por exemplo, 1024x768). |
| servidor | servidor | Sequência de caracteres do servidor. |
| estado | estado | Sequência de caracteres do estado de conversão. |
| carimbo de data e hora | data | Use o formato de data AAAA-MM-DDThh:mm:ss±UTC_offset da ISO 8601: (por exemplo, 2021-09-01T12:00::00-07:00) ou o formato de hora Unix (o total de segundos decorridos desde 1° de janeiro de 1970). |
| trackingServer | Não suportado | Só pode ser fornecido por meio do cabeçalho da coluna. |
| transactionID | Não suportado | Valor comum usado para vincular as atividades de usuário multicanal juntamente para fins de relatório. Para obter mais informações, consulte o [Guia do Usuário das fontes de dados](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html?lang=pt-BR#data-sources). |
| userAgent | Não suportado | Sequência de agente do usuário |
| visitorID | visitorID | ID Analytics do visitante. Consulte a [Identificação do visitante](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR). |
| CEP | CEP | CEP de conversão. |
