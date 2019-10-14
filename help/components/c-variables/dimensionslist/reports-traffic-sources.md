---
description: Exibe informações sobre os locais na Web que enviaram tráfego para o seu site. Você pode ver quais mecanismos de pesquisa e sites fora do seu próprio domínio enviam visitantes para você.
seo-description: Exibe informações sobre os locais na Web que enviaram tráfego para o seu site. Você pode ver quais mecanismos de pesquisa e sites fora do seu próprio domínio enviam visitantes para você.
seo-title: Fontes de Tráfego
solution: Analytics
title: Fontes de Tráfego
topic: Relatórios
uuid: 34ab8797-7a3e-43fd-afb2-433586961b8
translation-type: tm+mt
source-git-commit: debfeb513ec40de9323485006e9ed8459f75a586

---


# Fontes de Tráfego

Exibe informações sobre os locais na Web que enviaram tráfego para o seu site. Você pode ver quais mecanismos de pesquisa e sites da Web fora do seu próprio domínio enviam visitantes para você.

## Fontes de Tráfego {#topic_6718F8EFD5984DC5839B9E8F6CC45EDA}

Exibe informações sobre os locais na Web que enviaram tráfego para o seu site. Você pode ver quais mecanismos de pesquisa e sites fora do seu próprio domínio enviam visitantes para você.

Os relatórios neste menu se dividem em três categorias básicas:

* Pesquisar por palavras-chave
* Mecanismos de pesquisa
* Referências e domínios referenciadores

### Palavras-chave de pesquisa - Todas, Pagas ou Naturais

Exibe o detalhamento de cada palavra-chave de pesquisa usada para encontrar o site. É possível classificar esta lista por exibições da página ou palavras-chave de pesquisa, clicando no título da coluna acima da listagem. Clique na lente de aumento ao lado de uma palavra-chave de busca para ver os resultados da pesquisa para o site.

### Mecanismos de pesquisa - Todos, Pagos ou Naturais

Exibe quais mecanismos de pesquisa as pessoas estão usando para localizar sua página da Web. O gráfico mostra o detalhamento da porcentagem dos mecanismos de pesquisa usados para localizar o site.

**Todas as classificações da página de pesquisa**

Exibe a classificação do seu site dentre todas as listas para buscas dos seus visitantes, incluindo dados de classificação de página de busca natural e paga.

Por exemplo, um usuário que chega ao seu site por um mecanismo de busca pode ter visto você em um terço de cem páginas de resultados. Isso pode ajudá-lo a rapidamente ver e otimizar os esforços do mecanismo de busca. Os dados para este relatório podem ser visto por todos, exceto os de hora em hora.

### Domínios de referência e referenciadores

**Domínios de referência**

Mostra os domínios que indicaram os clientes que mais tiveram impacto nas métricas de sucesso do site. Os referenciadores são divididos em duas categorias principais: Domínios e URLs. Domínios referem-se ao nome do domínio e aparecem como o domínio base, sem a sequência de consulta nem subdiretórios anexados. URLs incluem o nome de domínio base, bem como qualquer sequência de consulta ou subdiretórios.

**Domínios de referência originais**

Exibe os referenciadores originais que geraram clientes para o seu site. Os clientes podem visitar site várias vezes e ter um referenciador diferente para cada visita.

Esse relatório é útil para exibir como os visitantes foram referenciados na primeira vez que chegaram no seu site. Isso pode ajudá-lo a saber se eles continuaram a usar o mesmo referenciador e visualizar os padrões de como os clientes são referenciados ao seu site. É possível ver o número de visitantes gerados por um referenciador original ou descobrir o valor da receita que cada referenciador original gerou. Os Relatórios de referenciadores podem ser preenchidos a cada vez que um visitante chega ao seu site, mesmo que o visitante acesso o local diversas vezes durante uma sessão (antes da visita expirar.)

**Referenciadores**

Mostra o domínio ou URL de onde os visitantes vieram antes de chegarem ao site, os métodos utilizados para encontrar site e o número de visitas ao site que vieram desses locais de referência.

Por exemplo, se um visitante clica em um link do Site A e chega do site, Site A é o referenciador se não for definido como parte de seu domínio. Durante a implementação, seu consultor de implementação pode ajudá-lo a definir os domínios e URLs que fazem parte do seu site (isso também pode ser feito após a implementação.) Quaisquer domínios ou URLs que não sejam parte desses domínios e URLs definidos são considerados referenciadores.

Por exemplo, se as páginas da Web A e B são adicionadas ao filtro de URL interno, mas a página da Web C não é, a página da Web C é considerada uma referência.

See [Internal URL Filters](/help/admin/admin/internal-URL-filter-admin.md)

>[!NOTE]
>
>Analytics records a referring domain as an email when visitors click an emailed message link containing the protocol `imap://` or `mail://` and arrive at your site.
>
>For example, anything coming from  https://mail.yahoo.com</code> is not counted as an email referrer because the protocol is `https://`. Os emails do Outlook são relatados na `Typed/ Bookmarked` linha. Qualquer referenciador com um protocolo HTTP no qual o domínio é um mecanismo de pesquisa conhecido é relatado na `Search Engine` linha.

**Tipos de Referenciador**

Ao rastrear e registrar os sites de referência dos visitantes para cada visita, você pode determinar como os visitantes descobriram o site em cada visita. A lista abaixo define os diversos tipos de referenciadores.

* Referenciadores de disco rígido são registrados quando os visitantes clicam em um link em um documento HTML localizado em seu próprio disco rígido e, assim, chegam ao site.
* Referenciadores de outros sites são registrados quando os visitantes clicam em um link localizado em uma página em outro site (não definida como parte do site) e chegam ao site.
* Referenciadores de Mecanismo de pesquisa são registrados quando os visitantes usam um mecanismo de pesquisa para acessar site. * Referenciadores Digitados/Marcados são registrados quando os visitantes digitam o URL do seu site diretamente no navegador, ou se acessam seu site selecionando marcadores.
