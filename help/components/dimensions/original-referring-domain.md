---
title: Domínio de referência original
description: O primeiro domínio de referência em que um visitante estava antes de clicar no site.
translation-type: tm+mt
source-git-commit: 7c722e361978a3d7517e95c23442b703e7e25270
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---


# Domínio de referência original

A dimensão &#39;Domínio de referência original&#39; relata o primeiro domínio de referência pelo qual um visitante clicou para chegar ao site. Depois de definido, ele contém o mesmo valor para toda a vida útil da ID do visitante. Essa dimensão é útil para entender quais sites de terceiros originalmente direcionam tráfego para o site.

>[!IMPORTANT]
>
>Você deve configurar os filtros [de URL](/help/admin/admin/internal-url-filter-admin.md) internos do conjunto de relatórios para usar essa dimensão. A falha ao configurar filtros internos de URL pode incluir domínios internos ou impedir que domínios externos apareçam.

## Preencher esta dimensão com dados

Essa dimensão requer configuração na interface do Analytics e na implementação.

* Em sua implementação, essa dimensão recupera dados da sequência de caracteres [`r` do](/help/implement/validate/query-parameters.md) query em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `document.referrer` no navegador. Se você usar uma biblioteca do AppMeasurement (por exemplo, pelo Adobe Experience Platform Launch), essa dimensão funcionará imediatamente. Se você usar um método de coleta de dados fora do AppMeasurement (por exemplo, por meio da API), certifique-se de incluir o parâmetro da string de `r` query em solicitações de imagem.
* Na interface do Analytics, você deve configurar os filtros [de URL](/help/admin/admin/internal-url-filter-admin.md)internos do conjunto de relatórios. A falha ao configurar filtros internos de URL pode incluir domínios internos ou impedir que domínios externos apareçam.

Adobe persiste no domínio de referência original para uma vida útil do visitante. Se um visitante sair e clicar em um link em um domínio diferente a qualquer momento, o novo valor não será registrado. Se quiser ver novos valores, consulte [Domínio](referring-domain.md)de referência.

## itens de Dimension

Os itens de Dimension incluem domínios que os visitantes clicam até o site. Se uma ocorrência não tiver dados de quem indicou (definidos ou persistentes), ela será agrupada no item de dimensão `"None"`. Esse item de dimensão significa que não havia valor de quem indicou, como se o visitante digitasse manualmente o endereço do navegador na barra de endereços, ou clicasse em um marcador.

## Comparar domínio de referência ao domínio de referência original

O domínio de referência pode mudar entre visitas. Por exemplo, um visitante chega ao seu site por meio do `google.com`e, em seguida, uma semana depois, chega ao seu site por meio do `twitter.com`. Eventualmente eles fazem uma compra em seu site. Se estiver usando o domínio de referência como a dimensão com atribuição de último toque, `twitter.com` obterá crédito pela compra. Se estiver usando o domínio de referência original como a dimensão, `google.com` obterá crédito pela compra independentemente do modelo de atribuição.

O domínio de referência original nunca é alterado durante toda a vida útil de uma determinada ID de visitante.
