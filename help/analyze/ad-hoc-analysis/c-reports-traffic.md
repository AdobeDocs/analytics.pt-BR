---
description: Os relatórios de fontes de tráfego fornecem um insight detalhado sobre como os visitantes interagem com o site da Web.
seo-description: Os relatórios de fontes de tráfego fornecem um insight detalhado sobre como os visitantes interagem com o site da Web.
seo-title: Relatórios de fontes de tráfego
solution: Analytics
title: Relatórios de fontes de tráfego
topic: Ad Hoc Analysis
uuid: 246afbdc-9f7b-4956-a44a-b7aad948f392
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Relatórios de fontes de tráfego

Os relatórios de fontes de tráfego fornecem um insight detalhado sobre como os visitantes interagem com o site da Web.

## Relatórios de fontes de tráfego {#concept_0F1772141E1345C5BCF63BE7C544C0CB}

Os relatórios de fontes de tráfego fornecem um insight detalhado sobre como os visitantes interagem com o site da Web.

Os relatórios de fontes de tráfego permitem:

* Analisar os aspectos essenciais do comportamento dos visitantes.
* Monitorar e entender os padrões de tráfego.
* Identificar o conteúdo mais popular do site.
* Segmentar os visitantes por qualquer critério mensurável.

**Persistência comum**

Em [!UICONTROL Fontes de tráfego], todos os valores do relatório persistem e recebem crédito até que sejam substituídos ou que a visita termine, o que ocorrer primeiro. Anteriormente, somente palavras-chave e domínios referenciadores persistiam. Por exemplo, se um visitante realizar uma pesquisa no Google por   "DVD," que os trás até seu site para uma compra de $100, o relatório aloca um crédito de $100 para a palavra-chave "DVD" e também para o mecanismo de pesquisa do Google. This functionality is unalterable, regardless of [!DNL Admin Console] settings.

## Palavras-chave de pesquisa {#concept_071FDCBD0A3B4242BA00744786D1C59C}

Exibe uma análise das palavras-chaves de pesquisas dos tipos Todas, Pagas e Naturais.

<!-- 

c_reports_search_keyword.xml

 -->

**[!UICONTROL Palavras-chave de pesquisa - Todas]**: mostra o detalhamento de cada palavra-chave de pesquisa usada para encontrar o site. É possível classificar esta lista por exibições da página ou palavras-chave de pesquisa, clicando no título da coluna acima da listagem. Clique na lente de aumento ao lado de uma palavra-chave de busca para ver os resultados da pesquisa para o site.

**[!UICONTROL Palavras-chave de pesquisa - Pagas]**: mostra o detalhamento de cada palavra-chave de pesquisa paga usada para encontrar o site. É possível classificar esta lista por exibições da página ou palavras-chave de pesquisa, clicando no título da coluna acima da listagem. Clique na lente de aumento ao lado de uma palavra-chave de busca para ver os resultados da pesquisa para o site.

**[!UICONTROL Palavras-chave de pesquisa - Naturais]**: mostra o detalhamento de cada palavra-chave de pesquisa usada para encontrar o site. É possível classificar esta lista por exibições da página ou palavras-chave de pesquisa, clicando no título da coluna acima da listagem. Clique na lente de aumento ao lado de uma palavra-chave de busca para ver os resultados da pesquisa para o site.

## Mecanismos de pesquisa {#concept_351CDE4F5FC44371B6B657064E125134}

Exibe quais mecanismos de pesquisa são usados pelos visitantes para pesquisas dos tipos Todas, Pagas e Naturais.

<!-- 

c_reports_search_engines.xml

 -->

**[!UICONTROL Mecanismos de pesquisa - Todos]**: mostra quais mecanismos de pesquisa as pessoas estão usando para localizar sua página da Web. O gráfico mostra o detalhamento da porcentagem dos mecanismos de pesquisa usados para localizar o site.

**[!UICONTROL Mecanismos de pesquisa - Pagos]**: mostra quais mecanismos de pesquisa as pessoas estão usando para localizar sua página da Web. O gráfico mostra o detalhamento da porcentagem dos mecanismos de pesquisa usados para localizar o site.

**[!UICONTROL Mecanismos de pesquisa - Naturais]**: mostra quais mecanismos de pesquisa as pessoas estão usando para localizar sua página da Web. O gráfico mostra o detalhamento da porcentagem dos mecanismos de pesquisa usados para localizar o site.

## Domínios de referência {#concept_804614DF21C14C9FB542451B30F92788}

<!-- 

c_reports_ref_domains.xml

 -->

Mostra os domínios que indicaram os clientes que mais tiveram impacto nas métricas de sucesso do site. Os referenciadores são divididos em duas categorias principais: Domínios e URLs. Domínios referem-se ao nome do domínio e aparecem como o domínio base, sem a sequência de consulta nem subdiretórios anexados. URLs incluem o nome de domínio base, bem como qualquer sequência de consulta ou subdiretórios.

## Domínios de referência originais {#concept_EB18251DF70343169B46BB59543A579A}

<!-- 

c_reports_original_ref_domains.xml

 -->

Exibe os referenciadores originais que geraram clientes para o seu site. Os clientes podem visitar seu site várias vezes e ter um referenciador diferente para cada visita. Este relatório mostra como eles foram encaminhados na primeira vez que chegaram ao seu site. Isso pode ajudá-lo a saber se eles continuaram a usar o mesmo referenciador e visualizar os padrões de como os clientes são referenciados ao seu site. É possível ver o número de visitantes gerados por um referenciador original ou descobrir o valor da receita que cada referenciador original gerou. Os Relatórios de referenciadores podem ser preenchidos a cada vez que um visitante chega ao site, mesmo que o visitante acesse o local diversas vezes durante uma sessão (antes da visita expirar).

## Referenciadores {#concept_40CF9C2D10B94E82819BC65A232F05C3}

Mostra o domínio ou URL de onde os visitantes vieram antes de chegarem ao site, os métodos utilizados para encontrar site e o número de visitas ao site que vieram desses locais de referência.

<!-- 

c_reports_referrers.xml

 -->

Por exemplo, se um visitante clica em um link do Site A e chega do site, Site A é o referenciador se não for definido como parte de seu domínio. Durante a implementação de relatórios e análises de marketing, o seu consultor de implementação pode ajudá-lo a definir os domínios e os URLs que fazem parte do site. (Essa alteração pode ser feita após a implementação.)

Os domínios ou URLs que não façam parte desses domínios e URLs definidos são considerados referenciadores. Por exemplo, se a página da Web A e a página da Web B são adicionadas ao filtro interno de URL, mas a página da Web C não é. Nesse caso, a página da Web C é considerada um referenciador.

Consulte [Filtros internos de URL](https://marketing.adobe.com/resources/help/en_US/reference/internal_URL_filter_admin.html) na ajuda do [!DNL Admin Console] para obter mais informações.

>[!NOTE]
>
>Marketing reports and analytics records a referring domain as an email when visitors click an emailed message link containing the protocol [!DNL imap://] or [!DNL mail://] and arrive at your site. Por exemplo, qualquer item vindo de [!DNL https://mail.yahoo.com] não é contado como um referenciador de email porque o protocolo é [!DNL https://]. Emails do Outlook são indicados na linha Digitado/Marcado, enquanto qualquer referenciador com um protocolo HTTP, onde o domínio é um mecanismo de pesquisa conhecido, é indicado na linha Mecanismo de pesquisa.

## Tipo de referenciador {#concept_689E42D8F96C450DA41C7167C7388198}

Ao monitorar e registrar os sites de referência dos visitantes para cada visita, você pode determinar como os visitantes descobriram o site em cada visita.

<!-- 

c_reports_ref_types.xml

 -->

A lista abaixo define os diversos tipos de referenciadores:

* *Referenciadores de outros sites* são registrados quando os visitantes clicam em um link localizado em uma página em outro site (não definida como parte do site) e chegam ao site.
* *Referenciadores do Mecanismo de pesquisa* são registrados quando os visitantes usam um mecanismo de pesquisa para acessar site.
* As referências *Digitadas/Adicionadas como favorito* são gravadas

   * Se um visitante entrar no site usando um link sem navegador (por exemplo, em um email).
   * Se um visitante digitar o URL do site diretamente no navegador.
   * Se um visitante clicar em um link HTML no disco rígido pessoal.
   * Se um visitante acessar o site, selecionando os marcadores do navegador.

**Definições**

Os itens da linha a seguir podem ser exibidos ao executar este relatório:

**No seu site**: Estes itens são URLs marcadas pelos filtros internos do URL. Esses itens não são contados como   mas podem ser visualizados quando relatados em outras métricas.

** Sem Java Script**: Não havia JavaScript, portanto, o tipo não era identificável (desconhecido). Isso significa que não haviam informações do referenciador fornecidas por um cliente em um navegador, o qual não informa ser compatível com JavaScript. Isso não é contado como "instâncias do referenciador", mas pode ser visualizado quando relatado em outras medidas.

**USENET (grupo de notícias)**: Isso significa que o URL para o referenciador começava com `news://`. Como tal, o link do referenciador foi postado em um grupo de notícias do Usenet em vez de na página da Web.

>[!NOTE]
>
>Referrer Type logic matches other traffic sources reports (such as [!UICONTROL Referrers] and [!UICONTROL Referring Domains]). Isso deve reduzir ou eliminar as ocorrências dos itens de linha Dentro do seu site e Sem JavaScript no relatório de [!UICONTROL Tipo do Referenciador].

