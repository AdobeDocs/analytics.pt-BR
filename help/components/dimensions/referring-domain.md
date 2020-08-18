---
title: Domínio de referência
description: O domínio global no qual um visitante estava antes de clicar para acessar o site.
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 53%

---


# Domínio de referência

A dimensão “Domínio de referência” informa em quais domínios os visitantes clicam para acessar seu site. Essa dimensão é útil para entender quais sites de terceiros direcionam mais tráfego para o seu site. Um link deve existir no site externo e um visitante deve clicar nele para que o item de dimensão seja exibido.

>[!IMPORTANT]
>
>Você deve configurar os [Filtros de URL internos](/help/admin/admin/internal-url-filter-admin.md) do conjunto de relatórios para utilizar essa dimensão. Falhas ao configurar filtros de URL internos podem incluir domínios internos e impedir que domínios externos apareçam.

O mesmo relatório pode mostrar resultados diferentes entre o Analysis Workspace e a Data Warehouse. A Analysis Workspace relata o domínio de referência para cada página individual, excluindo valores que correspondem a filtros internos de URL. A Data Warehouse relata somente o primeiro domínio de referência da visita e ignora filtros internos de URL.

## Preencher esta dimensão com dados

Essa dimensão precisa ser configurada na interface do Analytics e os dados em solicitações de imagem.

* Em sua implementação, essa dimensão recupera dados da [`r` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `document.referrer` no navegador. Se você utilizar uma biblioteca do AppMeasurement (por meio do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente. Se um método de coleta de dados diferente do AppMeasurement for utilizado (por meio da API), inclua o parâmetro da sequência de consulta `r` em solicitações de imagem.
* Na interface do Analytics, é necessário configurar os [Filtros de URL internos](/help/admin/admin/internal-url-filter-admin.md) do conjunto de relatórios. Falhas ao configurar filtros de URL internos podem incluir domínios internos e impedir que domínios externos apareçam.

A Adobe mantém o domínio referenciador para uma visita. Se um visitante sair e clicar em um link para acessar o site por um domínio diferente em uma única visita, o novo valor será atualizado e persistirá no restante da visita. Se desejar ver apenas o valor original, consulte [Domínio de Referência Original](original-referring-domain.md).

## itens de Dimension

Os itens de Dimension incluem domínios que os visitantes clicam até o site. If a hit does not have any referrer data (either set or persisted), it groups under the dimension item `"Typed/Bookmarked"`. Esse item de dimensão significa que não havia valor de quem indicou, como se o visitante digitasse manualmente o endereço do navegador na barra de endereços, ou clicasse em um marcador. O item de `"Typed/Bookmarked"` dimensão também aparece para redirecionamentos que não acomodam o Analytics. Consulte [Redirecionamentos e aliases](/help/technotes/redirects.md) no guia do usuário do Technotes.

### itens Dimension que contenham `googleusercontent.com`

Os usuários podem ver itens de dimensão com o domínio `googleusercontent.com`.

* **Páginas** em cache: As aranhas do Google rastreiam constantemente a web e armazenam cópias de páginas caso elas sejam tiradas offline. Essas páginas em cache estão disponíveis ao lado da maioria dos resultados da pesquisa clicando no link &quot;Em cache&quot;. Quando um usuário clica nesse link e visualização o conteúdo que o Google armazena em cache, `googleusercontent.com` é o item de dimensão.
* **Páginas traduzidas**: o Google oferece um serviço de tradução robusto e prático. Ao visualizar um site usando este serviço, ele é originário do `googleusercontent.com`. Esse item de dimensão será exibido se o usuário clicar em um link para retornar ao conteúdo original.
