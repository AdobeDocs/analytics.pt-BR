---
title: Domínio de referência
description: O domínio abrangente no qual um visitante estava ativado antes de clicar até o site.
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 5%

---


# Domínio de referência

A dimensão &#39;Domínio de referência&#39; relata quais domínios os visitantes clicam para chegar ao site. Essa dimensão é útil para entender quais sites de terceiros direcionam mais tráfego para o seu. Um link deve existir no site externo e um visitante deve clicar nele para que o item de dimensão seja exibido.

>[!IMPORTANT]
>
>Você deve configurar os filtros [de URL](/help/admin/admin/internal-url-filter-admin.md) internos do conjunto de relatórios para usar essa dimensão. A falha ao configurar filtros internos de URL pode incluir domínios internos ou impedir que domínios externos apareçam.

O mesmo relatório pode mostrar resultados diferentes entre Analysis Workspace e Data warehouse. Analysis Workspace relata o domínio de referência para cada página individual, excluindo valores que correspondem a filtros internos de URL. A Data warehouse relata somente o primeiro domínio de referência da visita e ignora filtros internos de URL.

## Preencher esta dimensão com dados

Essa dimensão requer configuração na interface do Analytics e dados em solicitações de imagem.

* Em sua implementação, essa dimensão recupera dados da sequência de caracteres [`r` do](/help/implement/validate/query-parameters.md) query em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `document.referrer` no navegador. Se você usar uma biblioteca do AppMeasurement (por exemplo, pelo Adobe Experience Platform Launch), essa dimensão funcionará imediatamente. Se você usar um método de coleta de dados fora do AppMeasurement (por exemplo, por meio da API), certifique-se de incluir o parâmetro da string de `r` query em solicitações de imagem.
* Na interface do Analytics, você deve configurar os filtros [de URL](/help/admin/admin/internal-url-filter-admin.md)internos do conjunto de relatórios. A falha ao configurar filtros internos de URL pode incluir domínios internos ou impedir que domínios externos apareçam.

Adobe persiste no domínio de referência para uma visita. Se um visitante sair e clicar em um link em um domínio diferente em uma única visita, o novo valor será atualizado e persistirá pelo restante da visita. Se quiser ver apenas o valor original, consulte Domínio [de referência](original-referring-domain.md)original.

## itens de Dimension

Os itens de Dimension incluem domínios que os visitantes clicam até o site. Se uma ocorrência não tiver dados de quem indicou (definidos ou persistentes), ela será agrupada no item de dimensão `"Typed/Bookmarked"`. Esse item de dimensão significa que não havia valor de quem indicou, como se o visitante digitasse manualmente o endereço do navegador na barra de endereços, ou clicasse em um marcador.

### itens Dimension que contenham `googleusercontent.com`

Os usuários podem ver itens de dimensão com o domínio `googleusercontent.com`.

* **Páginas** em cache: As aranhas do Google rastreiam constantemente a web e armazenam cópias de páginas caso elas sejam tiradas offline. Essas páginas em cache estão disponíveis ao lado da maioria dos resultados da pesquisa clicando no link &quot;Em cache&quot;. Quando um usuário clica nesse link e visualização o conteúdo que o Google armazena em cache, `googleusercontent.com` é o item de dimensão.
* **Páginas traduzidas**: o Google oferece um serviço de tradução robusto e prático. Ao visualizar um site usando este serviço, ele é originário do `googleusercontent.com`. Esse item de dimensão será exibido se o usuário clicar em um link para retornar ao conteúdo original.
