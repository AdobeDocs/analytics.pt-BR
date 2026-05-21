---
title: Domínio referenciador original
description: O primeiro domínio referenciador no qual um visitante estava antes de clicar para acessar o site.
feature: Dimensions
exl-id: 6b9ac662-a79a-477b-8612-7980da7cfadd
TQID: https://experienceleague.adobe.com/G-se6LH33gMTt8ttrP5RBzL85m335ujtbiSm6EjLGuU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 409
ht-degree: 95%

---

# Domínio referenciador original

A [dimensão](overview.md) de &#39;Domínio referenciador original&#39; informa o primeiro domínio referenciador em que um visitante clicou para chegar ao site. Depois de definido, ele contém o mesmo valor para toda a vida útil da ID do visitante. Essa dimensão é útil para entender quais sites de terceiros originalmente direcionam tráfego para o site.

>[!IMPORTANT]
>
>Você deve configurar os [Filtros de URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) do conjunto de relatórios para utilizar essa dimensão. Falhas ao configurar filtros de URL internos podem incluir domínios internos e impedir que domínios externos apareçam.

## Preencher esta dimensão com dados

Essa dimensão requer configuração na interface do Analytics e na implementação.

* Em sua implementação, essa dimensão recupera dados da [`r` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `document.referrer` no navegador. Se você utilizar uma biblioteca do AppMeasurement (por meio de tags na Adobe Experience Platform ), essa dimensão funcionará imediatamente. Se um método de coleta de dados diferente do AppMeasurement for utilizado (por meio da API), inclua o parâmetro da sequência de consulta `r` em solicitações de imagem.
* Na interface do Analytics, é necessário configurar os [Filtros de URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) do conjunto de relatórios. Falhas ao configurar filtros de URL internos podem incluir domínios internos e impedir que domínios externos apareçam.

A Adobe mantém o domínio referenciador original por toda a vida útil do visitante. Se um visitante sair e clicar em um link em um domínio diferente a qualquer momento, o novo valor não será registrado. Se quiser ver novos valores, consulte [Domínio referenciador](referring-domain.md).

## Itens de dimensão

Os itens de dimensão incluem os domínios nos quais os visitantes clicam para acessar seu site. Se uma ocorrência não tiver dados de referenciador (definidos ou persistentes), ela será agrupada sob o item de dimensão `"None"`. Esse item de dimensão significa que não havia valor de referenciador, como se o visitante tivesse digitado manualmente o endereço do navegador na barra de endereços ou clicado em um marcador.

## Comparar o domínio referenciador ao domínio referenciador original

O domínio referenciador pode mudar entre as visitas. Por exemplo, um visitante chega ao seu site por meio do `google.com` e, em seguida, uma semana depois, chega ao seu site por meio do `twitter.com`. Finalmente, eles fazem uma compra em seu site. Se estiver usando o domínio referenciador como a dimensão com atribuição de último contato, o `twitter.com` obterá crédito pela compra. Se estiver usando o domínio referenciador original como a dimensão, o `google.com` obterá crédito pela compra independentemente do modelo de atribuição.

O domínio referenciador original nunca é alterado durante toda a vida útil de uma determinada ID de visitante.
