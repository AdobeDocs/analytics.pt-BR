---
title: Tipo de referenciador
description: O tipo de quem indicou, dependendo de onde o visitante veio.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---


# Tipo de referenciador

A dimensão &#39;Tipo de Quem indicou&#39; relata quais visitantes genéricos de canais clicaram para chegar ao site. A Adobe mantém as regras para cada item de dimensão, ao contrário dos canais [de](marketing-channel.md)marketing, onde sua organização mantém regras para cada canal.

## Preencher esta dimensão com dados

Essa dimensão faz referência a várias tabelas de pesquisa internas da Adobe. Cada valor é baseado na [quem indicou](referrer.md) da ocorrência, que depende dos filtros [de URL](/help/admin/admin/internal-url-filter-admin.md)internos. Verifique se a dimensão de quem indicou e os filtros internos de URL estão configurados corretamente.

## Itens de dimensão

Os itens de dimensão incluem o tipo de quem indicou da ocorrência. Os valores específicos incluem:

* **Digitado/Marcado**: Não existem dados de quem indicou para a ocorrência.
* **Mecanismos** de pesquisa: A quem indicou veio de um mecanismo de pesquisa reconhecido que inclui uma string de query de palavra-chave.
* **Redes sociais:**: Os dados de Quem indicou pertenciam a uma rede social reconhecida pela Adobe.
* **Outros sites**: Os dados de Quem indicou não pertenciam a um mecanismo de pesquisa ou rede social reconhecida pela Adobe.
* **Disco rígido**: Quem indicou originada de uma cópia local de uma página da Web no disco rígido do visitante.
* **Email**: Quem indicou originada de um URL com um protocolo de `imap://` ou `mail://`. Não inclui serviços de e-mail online, pois eles normalmente usam `https://` protocolo.

### Redes sociais

A lista a seguir faz referência à tabela de pesquisa &quot;Redes sociais&quot; que a Adobe usa. A Adobe oferece essa lista como cortesia para os clientes da Adobe Analytics. Se você quiser recomendar que a Adobe adicione um domínio a essa lista, peça a um representante de suporte em sua organização para entrar em contato com o Atendimento ao cliente.

>[!NOTE]
>
>Essa lista é diferente da lista padrão das redes sociais nas regras [de processamento do](../c-marketing-channels/c-rules.md)canal de marketing.

* `12seconds.tv`
* `t.163.com`
* `4travel.jp`
* `advogato.org`
* `ameba.jp`
* `anobii.com`
* `asmallworld.net`
* `avforums.com`
* `backtype.com`
* `badoo.com`
* `bebo.com`
* `bigadda.com`
* `bigtent.com`
* `biip.no`
* `blackplanet.com`
* `blogspot.com`
* `blogster.com`
* `blomotion.jp`
* `bolt.com`
* `brightkite.com`
* `buzznet.com`
* `cafemom.com`
* `care2.com`
* `classmates.com`
* `cloob.com`
* `collegeblender.com`
* `cyworld.co.kr`
* `cyworld.com.cn`
* `dailymotion.com`
* `yozm.daum.net`
* `delicious.com`
* `deviantart.com`
* `digg.com`
* `diigo.com`
* `disqus.com`
* `draugiem.lv`
* `facebook.com`
* `faceparty.com`
* `fc2.com`
* `flickr.com`
* `flixster.com`
* `fotolog.com`
* `foursquare.com`
* `friendfeed.com`
* `friendsreunited.com`
* `friendsreunited.co.uk`
* `friendster.com`
* `fubar.com`
* `gaiaonline.com`
* `geni.com`
* `goodreads.com`
* `plus.google.com`
* `plus.url.google.com`
* `grono.net`
* `habbo.com`
* `hatena.ne.jp`
* `t.hexun.com`
* `hi5.com`
* `hyves.nl`
* `ibibo.com`
* `identi.ca`
* `t.ifeng.com`
* `imeem.com`
* `hotnews.infoseek.co.jp`
* `instagram.com`
* `intensedebate.com`
* `irc-galleria.net`
* `iwiw.hu`
* `jaiku.com`
* `kaixin001.com`
* `kaixin002.com`
* `kakaku.com`
* `kanshin.com`
* `kozocom.com`
* `last.fm`
* `linkedin.com`
* `livejournal.com`
* `lnkd.in`
* `me2day.net`
* `meetup.com`
* `mister-wong.com`
* `mixi.jp`
* `mixx.com`
* `mouthshut.com`
* `multiply.com`
* `mumsnet.com`
* `myheritage.com`
* `mylife.com`
* `myspace.com`
* `myyearbook.com`
* `nasza-klasa.pl`
* `matome.naver.jp`
* `netlog.com`
* `nettby.no`
* `netvibes.com`
* `nextdoor.com`
* `nicovideo.jp`
* `ning.com`
* `odnoklassniki.ru`
* `ok.ru`
* `orkut.com`
* `pakila.jp`
* `t.people.com.cn`
* `photobucket.com`
* `pinterest.com (and all international domains)`
* `plaxo.com`
* `plurk.com`
* `po.st`
* `t.qq.com`
* `mp.weixin.qq.com`
* `boards.qwant.com`
* `reddit.com`
* `renren.com`
* `blog.seesaa.jp`
* `t.sina.com.cn`
* `skyrock.com`
* `slideshare.net`
* `smcb.jp`
* `smugmug.com`
* `t.sohu.com`
* `sonico.com`
* `studivz.net`
* `stumbleupon.com`
* `t.co`
* `tabelog.com`
* `tagged.com`
* `taringa.net`
* `thefancy.com`
* `toutiao.com`
* `tripit.com`
* `trombi.com`
* `trytrend.jp`
* `tuenti.com`
* `tumblr.com`
* `twine.com`
* `twitter.com`
* `uhuru.jp`
* `viadeo.com`
* `vimeo.com`
* `vk.com`
* `wayn.com`
* `weibo.com`
* `weourfamily.com`
* `wer-kennt-wen.de`
* `wordpress.com`
* `xanga.com`
* `xing.com`
* `answers.yahoo.com`
* `yammer.com`
* `yaplog.jp`
* `yelp.com`
* `yelp.co.uk`
* `youku.com`
* `youtube.com`
* `yuku.com`
* `zooomr.com`
* `zhihu.com`

### Mecanismos de pesquisa no item de dimensão &quot;Outros sites&quot;

Quando você visualização domínios específicos na dimensão &#39;Tipo de Quem indicou&#39;, pode haver domínios que você esperaria em &#39;Mecanismos de pesquisa&#39; listados em vez de &#39;Outros sites&#39;. Por exemplo, você pode ver `'google.com'` em &#39;Outros sites&#39;.

* **Domínios de mecanismo de pesquisa no item** de dimensão &#39;Mecanismos de pesquisa&#39;: A quem indicou atendeu a todos os critérios para classificar como um mecanismo de pesquisa pela Adobe. O domínio de referência é um mecanismo de pesquisa válido *e* o URL de referência contém um parâmetro de string de query de palavra-chave.
* **Domínios do mecanismo de pesquisa no item** de dimensão &quot;Outros sites&quot;: O URL de referência não atendia a todos os critérios para classificar como um mecanismo de pesquisa. Exemplos comuns incluem subdomínios dedicados a outros recursos além da pesquisa. Por exemplo, `mail.google.com` ou não `autos.yahoo.com` são mecanismos de pesquisa, mas residem em um domínio de nível superior normalmente associado à pesquisa. Esses subdomínios não incluem uma sequência de query de palavra-chave, razão pela qual são incluídos em &quot;Outros sites&quot; em vez de &quot;Mecanismos de pesquisa&quot;.
