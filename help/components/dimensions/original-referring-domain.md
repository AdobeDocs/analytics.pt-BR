---
title: Domínio referenciador original
description: O primeiro domínio referenciador no qual um visitante estava antes de clicar para acessar o site.
exl-id: 6b9ac662-a79a-477b-8612-7980da7cfadd
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '407'
ht-degree: 100%

---

# Domínio referenciador original

A dimensão “Domínio referenciador” informa o primeiro domínio referenciador em que um visitante clicou para chegar ao site. Depois de definido, ele contém o mesmo valor para toda a vida útil da ID do visitante. Essa dimensão é útil para entender quais sites de terceiros originalmente direcionam tráfego para o site.

>[!IMPORTANT]
>
>Você deve configurar os [Filtros de URL internos](/help/admin/admin/internal-url-filter-admin.md) do conjunto de relatórios para utilizar essa dimensão. Falhas ao configurar filtros de URL internos podem incluir domínios internos e impedir que domínios externos apareçam.

## Preencher esta dimensão com dados

Essa dimensão requer configuração na interface do Analytics e na implementação.

* Em sua implementação, essa dimensão recupera dados da [`r` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `document.referrer` no navegador. Se você utilizar uma biblioteca do AppMeasurement (por meio do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente. Se um método de coleta de dados diferente do AppMeasurement for utilizado (por meio da API), inclua o parâmetro da sequência de consulta `r` em solicitações de imagem.
* Na interface do Analytics, é necessário configurar os [Filtros de URL internos](/help/admin/admin/internal-url-filter-admin.md) do conjunto de relatórios. Falhas ao configurar filtros de URL internos podem incluir domínios internos e impedir que domínios externos apareçam.

A Adobe mantém o domínio referenciador original por toda a vida útil do visitante. Se um visitante sair e clicar em um link em um domínio diferente a qualquer momento, o novo valor não será registrado. Se quiser ver novos valores, consulte [Domínio referenciador](referring-domain.md).

## Itens de dimensão

Os itens de dimensão incluem os domínios nos quais os visitantes clicam para acessar seu site. Se uma ocorrência não tiver dados de referenciador (definidos ou persistentes), ela será agrupada sob o item de dimensão `"None"`. Esse item de dimensão significa que não havia valor de referenciador, como se o visitante tivesse digitado manualmente o endereço do navegador na barra de endereços ou clicado em um marcador.

## Comparar o domínio referenciador ao domínio referenciador original

O domínio referenciador pode mudar entre as visitas. Por exemplo, um visitante chega ao seu site por meio do `google.com` e, em seguida, uma semana depois, chega ao seu site por meio do `twitter.com`. Finalmente, eles fazem uma compra em seu site. Se estiver usando o domínio referenciador como a dimensão com atribuição de último contato, o `twitter.com` obterá crédito pela compra. Se estiver usando o domínio referenciador original como a dimensão, o `google.com` obterá crédito pela compra independentemente do modelo de atribuição.

O domínio referenciador original nunca é alterado durante toda a vida útil de uma determinada ID de visitante.
