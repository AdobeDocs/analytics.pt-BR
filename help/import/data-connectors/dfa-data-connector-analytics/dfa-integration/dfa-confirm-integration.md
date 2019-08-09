---
description: Depois de fazer todas as atualizações necessárias no site, você pode usar um visualizador de tráfego de rede, como o Charles*, as ferramentas de desenvolvedor do Chrome ou o Firebug*, para confirmar se o DFA está se comunicando com os servidores de coleta da Adobe.
keywords: DFA
seo-description: Depois de fazer todas as atualizações necessárias no site, você pode usar um visualizador de tráfego de rede, como o Charles*, as ferramentas de desenvolvedor do Chrome ou o Firebug*, para confirmar se o DFA está se comunicando com os servidores de coleta da Adobe.
seo-title: Confirmação de uma integração do DFA bem-sucedida
solution: Analytics
title: Confirmação de uma integração do DFA bem-sucedida
topic: Conectores de dados
uuid: d 658 cd 7 c -6377-439 a -850 c-ecea 8 c 41 f 970
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Confirmação de uma integração do DFA bem-sucedida{#confirming-a-successful-dfa-integration}

Depois de fazer todas as atualizações necessárias no site, você pode usar um visualizador de tráfego de rede, como o Charles*, as ferramentas de desenvolvedor do Chrome ou o Firebug*, para confirmar se o DFA está se comunicando com os servidores de coleta da Adobe.

Depois de implantar o arquivo `s_code.js` habilitado para o DFA, use o visualizador de tráfego de rede para exibir as solicitações entre o DFA e os servidores de coleta de dados da Adobe e procure o seguinte:

* A request to DFA's `fls.doubleclick.net/json` service. Esse serviço pode responder de modo diferente dependendo da versão do DFA que você está usando. Com a versão 1.5 da integração do DFA:

   * Um redirecionamento HTTP 302 para [!DNL ad.doubleclick.net]. Isso enviará uma tag Location: na resposta que contém informações sobre o visitante do anúncio.
   * This Location tag causes a redirect to [!DNL integrate.112.2o7.net/dfa_echo]. Esse serviço traduz as informações sobre o visitante do anúncio para uma sequência codificada JSON (JavaScript Object Notation). Esses dados são devolvidos com uma resposta 200 OK HTTP.

* Com a versão 2.0 da integração do DFA (habilitada para exibição de anúncios avançada):

   * [!DNL fls.doubleclick.net] responderá diretamente com 200 OK.

Em todo caso, uma solicitação bem-sucedida resultará em uma solicitação para os servidores de coleta de dados da Adobe que contém o parâmetro vX, em que X é o número de sua eVar de view-through. O valor desse parâmetro apresenta a forma: DFA-XXXX-XXXX- XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX. Essa sequência contém dados sobre o último clique e a última impressão do visitante atual.
