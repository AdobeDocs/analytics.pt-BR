---
title: Domínio de referência original
description: O primeiro domínio de referência em que um visitante estava antes de clicar no site.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---


# Domínio de referência original

A dimensão &#39;Domínio de referência original&#39; relata o primeiro domínio de referência pelo qual um visitante clicou para chegar ao site. Depois de definido, ele contém o mesmo valor para toda a vida útil da ID do visitante. Essa dimensão é útil para entender quais sites de terceiros originalmente direcionam tráfego para o site.

## Preencher esta dimensão com dados

Essa dimensão requer configuração na interface do Analytics e na implementação.

* Em sua implementação, essa dimensão recupera dados da sequência de caracteres [`r` do](/help/implement/validate/query-parameters.md) query em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `document.referrer` no navegador. Se você usar uma biblioteca do AppMeasurement (por exemplo, por meio do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente. Se você usar um método de coleta de dados fora do AppMeasurement (por exemplo, por meio da API), certifique-se de incluir o parâmetro da string de `r` query em solicitações de imagem.
* Na interface do Analytics, você deve configurar os filtros [de URL](/help/admin/admin/internal-url-filter-admin.md)internos do conjunto de relatórios. A falha ao configurar filtros internos de URL pode incluir domínios internos ou impedir que domínios externos apareçam.

A Adobe persiste no domínio de referência original para uma duração de visitante. Se um visitante sair e clicar em um link em um domínio diferente a qualquer momento, o novo valor não será registrado. Se quiser ver novos valores, consulte [Domínio](referring-domain.md)de referência.

## Itens de dimensão

Os itens de dimensão incluem domínios nos quais os visitantes clicam até o site. Se uma ocorrência não tiver dados de quem indicou (definidos ou persistentes), ela será agrupada no item de dimensão `"None"`. Esse item de dimensão significa que não havia valor de quem indicou, como se o visitante digitasse manualmente o endereço do navegador na barra de endereços, ou clicasse em um marcador.
