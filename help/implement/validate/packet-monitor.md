---
title: Analisadores de pacote
description: Os analisadores de pacote permitem exibir os dados enviados pela implementação para os servidores de coleta de dados da Adobe.
keywords: packet sniffer, http status, 200, 302, charles
translation-type: tm+mt
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 60%

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
| [HttpFox](https://addons.mozilla.org/en-US/firefox/addon/httpfox/) |  | [Ferramentas de desenvolvedor do Google Chrome](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Tamper Data](https://addons.mozilla.org/en-us/firefox/addon/tamper-data/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
>O Adobe NÃO oferece suporte ou solução de problemas que você tenha com esses monitores de pacote. Consulte o site de origem do monitor de pacote para obter assistência.

## Códigos típicos de status de resposta HTTP

Quando o AppMeasurement envia dados para os servidores de coleta de dados do Adobe, os servidores respondem com um código de status de resposta.

* **200 OK**: A resposta mais comum dos servidores de coleta de dados. A solicitação de imagem foi recebida com êxito e uma imagem transparente foi retornada.
* **302 ENCONTRADO**: Há algumas razões possíveis para receber esta resposta:
   * A primeira solicitação de imagem de um visitante: Um redirecionamento ocorre se um usuário visitar seu site pela primeira vez. Esse redirecionamento é para obter um cookie de visitante. Isso não afeta a coleta de dados.
   * Integração entre Comscore e Adobe: Se sua organização usar uma integração Comscore/Analytics, cada solicitação de imagem sempre resultará em uma resposta 302.
* **404 NÃO ENCONTRADO**: Essa resposta significa que a solicitação de imagem não foi encontrada e os dados não são enviados para os servidores de coleta de dados do Adobe. Essa resposta também é possível quando solicitações de imagem codificadas não estão formatadas corretamente. Trabalhe com o indivíduo ou a equipe que implementou o Analytics para resolver esse problema.

## NS_BINDING_ABORTED em códigos de resposta

Essa mensagem ocorre porque a solicitação de imagem de rastreamento de link foi projetada para permitir que o navegador continue para a página seguinte antes de aguardar uma resposta dos servidores de coleta de dados do Adobe.

A resposta da Adobe à solicitação de imagem é uma imagem transparente 1x1 em branco, que não é relevante para o conteúdo da página. If you see a line item in your packet monitor from Adobe, either with a **[!UICONTROL 200 OK]** response or an **[!UICONTROL NS_BINDING_ABORTED]** response, the data has reached Adobe&#39;s servers. Não há necessidade de fazer com que a página aguarde tanto tempo.

Monitores de pacote integrados como um plug-in raramente veem a resposta completa. Eles tendem a ver a solicitação como abortada pois a resposta completa não foi recebida. Esses monitores também raramente diferenciam se uma solicitação ou uma resposta foi abortada. Um monitor de pacote avulso, contudo, normalmente tem mensagens mais detalhadas e relata o status com mais precisão. Por exemplo, um usuário pode receber uma mensagem em *Charles* dizendo &quot;Conexão fechada do cliente antes de receber resposta inteira&quot;. Isso significa que os dados chegaram aos servidores da Adobe, mas o navegador continuou para a página seguinte antes de o pixel de 1x1 ser recebido.

Se um monitor de pacote externo reportar que a solicitação de coleta de dados foi abortada, em vez da resposta, isso é motivo de preocupação. O Adobe [!DNL Customer Care] pode fornecer ajuda para solucionar o problema.
