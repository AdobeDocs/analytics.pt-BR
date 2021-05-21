---
title: Analisadores de pacote
description: Os analisadores de pacote permitem exibir os dados enviados pela implementação para os servidores de coleta de dados da Adobe.
keywords: sniffer de pacote, status http, 200, 302, charles
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '664'
ht-degree: 100%

---

# Analisadores de pacote

Os analisadores de pacote permitem exibir os dados enviados pela implementação para os servidores de coleta de dados da Adobe.

Assim como o Adobe Experience Cloud Debugger, um monitor de pacote mostra quais parâmetros de dados são transmitidos em uma solicitação de imagem. No entanto, monitores de pacotes oferecem funcionalidades adicionais:

* Exibir solicitações de imagem de rastreamento de link personalizado
* Visualizar solicitações de imagem usando métodos de implementação diferentes do JavaScript, como solicitações de imagens codificadas ou [!DNL Appmeasurement]

Para exibir solicitações do Analytics, filtre as solicitações de saída usando &quot;b/ss&quot;.

Em casos muito raros, o depurador cria um relatório de solicitação de imagem, mas nenhuma solicitação chega a servidores de processamento do [!DNL Analytics] da Adobe. Usar um monitor de pacote é uma ótima maneira de ter 100% de certeza de que uma solicitação de imagem específica será acionada com sucesso.

Enquanto a Adobe não oferece um monitor de pacote oficial, há uma grande variedade deles na internet. Os seguintes são alguns monitores de pacotes que outras pessoas acharam úteis.

>[!TIP]
>
>Estas listas não estão completas, mas são informações sobre os monitores usados frequentemente.

| Firefox | Internet Explorer | Chrome | Programas autônomos |
|---|---|---|---|
| [Ponto de observação](https://www.observepoint.com/product#plugin) (visualizador de tag) | [HttpWatch](https://www.httpwatch.com/) | [Ponto de observação](https://www.observepoint.com/product#plugin) (visualizador de tag) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.thunderbird.net/en-us/firefox/addon/httpfox/) |  | [Ferramentas de desenvolvedor do Google Chrome](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Tamper Data](https://addons.mozilla.org/pt-BR/firefox/addon/tamper-data-for-ff-quantum/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
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

A resposta da Adobe à solicitação de imagem é uma imagem transparente 1x1 em branco, que não é relevante para o conteúdo da página. Se você vir um item de linha em seu monitor de pacotes da Adobe, com uma resposta **[!UICONTROL 200 OK]** ou uma resposta **[!UICONTROL NS_BINDING_ABORTED]**, os dados chegaram aos nossos servidores. Não há necessidade de fazer com que a página aguarde tanto tempo.

Monitores de pacote integrados como um plug-in raramente veem a resposta completa. Eles tendem a ver a solicitação como abortada pois a resposta completa não foi recebida. Esses monitores também raramente diferenciam se uma solicitação ou uma resposta foi abortada. Um monitor de pacote avulso, contudo, normalmente tem mensagens mais detalhadas e relata o status com mais precisão. Por exemplo, um usuário pode receber uma mensagem em *Charles* dizendo &quot;Conexão fechada do cliente antes de receber resposta inteira&quot;. Isso significa que os dados chegaram aos servidores da Adobe, mas o navegador continuou para a página seguinte antes de o pixel de 1x1 ser recebido.

Se um monitor de pacote externo relata que a solicitação de coleção de dados foi abortada, em vez da resposta, isso pode ser preocupante. A Adobe [!DNL Customer Care] pode fornecer ajuda para solucionar o problema.
