---
title: Analisadores de pacote
description: Os analisadores de pacote permitem exibir os dados enviados pela implementação para os servidores de coleta de dados da Adobe.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Analisadores de pacote

Os analisadores de pacote permitem exibir os dados enviados pela implementação para os servidores de coleta de dados da Adobe.

Assim como o Adobe Experience Cloud Debugger, um monitor de pacote mostra quais parâmetros de dados são transmitidos em uma solicitação de imagem. No entanto, monitores de pacotes oferecem funcionalidades adicionais:

* Exibir solicitações de imagem de rastreamento de link personalizado
* Visualizar solicitações de imagem usando métodos de implementação diferentes do JavaScript, como solicitações de imagens codificadas ou [!DNL Appmeasurement]

Para exibir solicitações do Analytics, filtre as solicitações de saída usando &quot;b/ss&quot;.

Em casos muito raros, o depurador cria um relatório de solicitação de imagem, mas nenhuma solicitação chega a servidores de processamento do [!DNL Analytics] da Adobe. Usar um monitor de pacote é uma excelente maneira de ter 100% de certeza de que uma solicitação de imagem específica está sendo acionada com êxito.

Embora a Adobe não forneça um monitor de pacote oficial, há uma grande variedade deles na Internet. A seguir estão alguns monitores de pacote que outros acharam úteis.

>[!NOTE] Estas listas não estão completas, mas são informações sobre os monitores usados frequentemente. Se você tiver um monitor de pacote que você usar e achar útil, sinta-se à vontade para fornecer feedback usando o [!UICONTROL Feedback] botão no lado direito desta janela.

| Firefox | Internet Explorer | Chrome | Programas independentes |
|---|---|---|---|
| [Ponto](https://www.observepoint.com/product#plugin) de observação (visualizador de tags) | [HttpWatch](https://www.httpwatch.com/) | [Ponto](https://www.observepoint.com/product#plugin) de observação (visualizador de tags) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.mozilla.org/en-US/firefox/addon/httpfox/) |  | [Ferramentas de desenvolvedor do Google Chrome](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Dados de adulteração](https://addons.mozilla.org/en-us/firefox/addon/tamper-data/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE] A Adobe NÃO oferece suporte ou solução de problemas que você possa ter com esses monitores de pacote. Para obter assistência, consulte o site de origem do monitor de pacote.

## NS_BINDING_ABORTED em códigos de resposta

Esse erro ocorre porque a solicitação de imagem de rastreamento de link foi projetada para permitir que o navegador continue para a página seguinte antes de aguardar uma resposta dos servidores de coleta de dados da Adobe.

A resposta da Adobe à solicitação de imagem é simplesmente uma imagem transparente 1x1 em branco, que não é relevante para o conteúdo da página. Se você vir um item de linha em seu monitor de pacotes da Adobe, com uma resposta **[!UICONTROL 200 OK]** ou uma resposta **[!UICONTROL NS_BINDING_ABORTED]**, os dados chegaram aos nossos servidores. Não é necessário que a página aguarde mais.

Monitores de pacote integrados como um plug-in raramente veem a resposta completa. Eles tendem a ver a solicitação como abortada porque a resposta completa não foi recebida. Esses monitores também raramente distinguem se foi a solicitação ou resposta que foi abortada. Um monitor de pacote independente geralmente tem mensagens mais detalhadas e relata o status com mais precisão. Por exemplo, um usuário pode receber uma mensagem em *Charles* dizendo &quot;Conexão fechada do cliente antes de receber resposta inteira&quot;. Isso significa que os dados chegaram aos nossos servidores, apenas o navegador continuou para a página seguinte antes do pixel de 1x1 ser recebido.

Se um sniffer de pacote externo for relatórios de que a solicitação de coleta de dados foi abortada, em vez da resposta, isso é motivo de preocupação. O Adobe [!DNL Customer Care] pode fornecer ajuda para solucionar o problema.
