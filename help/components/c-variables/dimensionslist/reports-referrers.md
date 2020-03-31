---
title: Referenciadores
description: Mostra o URL da ocorrência anterior, se essa ocorrência estiver fora do site.
translation-type: tm+mt
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# Referenciadores

A dimensão &#39;Quem indicou&#39; mostra o URL de onde seus visitantes vieram antes de chegarem ao site. Por exemplo, se um visitante clicar em um link de `example.com/example-page.html` e chegar ao seu site, `example.com/example-page.html` será a quem indicou se não for definida como parte do seu domínio.

Essa dimensão exige que você configure os filtros [de URL](/help/admin/admin/internal-url-filter-admin.md)internos do conjunto de relatórios. Se você não configurar filtros internos de URL, o Adobe Analytics considerará todos os domínios como internos do site.

## Propriedades da dimensão

* Essa dimensão usa a alocação mais recente por padrão.
* Essa dimensão expira após a visita por padrão.
* Essa dimensão está sujeita ao limite exclusivo de 500k antes de agrupar valores de dimensão em (tráfego baixo). O Data Warehouse não tem um limite exclusivo.
* Se não houver um valor de quem indicou para uma métrica, ele será agrupado em `Typed/Bookmarked`.
* Normalmente, essa dimensão é definida na primeira ocorrência da visita, mas pode ser definida como meia visita.

## Solução de problemas

**P: Por que vejo`googleusercontent.com`como um valor de dimensão?**

A: O [Google](https://about.google/) usa o domínio `googleusercontent.com` para seu conteúdo hospedado. O conteúdo hospedado inclui:

* **Páginas** em cache: Os spiders do Google rastreiam constantemente a Web e salvam páginas da Web caso estejam offline ou indisponíveis. Essas páginas em cache estão disponíveis ao lado de todos os resultados da pesquisa clicando no link &quot;Em cache&quot; de uma das páginas de resultados da pesquisa do Google. Quando um usuário clica nesse link e, em seguida, verifica o conteúdo original no site, `googleusercontent.com` é listado como seu domínio de referência. Essas páginas têm o subdomínio `webcache.googleusercontent.com`.
* **Páginas** traduzidas: O Google oferta um serviço de tradução robusto e conveniente. Ao visualizar um site usando este serviço, ele é originário de `googleusercontent.com`. A dimensão de quem indicou mostra URLS desse domínio se o usuário clicar em um link para retornar ao conteúdo original. Essas páginas têm o subdomínio `translate.googleusercontent.com`.
