---
title: Referenciador
description: O URL no qual um visitante estava antes de clicar para acessar seu site.
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 49%

---


# Referenciador

A dimensão &quot;Referenciador&quot; informa em quais URLs os visitantes estavam quando clicaram para acessar seu site. Essa dimensão é útil para entender quais URLs específicos direcionam mais tráfego para o site. Um link deve existir no URL externo e um visitante deve clicar nele para que o item de dimensão seja exibido.

>[!IMPORTANT]
>
>Você deve configurar os [filtros de URL internos](/help/admin/admin/internal-url-filter-admin.md) do conjunto de relatórios para utilizar essa dimensão. Falhas ao configurar filtros de URL internos podem incluir URLs internos ou impedir que URLs externos apareçam.

O mesmo relatório pode mostrar resultados diferentes entre o Analysis Workspace e a Data Warehouse. A Analysis Workspace relata a quem indicou de cada página individual, excluindo valores que correspondem a filtros internos de URL. A Data Warehouse relata somente a primeira quem indicou da visita e ignora filtros internos de URL.

## Preencher esta dimensão com dados

Essa dimensão precisa ser configurada na interface do Analytics e os dados em solicitações de imagem.

* Em sua implementação, essa dimensão recupera dados da [`r` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `document.referrer` no navegador. Se você utilizar uma biblioteca do AppMeasurement (por meio do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente. Se um método de coleta de dados diferente do AppMeasurement for utilizado (por meio da API), inclua o parâmetro da sequência de consulta `r` em solicitações de imagem.
* Na interface do Analytics, é necessário configurar os [Filtros de URL internos](/help/admin/admin/internal-url-filter-admin.md) do conjunto de relatórios. Falhas ao configurar filtros de URL internos podem incluir URLs internos ou impedir que URLs externos apareçam.

## itens de Dimension

Os itens de Dimension incluem URLs nos quais os visitantes clicam até o site. If a hit does not have any referrer data, it groups under the dimension item `"Typed/Bookmarked"`. Esse item de dimensão significa que não havia valor de quem indicou, como se o visitante digitasse manualmente o endereço do navegador na barra de endereços, ou clicasse em um marcador. O item de `"Typed/Bookmarked"` dimensão também aparece para redirecionamentos que não acomodam o Analytics. Consulte [Redirecionamentos e aliases](/help/technotes/redirects.md) no guia do usuário do Technotes.

### itens Dimension que contenham `googleusercontent.com`

Os usuários podem ver itens de dimensão com o domínio `googleusercontent.com`.

* **Páginas** em cache: As aranhas do Google rastreiam constantemente a web e armazenam cópias de páginas caso elas sejam tiradas offline. Essas páginas em cache estão disponíveis ao lado da maioria dos resultados da pesquisa clicando no link &quot;Em cache&quot;. Quando um usuário clica nesse link e visualização o conteúdo que o Google armazena em cache, `webcache.googleusercontent.com` é um item de dimensão típico.
* **Páginas traduzidas**: o Google oferece um serviço de tradução robusto e prático. Ao visualizar um site usando este serviço, ele é originário do `translate.googleusercontent.com`. Esse item de dimensão será exibido se o usuário clicar em um link para retornar ao conteúdo original.
