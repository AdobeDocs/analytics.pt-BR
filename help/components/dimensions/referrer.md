---
title: Referenciador
description: O URL no qual um visitante estava antes de clicar até o site.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 0%

---


# Referenciador

A dimensão &quot;Quem indicou&quot; relata quais URLs os visitantes estavam ativados ao clicar para acessar seu site. Essa dimensão é útil para entender quais URLs específicos direcionam mais tráfego para o site. Um link deve existir no URL externo e um visitante deve clicar nele para que o valor da dimensão seja exibido.

>[!IMPORTANT]
>
>Você deve configurar os filtros [de URL](/help/admin/admin/internal-url-filter-admin.md) internos do conjunto de relatórios para usar essa dimensão. A falha ao configurar filtros internos de URL pode incluir URLs internos ou impedir que URLs externos apareçam.

## Preencher esta dimensão com dados

Essa dimensão requer configuração na interface do Analytics e dados em solicitações de imagem.

* Em sua implementação, essa dimensão recupera dados da sequência de caracteres [`r` do](/help/implement/validate/query-parameters.md) query em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `document.referrer` no navegador. Se você usar uma biblioteca do AppMeasurement (por exemplo, por meio do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente. Se você usar um método de coleta de dados fora do AppMeasurement (por exemplo, por meio da API), certifique-se de incluir o parâmetro da string de `r` query em solicitações de imagem.
* Na interface do Analytics, você deve configurar os filtros [de URL](/help/admin/admin/internal-url-filter-admin.md)internos do conjunto de relatórios. A falha ao configurar filtros internos de URL pode incluir URLs internos ou impedir que URLs externos apareçam.

## Valores de dimensão

Os valores de dimensão incluem URLs nos quais os visitantes clicam até o site. Se uma ocorrência não tiver dados quens indicou, ela será agrupada sob o valor da dimensão `"Typed/Bookmarked"`. Esse valor de dimensão significa que não havia valor de quem indicou, como se o visitante digitasse manualmente o endereço do navegador na barra de endereços, ou clicasse em um marcador.
