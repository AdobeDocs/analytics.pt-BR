---
title: Referenciador
description: O URL no qual um visitante estava antes de clicar até o site.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 0%

---


# Referenciador

A dimensão &quot;Quem indicou&quot; relata quais URLs os visitantes estavam ativados ao clicar para acessar seu site. Essa dimensão é útil para entender quais URLs específicos direcionam mais tráfego para o site. Um link deve existir no URL externo e um visitante deve clicar nele para que o item de dimensão seja exibido.

>[!IMPORTANT]
>
>Você deve configurar os filtros [de URL](/help/admin/admin/internal-url-filter-admin.md) internos do conjunto de relatórios para usar essa dimensão. A falha ao configurar filtros internos de URL pode incluir URLs internos ou impedir que URLs externos apareçam.

## Preencher esta dimensão com dados

Essa dimensão requer configuração na interface do Analytics e dados em solicitações de imagem.

* Em sua implementação, essa dimensão recupera dados da sequência de caracteres [`r` do](/help/implement/validate/query-parameters.md) query em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `document.referrer` no navegador. Se você usar uma biblioteca do AppMeasurement (por exemplo, por meio do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente. Se você usar um método de coleta de dados fora do AppMeasurement (por exemplo, por meio da API), certifique-se de incluir o parâmetro da string de `r` query em solicitações de imagem.
* Na interface do Analytics, você deve configurar os filtros [de URL](/help/admin/admin/internal-url-filter-admin.md)internos do conjunto de relatórios. A falha ao configurar filtros internos de URL pode incluir URLs internos ou impedir que URLs externos apareçam.

## Itens de dimensão

Os itens de dimensão incluem URLs nos quais os visitantes clicam até o site. Se uma ocorrência não tiver dados de quem indicou, ela será agrupada no item de dimensão `"Typed/Bookmarked"`. Esse item de dimensão significa que não havia valor de quem indicou, como se o visitante digitasse manualmente o endereço do navegador na barra de endereços, ou clicasse em um marcador.
