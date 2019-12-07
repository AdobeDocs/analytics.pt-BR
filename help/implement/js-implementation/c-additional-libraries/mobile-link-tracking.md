---
description: 'null'
keywords: Analytics Implementation;link reference;redir
title: Medição de link padrão em protocolos móveis
topic: Developer and implementation
uuid: eb82de26-da2e-41c2-8924-59b6b5ccef28
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Medição de link padrão em protocolos móveis

Vários usuários de dispositivos móveis baixam os arquivos para seus dispositivos, como podcasts, toques de telefone e arquivos semelhantes. Como vários dispositivos móveis não são compatíveis com JavaScript, a medição de link deve ser implementada através de direcionamentos. Para usar redirecionamentos, você deve modificar os links href no html para incluir o elemento REDIR. O formato geral para um link personalizado é o seguinte:

```
https://<your_Namespace>.112.2o7.net/b/ss/<RSID>/4/REDIR/
?url=<destination_URL>&pe=<link_type>&pev1=<current_URL>&pev2=<link_name>
```

Lembre-se do seguinte ao criar a referência do link:

* O valor do URL deve ser codificado.
* É necessário definir um parâmetro pageName ou de URL de página (g).
* As variáveis dinâmicas podem ler parâmetros de URL, mas não defini-los.
* Se não existirem cookies definidos, os servidores Adobe executam um handshake normal de cookie.
* Para rastrear links, você deve incluir os parâmetros pe, pev1 e pev2.

O URL de medição de link personalizado é semelhante ao seguinte:

```
<a href=" https://johnny_appleseed.122.2o7.net/b/ss/appleseedpodcasts/4/REDIR/
?url=http%3A%2F%2Fwww.johnny_appleseed.org%2Fmpegs%2Fplanting_apple_trees.mpeg&pe=lnk_d
&pev1=http%3A%2F%2Fwww.johnny_appleseed.org%2Fmpegs%2Fplanting_apple_trees.mpeg&pev2=pl anting_apple_trees&">Planting an Apple Tree</a>
```

Para obter mais informações, consulte o [white paper Redirecionamentos por rastreamento de link de saída](https://marketing.adobe.com/resources/help/en_US/whitepapers/redirects/).
