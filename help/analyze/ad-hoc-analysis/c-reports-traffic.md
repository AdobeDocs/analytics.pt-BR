---
description: Os relatórios de fontes de tráfego fornecem um insight detalhado sobre como os visitantes interagem com o site da Web.
title: Relatórios de fontes de tráfego
topic: Ad hoc analysis
uuid: 246afbdc-9f7b-4956-a44a-b7aad948f392
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Relatórios de fontes de tráfego

Os relatórios de fontes de tráfego fornecem um insight detalhado sobre como os visitantes interagem com o site da Web.

## Relatórios de fontes de tráfego {#concept_0F1772141E1345C5BCF63BE7C544C0CB}

Os relatórios de fontes de tráfego fornecem um insight detalhado sobre como os visitantes interagem com o site da Web.

Os relatórios de fontes de tráfego permitem:

* Analise os aspectos críticos do comportamento do visitante.
* Monitore e entenda os padrões de tráfego.
* Determine o conteúdo popular do site.
* Segmentar visitantes por qualquer critério mensurável.

**Persistência comum**

Em [!UICONTROL Traffic Sources], todos os valores do relatório persistem e recebem crédito até que sejam substituídos ou até que a visita termine, o que ocorrer primeiro. Anteriormente, somente palavras-chave e domínios referenciadores persistiam. Por exemplo, se um visitante realizar uma pesquisa no Google por    &quot;DVD&quot;, que os traz ao seu site para uma compra de $100, o relatório aloca um crédito de $100 para a palavra-chave &quot;DVD&quot; e também para o mecanismo de pesquisa do Google. Essa funcionalidade é inalterável, independentemente das configurações do [!DNL Admin Console].

## Palavras-chave de pesquisa {#concept_071FDCBD0A3B4242BA00744786D1C59C}

Exibe um detalhamento de palavras-chave para pesquisas Todas, Pagas e Naturais.

<!-- 

c_reports_search_keyword.xml

 -->

**[!UICONTROL Search Keywords - All]**: Exibe um detalhamento de cada palavra-chave de pesquisa usada para encontrar o site. É possível classificar essa lista por visualizações de página ou palavras-chave de pesquisa clicando no título da coluna acima da listagem. Clique na lente de aumento ao lado de uma palavra-chave de pesquisa para ver os resultados da pesquisa do site.

**[!UICONTROL Search Keywords - Paid]**: Exibe um detalhamento de cada palavra-chave de pesquisa paga usada para encontrar o site. É possível classificar essa lista por visualizações de página ou palavras-chave de pesquisa clicando no título da coluna acima da listagem. Clique na lente de aumento ao lado de uma palavra-chave de pesquisa para ver os resultados da pesquisa do site.

**[!UICONTROL Search Keywords - Natural]**: Exibe um detalhamento de cada palavra-chave de pesquisa natural usada para encontrar o site. É possível classificar essa lista por visualizações de página ou palavras-chave de pesquisa clicando no título da coluna acima da listagem. Clique na lente de aumento ao lado de uma palavra-chave de pesquisa para ver os resultados da pesquisa do site.

## Mecanismos de pesquisa {#concept_351CDE4F5FC44371B6B657064E125134}

Exibe quais mecanismos de pesquisa os visitantes usam para pesquisas Todas, Pagas e Naturais.

<!-- 

c_reports_search_engines.xml

 -->

**[!UICONTROL Search Engines - All]**: Exibe quais mecanismos de pesquisa as pessoas estão usando para localizar sua página da Web. O gráfico mostra o detalhamento da porcentagem dos mecanismos de pesquisa usados para localizar o site.

**[!UICONTROL Search Engines - Paid]**: Exibe quais mecanismos de pesquisa as pessoas estão usando para localizar sua página da Web. O gráfico mostra o detalhamento da porcentagem dos mecanismos de pesquisa usados para localizar o site.

**[!UICONTROL Search Engines - Natural]**: Exibe quais mecanismos de pesquisa as pessoas estão usando para localizar sua página da Web. O gráfico mostra o detalhamento da porcentagem dos mecanismos de pesquisa usados para localizar o site.

## Domínios de referência {#concept_804614DF21C14C9FB542451B30F92788}

<!-- 

c_reports_ref_domains.xml

 -->

Mostra os domínios que indicaram os clientes que mais tiveram impacto nas métricas de sucesso do site. Quens indicou se dividem em duas categorias principais: Domínios e URLs. Os domínios se referem ao nome do domínio e são exibidos como o domínio base sem a sequência de caracteres do query ou os subdiretórios anexados. Os URLs incluem o nome de domínio base, bem como qualquer sequência de caracteres ou subdiretórios de query.

## Domínios de referência originais  {#concept_EB18251DF70343169B46BB59543A579A}

<!-- 

c_reports_original_ref_domains.xml

 -->

Exibe as quens indicou originais que produziram os clientes em seu site. Os clientes podem visitar seu site várias vezes e ter uma quem indicou diferente para cada visita. Este relatório mostra como eles foram referenciados na primeira vez que chegaram ao site. Isso pode ajudá-lo a ver se eles continuaram a usar a mesma quem indicou e os mesmos padrões de visualização em como os clientes são referenciados ao seu site. Você pode visualização o número de visitantes gerados por uma quem indicou original ou descobrir a receita que cada quem indicou original gerou. Os Relatórios de referenciadores podem ser preenchidos a cada vez que um visitante chega ao site, mesmo que o visitante acesso o local diversas vezes durante uma sessão (antes da visita expirar.)

## Referenciadores {#concept_40CF9C2D10B94E82819BC65A232F05C3}

Exibe o domínio ou URL de onde os visitantes vieram antes de chegarem ao site, os métodos que os visitantes usam para localizar seu site e o número de visitas ao site que vieram desses locais de referência.

<!-- 

c_reports_referrers.xml

 -->

Por exemplo, se um visitante clicar em um link do Site A e chegar ao seu site, o Site A será a quem indicou se não for definida como parte do seu domínio. Durante a implementação de relatórios e análises de marketing, seu consultor de implementação pode ajudá-lo a definir os domínios e URLs que fazem parte do seu site. (Essa alteração pode ser feita após a implementação.)

Domínios ou URLs que não fazem parte desses domínios e URLs definidos são considerados quens indicou. Por exemplo, as páginas A e B da Web são adicionadas ao filtro interno de URL, mas a página C não é. Nesse caso, a página C é considerada uma quem indicou.

Consulte [Filtros internos de URL](https://marketing.adobe.com/resources/help/pt_BR/reference/internal_URL_filter_admin.html) na ajuda do [!DNL Admin Console] para obter mais informações.

>[!NOTE] Os relatórios e análises de marketing registram um domínio de referência como um email quando visitantes clicam em um link de mensagem enviado por email contendo o protocolo [!DNL imap://] ou [!DNL mail://] e chegam em seu site. Por exemplo, qualquer item vindo de [!DNL https://mail.yahoo.com] não é contado como um referenciador de email porque o protocolo é [!DNL https://]. Emails do Outlook são indicados na linha Digitado/Marcado, enquanto qualquer referenciador com um protocolo HTTP, onde o domínio é um mecanismo de pesquisa conhecido, é indicado na linha Mecanismo de pesquisa.

## Tipo de referenciador {#concept_689E42D8F96C450DA41C7167C7388198}

Ao rastrear e registrar os sites de referência dos visitantes para cada visita, você pode determinar como os visitantes descobriram o site em cada visita.

<!-- 

c_reports_ref_types.xml

 -->

A lista abaixo define os vários tipos de quens indicou:

* *Outras quens indicou* do site são gravadas quando visitantes clicam em um link localizado em uma página em outro site (não definido como parte do site) e chegam ao seu site.
* *As quens indicou do mecanismo* de pesquisa são registradas quando os visitantes usam um mecanismo de pesquisa para acessar seu site.
* *quens indicou Digitadas/Marcadas* são gravadas

   * Se um visitante entrar em seu site por meio de um link que não seja do navegador (por exemplo, em um email).
   * Se um visitante digitar o URL do site diretamente no navegador.
   * Se um visitante clicar em um link HTML no disco rígido pessoal.
   * Se um visitante acessar seu site selecionando marcadores do navegador.

**Definições**

Os seguintes itens de linha podem ser exibidos ao executar este relatório:

**No seu site**: Estes itens são URLs marcadas pelos filtros internos do URL. Esses itens não são contados como instâncias do referenciador, mas podem ser visualizados quando relatados em outras medidas.

**Sem Java Script**: Não havia JavaScript, portanto, o tipo não era identificável (desconhecido). Isso significa que não haviam informações do referenciador fornecidas por um cliente em um navegador, o qual não informa ser compatível com JavaScript. Elas não são contadas como &quot;instâncias de quem indicou&quot;, mas podem ser visualizadas ao relatórios de outras métricas.

**USENET (grupo de notícias)**: Isso significa que o URL para o referenciador começava com `news://`. Como tal, o link do referenciador foi postado em um grupo de notícias do Usenet em vez de na página da Web.

>[!NOTE] A lógica do Tipo de Quem indicou corresponde a outros relatórios de fontes de tráfego (como [!UICONTROL Referrers] e [!UICONTROL Referring Domains]). This should reduce or eliminate the occurrences of the Inside Your Site and No JavaScript line items in the [!UICONTROL Referrer Type] report.

