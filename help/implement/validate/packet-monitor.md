---
title: Analisadores de pacote
description: Os analisadores de pacote permitem exibir os dados enviados pela implementação para os servidores de coleta de dados da Adobe.
keywords: sniffer de pacote, status http, 200, 302, charles
feature: Implementation Basics
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/debgxI3FK1fp1Q02GY1-0H40z-L4G2HSmq11Tog97-Y'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2: id: e992d880-33bc-4949-a648-aa7d410276cd
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 679
ht-degree: 69%

---

# Analisadores de pacote

Os analisadores de pacote permitem exibir os dados enviados pela implementação para os servidores de coleta de dados da Adobe.

Semelhante ao Adobe CX Enterprise Debugger, um monitor de pacote mostra quais parâmetros de dados são transmitidos em uma solicitação de imagem. No entanto, monitores de pacotes oferecem funcionalidades adicionais:

* Exibir solicitações de imagem de rastreamento de link personalizado
* Visualizar solicitações de imagem usando métodos de implementação diferentes do JavaScript, como solicitações de imagens codificadas ou [!DNL Appmeasurement]

Para exibir solicitações do Analytics, filtre as solicitações de saída usando &quot;b/ss&quot;.

Em casos muito raros, o depurador cria um relatório de solicitação de imagem, mas nenhuma solicitação chega a servidores de processamento do [!DNL Analytics] da Adobe. O uso de um monitor de pacote é uma ótima maneira de ter 100% de certeza de que uma solicitação de imagem específica está sendo acionada com sucesso.

Embora a Adobe não forneça um monitor oficial de pacotes, há uma grande variedade deles na Internet. Veja a seguir alguns monitores de pacote que outros acharam úteis.

>[!TIP]
>
>Estas listas não estão completas, mas são informações sobre os monitores usados frequentemente.

| Firefox | Internet Explorer | Chrome | Programas Autônomos |
|---|---|---|---|
| [Ponto de observação](https://www.observepoint.com/product#plugin) (visualizador de marcas) | [HttpWatch](https://www.httpwatch.com/) | [Ponto de observação](https://www.observepoint.com/product#plugin) (visualizador de marcas) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.thunderbird.net/en-us/firefox/addon/httpfox/) |  | [Ferramentas de desenvolvedor do Google Chrome](https://code.google.com/chrome/devtools/docs/overview.html) | [Criador](https://www.telerik.com/fiddler) |
| [Dados de adulteração](https://addons.mozilla.org/pt-BR/firefox/addon/tamper-data-for-ff-quantum/) |  | [Firebug Lite](https://chromewebstore.google.com/detail/firebug-lite-for-google-c/ehemiojjcpldeipjhjkepfdaohajpbdo) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
>A Adobe NÃO oferece suporte ou solução de problemas que você possa ter com esses monitores de pacote. Para obter assistência, consulte o site de origem do monitor de pacote.

## Códigos de status de resposta HTTP típicos

Quando o AppMeasurement envia dados para os servidores de coleta de dados da Adobe, os servidores respondem com um código de status de resposta.

* **200 OK**: a resposta mais comum dos servidores de coleta de dados. A solicitação de imagem foi recebida com êxito e uma imagem transparente foi retornada.
* **302 ENCONTRADO**: há algumas razões possíveis para receber esta resposta:
   * A primeira solicitação de imagem de um visitante: um redirecionamento ocorre se um usuário visitar seu site pela primeira vez. Esse redirecionamento é para obter um cookie de visitante. A coleta de dados não é afetada.
   * Integração entre a Comscore e a Adobe: se a sua organização usar uma integração Comscore/Analytics, cada solicitação de imagem sempre resultará em uma resposta 302.
* **404 NÃO ENCONTRADO**: essa resposta significa que a solicitação de imagem não foi encontrada e os dados não são enviados para os servidores de coleta de dados da Adobe. Essa resposta também é possível quando solicitações de imagem codificadas não estão formatadas corretamente. Fale com a pessoa ou a equipe que implementou o Analytics para resolver esse problema.

## NS_BINDING_ABORTED em códigos de resposta

Essa mensagem ocorre porque a solicitação de imagem de rastreamento de link foi projetada para permitir que o navegador continue para a página seguinte antes de aguardar uma resposta dos servidores de coleta de dados da Adobe.

A resposta da Adobe à solicitação de imagem é uma imagem transparente 1x1 em branco, que não é relevante para o conteúdo da página. Se você vir um item de linha em seu monitor de pacotes da Adobe, com uma resposta **[!UICONTROL 200 OK]** ou uma resposta **[!UICONTROL NS_BINDING_ABORTED]**, os dados chegaram aos nossos servidores. Não há necessidade de ter a página aguardando mais.

Monitores de pacote integrados como um plug-in raramente veem a resposta completa. Eles tendem a ver a solicitação como anulada porque a resposta completa não foi recebida. Esses monitores também raramente fazem uma distinção entre se foi a solicitação ou a resposta que foi abortada. Um monitor de pacote independente geralmente tem mensagens mais detalhadas e relata o status com mais precisão. Por exemplo, um usuário pode receber uma mensagem em *Charles* dizendo &quot;Conexão fechada do cliente antes de receber resposta inteira&quot;. Isso significa que os dados chegaram aos nossos servidores, apenas o navegador foi movido para a próxima página antes do pixel 1x1 ser recebido.

Se um monitor de pacote externo relata que a solicitação de coleção de dados foi abortada, em vez da resposta, isso pode ser preocupante. A Adobe [!DNL Customer Care] pode fornecer ajuda para solucionar o problema.
