---
title: Tipo de referenciador
description: O tipo de referenciador dependendo a origem do visitante.
feature: Dimensions
exl-id: a6cfcbf4-cd08-4e7f-8e86-47488ceb0ea3
TQID: 'https://experienceleague.adobe.com/KPTS2iWls0V8I2gI0xcH1V89w0stZyVq6jWdQyEyrLY'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b7156124-d291-4de4-ac0c-ed17d8078449
    internal-label: AI Tools
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: b4c7365f660ff093731d55c7aba9cae5ade76789
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 47%
---
# Tipo de referenciador

A [dimensão](overview.md) de &quot;Tipo de referenciador&quot; informa em quais canais genéricos os visitantes clicaram para acessar seu site. A Adobe mantém regras para cada item de dimensão, ao contrário dos [canais de marketing](marketing-channel.md), em que a própria organização mantém regras para cada canal.

## Preencher esta dimensão com dados

O Adobe deriva essa dimensão do [referenciador](referrer.md) de cada ocorrência, comparando-a com várias tabelas de pesquisa internas do Adobe. Não há variável a ser definida. Como cada valor depende do referenciador, verifique se a dimensão do referenciador e os [filtros internos de URL](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) estão configurados corretamente.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (derivado do referenciador) |
| **Web SDK / campo XDM** | Nenhum (derivado do referenciador) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | N/D |

## Itens de dimensão

Os itens de dimensão incluem o tipo de referenciador do hit. Valores específicos incluem:

* **Digitado/Marcado**: não existem dados do referenciador para o hit. Este valor inclui visitas de [ferramentas de IA conversacional que abrem links sem um referenciador](#include-ai-traffic-that-has-no-referrer).
* **Mecanismos de pesquisa**: o referenciador veio de um mecanismo de pesquisa reconhecido que inclui uma sequência de consulta de palavra-chave.
* **Ferramentas de IA de conversa**: o referenciador veio de uma ferramenta de IA de conversa reconhecida.
* **Redes sociais:**: os dados do referenciador pertenciam a uma rede social reconhecida pela Adobe.
* **Outros sites**: os dados do referenciador não pertenciam a um mecanismo de pesquisa ou rede social reconhecida pela Adobe.
* **Nenhum JavaScript**: o referenciador veio de um navegador que não tinha o JavaScript habilitado.
* **Disco rígido**: o referenciador é originado de uma cópia local de uma página da Web no disco rígido do visitante.
* **Email**: o referenciador é originado de um URL com um protocolo de `imap://` ou `mail://`. Não inclui serviços de email online, pois eles normalmente utilizam o protocolo `https://`.

### Ferramentas de IA de conversa

>[!IMPORTANT]
>
>Esse valor inclui somente visitas que têm um referenciador da lista a seguir. Algumas ferramentas de IA de conversação, como o ChatGPT, não enviam um referenciador quando abrem links, portanto, suas visitas não são incluídas. Para obter mais informações, consulte [Incluir o tráfego de IA que não tem referenciador](#include-ai-traffic-that-has-no-referrer).

A lista a seguir faz referência à tabela de pesquisa &quot;Ferramentas de IA de conversa&quot; que o Adobe usa. A Adobe oferece essa lista como cortesia para os clientes do Adobe Analytics. Se você quiser que a Adobe adicione um domínio a esta lista, peça para um representante de suporte da sua organização entrar em contato com o Atendimento ao cliente.

* `https://chatgpt.com`
* `https://chat.com`
* `https://chat.deepseek.com`
* `https://chat.openai.com`
* `https://doubao.com`
* `https://duck.ai`
* `https://gemini.google.com`
* `https://copilot.microsoft.com`
* `https://m365.cloud.microsoft`
* `https://perplexity.ai`
* `https://labs.perplexity.ai`
* `https://playground.perplexity.ai`
* `https://claude.ai`
* `https://grok.com`
* `https://komo.ai`
* `https://phind.com`
* `https://poe.com`
* `https://blackbox.ai`
* `https://chat.mistral.ai`
* `https://meta.ai`
* `https://you.com`

#### Incluir tráfego de IA que não tenha referenciador

Algumas ferramentas de IA de conversação, incluindo o ChatGPT, abrem links sem enviar um referenciador. O Adobe relata essas visitas em &quot;Digitado/Marcado&quot; em vez de &quot;Ferramentas de IA de conversa&quot;. As ferramentas de IA podem alterar a forma como abrem links a qualquer momento. Se o tráfego das &quot;Ferramentas de IA de conversa&quot; cair, uma ferramenta pode ter parado de enviar um referenciador. A queda não significa que o Adobe Analytics perdeu dados.

Em vez de um referenciador, algumas dessas ferramentas adicionam um parâmetro de sequência de consulta UTM aos links que abrem, como `utm_source=chatgpt.com` ou `utm_source=perplexity`. Para obter uma contagem mais completa do tráfego de ferramentas de IA de conversação, use o parâmetro UTM junto com o valor &quot;Ferramentas de IA de conversação&quot;:

* **Capture o parâmetro UTM em uma variável**: defina uma eVar com o valor `utm_source` da URL da página de aterrissagem. Use o plug-in [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md), os recursos de parâmetro de URL na extensão do Web SDK ou do Adobe Analytics ou uma [regra de processamento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-use-cases.md) que leia o parâmetro da cadeia de caracteres de consulta.
* **Criar um canal de marketing para ferramentas de IA**: criar uma [Regra de processamento de canal de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md) que corresponda se qualquer uma de suas condições for verdadeira. Adicione a condição **[!UICONTROL Referenciador é IA de Conversação]** e uma condição **[!UICONTROL Parâmetro da Cadeia de Caracteres de Consulta]** `utm_source` para cada valor que as ferramentas de IA usam, como `chatgpt.com` ou `perplexity`.
* **Criar um segmento**: crie um [segmento](/help/components/segmentation/seg-overview.md) que corresponda a &quot;Tipo de referenciador&quot; que seja igual a &quot;Ferramentas de IA de conversação&quot; ou que seu UTM eVar contenha um valor que as ferramentas de IA usam. Como a dimensão [URL da página](page-url.md) inclui cadeias de caracteres de consulta, você também pode fazer a correspondência com a URL da página que contém `utm_source=chatgpt.com`. Essa opção funciona sem alterações de implementação.

Algumas ferramentas de IA não enviam um referenciador nem um parâmetro UTM. Você não pode identificar o tráfego dessas ferramentas como tráfego de IA.

### Redes sociais

A lista a seguir faz referência à tabela de pesquisa &quot;Redes sociais&quot; que a Adobe utiliza. A Adobe oferece essa lista como cortesia para os clientes do Adobe Analytics. Se você quiser que a Adobe adicione um domínio a esta lista, peça para um representante de suporte da sua organização entrar em contato com o Atendimento ao cliente.

>[!NOTE]
>
>Essa lista é diferente da lista padrão de redes sociais nas [Regras de processamento de canal de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md).

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
* `bsky.app`
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
* `go.bsky.app`
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
* `likeshop.me`
* `linkedin.com`
* `linkin.bio`
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
* `threads.com`
* `threads.net`
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
* `web-cdn.bsky.app`
* `weibo.com`
* `weourfamily.com`
* `wer-kennt-wen.de`
* `wordpress.com`
* `x.com`
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
