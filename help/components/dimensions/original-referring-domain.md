---
title: Domínio referenciador original
description: O primeiro domínio referenciador no qual um visitante estava antes de clicar para acessar o site.
feature: Dimensions
exl-id: 6b9ac662-a79a-477b-8612-7980da7cfadd
TQID: 'https://experienceleague.adobe.com/G-se6LH33gMTt8ttrP5RBzL85m335ujtbiSm6EjLGuU'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 72%
---
# Domínio referenciador original

A [dimensão](overview.md) de &#39;Domínio referenciador original&#39; informa o primeiro domínio referenciador em que um visitante clicou para chegar ao site. Depois de definido, ele contém o mesmo valor para toda a vida útil da ID do visitante. Essa dimensão é útil para entender quais sites de terceiros originalmente direcionam tráfego para o site.

>[!IMPORTANT]
>
>Você deve configurar os [Filtros de URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) do conjunto de relatórios para utilizar essa dimensão. Falhas ao configurar filtros de URL internos podem incluir domínios internos e impedir que domínios externos apareçam.

## Preencher esta dimensão com dados

A Adobe deriva essa dimensão do primeiro [referenciador](referrer.md) do visitante, usando a parte de domínio desse URL de referenciador. Não há variável a ser definida. Você deve configurar os [filtros internos de URL](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) do conjunto de relatórios. Se isso não for feito, poderá incluir domínios internos ou impedir que domínios externos apareçam.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (derivado do primeiro referenciador do visitante) |
| **Web SDK / campo XDM** | Nenhum (derivado do primeiro referenciador do visitante) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | Visitante |

Se um visitante sair e clicar em um link em um domínio diferente a qualquer momento, o novo valor não será registrado. Para ver novos valores, consulte [Domínio referenciador](referring-domain.md).

## Itens de dimensão

Os itens de dimensão incluem os domínios nos quais os visitantes clicam para acessar seu site. Se um hit não tiver dados de referenciador (definidos ou persistentes), ele será agrupado sob o item de dimensão `"None"`. Esse item de dimensão significa que não havia valor de referenciador, como se o visitante tivesse digitado manualmente o endereço do navegador na barra de endereços ou clicado em um marcador.

## Comparar o domínio referenciador ao domínio referenciador original

O domínio referenciador pode mudar entre as visitas. Por exemplo, um visitante chega ao seu site por meio do `google.com` e, em seguida, uma semana depois, chega ao seu site por meio do `twitter.com`. Finalmente, eles fazem uma compra em seu site. Se estiver usando o domínio referenciador como a dimensão com atribuição de último contato, o `twitter.com` obterá crédito pela compra. Se estiver usando o domínio referenciador original como a dimensão, o `google.com` obterá crédito pela compra independentemente do modelo de atribuição.

O domínio referenciador original nunca é alterado durante toda a vida útil de uma determinada ID de visitante.
