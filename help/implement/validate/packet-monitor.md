---
title: Analisadores de pacote
description: Os analisadores de pacote permitem exibir os dados enviados pela implementação para os servidores de coleta de dados da Adobe.
translation-type: ht
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Analisadores de pacote

Os analisadores de pacote permitem exibir os dados enviados pela implementação para os servidores de coleta de dados da Adobe.

Assim como o Adobe Experience Cloud Debugger, um monitor de pacote mostra quais parâmetros de dados são transmitidos em uma solicitação de imagem. No entanto, monitores de pacotes oferecem funcionalidades adicionais:

* Exibir solicitações de imagem de rastreamento de link personalizado
* Visualizar solicitações de imagem usando métodos de implementação diferentes do JavaScript, como solicitações de imagens codificadas ou [!DNL Appmeasurement]

Para exibir solicitações do Analytics, filtre as solicitações de saída usando &quot;b/ss&quot;.

Em casos muito raros, o depurador cria um relatório de solicitação de imagem, mas nenhuma solicitação chega a servidores de processamento do [!DNL Analytics] da Adobe. Usar um monitor de pacote é uma ótima maneira de ter 100% de certeza de que uma solicitação de imagem específica será acionada com sucesso.

Enquanto a Adobe não oferece um monitor de pacote oficial, há uma grande variedade deles na internet. Os seguintes são alguns monitores de pacotes que outras pessoas acharam úteis.

> [!NOTE] Estas listas não estão completas, mas são informações sobre os monitores usados frequentemente. Se você tiver um monitor de pacote que use e ache útil, sinta-se à vontade para oferecer feedback usando o botão [!UICONTROL Feedback] no lado direito desta janela.

| Firefox | Internet Explorer | Chrome | Programas autônomos |
|---|---|---|---|
| [Ponto de observação](https://www.observepoint.com/product#plugin) (visualizador de tag) | [HttpWatch](https://www.httpwatch.com/) | [Ponto de observação](https://www.observepoint.com/product#plugin) (visualizador de tag) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.mozilla.org/en-US/firefox/addon/httpfox/) |  | [Ferramentas de desenvolvedor do Google Chrome](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Tamper Data](https://addons.mozilla.org/en-us/firefox/addon/tamper-data/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

> [!NOTE] A Adobe NÃO oferece suporte ou solução de problemas que você possa ter com esses monitores de pacote. Para obter assistência, consulte o site de origem do monitor de pacote.

## NS_BINDING_ABORTED em códigos de resposta

O erro ocorre porque a solicitação de imagem de rastreamento de link foi projetada para permitir que o navegador continue para a página seguinte antes de aguardar uma resposta dos servidores de coleta de dados da Adobe.

A resposta da Adobe à solicitação de imagem é uma imagem transparente 1x1 em branco, que não é relevante para o conteúdo da página. Se você vir um item de linha em seu monitor de pacotes da Adobe, com uma resposta **[!UICONTROL 200 OK]** ou uma resposta **[!UICONTROL NS_BINDING_ABORTED]**, os dados chegaram aos nossos servidores. Não há necessidade de fazer com que a página aguarde tanto tempo.

Monitores de pacote integrados como um plug-in raramente veem a resposta completa. Eles tendem a ver a solicitação como abortada pois a resposta completa não foi recebida. Esses monitores também raramente diferenciam se uma solicitação ou uma resposta foi abortada. Um monitor de pacote avulso, contudo, normalmente tem mensagens mais detalhadas e relata o status com mais precisão. Por exemplo, um usuário pode receber uma mensagem em *Charles* dizendo &quot;Conexão fechada do cliente antes de receber resposta inteira&quot;. Isso significa que os dados chegaram aos servidores da Adobe, mas o navegador continuou para a página seguinte antes de o pixel de 1x1 ser recebido.

Se um sniffer de pacote externo relata que a solicitação de coleção de dados foi abortada, em vez da resposta, isso pode ser preocupante. O Adobe [!DNL Customer Care] pode fornecer ajuda para solucionar o problema.
