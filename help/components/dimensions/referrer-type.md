---
title: Tipo de referenciador
description: O tipo de referenciador dependendo a origem do visitante.
feature: Dimensions
exl-id: a6cfcbf4-cd08-4e7f-8e86-47488ceb0ea3
source-git-commit: 61a8aec9bbd6102dd3c0eb60362e02d553e1ebd2
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 100%

---

# Tipo de referenciador

A dimensão “Tipo de referenciador” informa em quais canais genéricos os visitantes clicaram para acessar seu site. A Adobe mantém regras para cada item de dimensão, ao contrário dos [canais de marketing](marketing-channel.md), em que a própria organização mantém regras para cada canal.

## Preencher esta dimensão com dados

Essa dimensão faz referência a várias tabelas de pesquisa internas da Adobe. Cada valor se baseia no [referenciador](referrer.md) da ocorrência, que depende dos [Filtros de URL internos](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md). Verifique se a dimensão do referenciador e os filtros de URL internos estão configurados corretamente.

## Itens de dimensão

Os itens de dimensão incluem o tipo de referenciador da ocorrência. Valores específicos incluem:

* **Digitado/Marcado**: não existem dados do referenciador para a ocorrência.
* **Mecanismos de pesquisa**: o referenciador veio de um mecanismo de pesquisa reconhecido que inclui uma sequência de consulta de palavra-chave.
* **Redes sociais:**: os dados do referenciador pertenciam a uma rede social reconhecida pela Adobe.
* **Outros sites**: os dados do referenciador não pertenciam a um mecanismo de pesquisa ou rede social reconhecida pela Adobe.
* **Disco rígido**: o referenciador é originado de uma cópia local de uma página da Web no disco rígido do visitante.
* **Email**: o referenciador é originado de um URL com um protocolo de `imap://` ou `mail://`. Não inclui serviços de email online, pois eles normalmente utilizam o protocolo `https://`.

### Redes sociais

A lista a seguir faz referência à tabela de pesquisa &quot;Redes sociais&quot; que a Adobe utiliza. A Adobe oferece essa lista como cortesia para os clientes do Adobe Analytics. Se você quiser que a Adobe adicione um domínio a esta lista, peça para um representante de suporte da sua organização entrar em contato com o Atendimento ao cliente.

>[!NOTE]
>
>Essa lista é diferente da lista padrão de redes sociais nas [Regras de processamento de canal de marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md).

* `12seconds.tv`
* `4travel.jp`
* `advogato.org`
* `ameba.jp`
* `anobii.com`
* `answers.yahoo.com`
* `asmallworld.net`
* `avforums.com`
* `backtype.com`
* `badoo.com`
* `bebo.com`
* `bigadda.com`
* `bigtent.com`
* `biip.no`
* `blackplanet.com`
* `blog.seesaa.jp`
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
* `hi5.com`
* `hotnews.infoseek.co.jp`
* `hyves.nl`
* `ibibo.com`
* `identi.ca`
* `t.ifeng.com`
* `imeem.com`
* `instagram.com`
* `intensedebate.com`
* `irc-galleria.net`
* `iwiw.hu`
* `jaiku.com`
* `jp.myspace.com`
* `kaixin001.com`
* `kakaku.com`
* `kanshin.com`
* `kozocom.com`
* `last.fm`
* `linkedin.com`
* `livejournal.com`
* `lnkd.in`
* `meetup.com`
* `me2day.net`
* `mister-wong.com`
* `mixi.jp`
* `mixx.com`
* `mouthshut.com`
* `mp.weixin.qq.com`
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
* `photobucket.com`
* `pinterest.com`
* `pinterest.co.uk`
* `plaxo.com`
* `plurk.com`
* `po.st`
* `reddit.com`
* `renren.com`
* `skyrock.com`
* `slideshare.net`
* `smcb.jp`
* `smugmug.com`
* `snapchat.com`
* `sonico.com`
* `studivz.net`
* `stumbleupon.com`
* `t.163.com`
* `t.co`
* `t.hexun.com`
* `t.people.com.cn`
* `t.qq.com`
* `t.sina.com.cn`
* `t.sohu.com`
* `tabelog.com`
* `tagged.com`
* `taringa.net`
* `thefancy.com`
* `tiktok.com`
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
* `yammer.com`
* `yaplog.jp`
* `yelp.com`
* `yelp.co.uk`
* `youku.com`
* `youtube.com`
* `yozm.daum.net`
* `yuku.com`
* `zooomr.com`
* `zhihu.com`

### Mecanismos de pesquisa no item de dimensão “Outros sites”

Ao visualizar domínios específicos na dimensão “Tipo do referenciador”, é possível encontrar domínios que seriam esperados em &#39;”Mecanismos de pesquisa” em vez de “Outros sites”. Por exemplo, você pode ver `'google.com'` em “Outros sites”.

* **Domínios de mecanismo de pesquisa no item de dimensão “Mecanismos de pesquisa”**: o referenciador atendeu a todos os critérios para se classificar como um mecanismo de pesquisa pela Adobe. O domínio referenciador é um mecanismo de pesquisa válido, *e* o URL de referência contém um parâmetro da sequência de consulta de palavras-chave.
* **Domínios do mecanismo de pesquisa no item de dimensão “Outros sites”**: o URL de referência não atendia a todos os critérios para se classificar como um mecanismo de pesquisa. Exemplos comuns incluem subdomínios dedicados a outros recursos além da pesquisa. Por exemplo, `mail.google.com` ou `autos.yahoo.com` não são mecanismos de pesquisa, mas residem em um domínio de nível superior normalmente associado à pesquisa. Esses subdomínios não incluem uma sequência de consulta de palavra-chave, razão pela qual são incluídos em &quot;Outros sites&quot; em vez de &quot;Mecanismos de pesquisa&quot;.
