---
title: eVar (dimensão de merchandising)
description: Variáveis personalizadas que se vinculam à dimensão de produtos.
feature: Dimensions
exl-id: a7e224c4-e8ae-4b53-8051-8b5dd43ff380
TQID: 'https://experienceleague.adobe.com/No-Va3JzN6Qz9hBu73A5ZzKudEB1Tqa4sNPKVKAASGI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
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
source-git-commit: ca917b867cd84b09b899ce7b72586f0b15003106
workflow-type: tm+mt
source-wordcount: '2343'
ht-degree: 4%
---
# eVar (merchandising)

>[!BEGINSHADEBOX]

*Esta página de ajuda descreve como as eVars de merchandising funcionam como uma [dimensão](overview.md). Para obter informações sobre como implementar eVars de merchandising, consulte [eVar (variável de merchandising)](/help/implement/vars/page-vars/evar-merchandising.md) no guia do usuário de implementação.*

>[!ENDSHADEBOX]

Um eVar de merchandising funciona como um eVar padrão, exceto que cada produto tem sua própria cópia dele. Persistência, alocação e expiração funcionam da mesma maneira, mas separadamente para cada produto. Um eVar padrão contém um valor persistente por visitante que recebe crédito por cada evento bem-sucedido. Um eVar de merchandising detém um valor persistente por produto e esse valor recebe crédito pelos eventos de sucesso desse produto:

* Produto A → `eVar1` = `value A`
* Produto B → `eVar1` = `value B`

O valor de cada produto pode ser definido ou alterado somente em ocorrências que incluam esse produto. Depois de definido, o valor persiste até expirar e recebe crédito somente pelos eventos bem-sucedidos desse produto. A alteração do valor do produto A não afeta o produto B.

As eVars de merchandising funcionam somente com a variável [`products`](/help/implement/vars/page-vars/products.md). Um valor de eVar de merchandising que não está vinculado a um produto não recebe crédito. Eventos bem-sucedidos em ocorrências sem produtos são atribuídos a `"None"` para cada eVar de merchandising.

>[!TIP]
>
>Para associar valores persistentes a uma dimensão diferente de produtos, considere usar [[!UICONTROL Dimensões de ligação]](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-dataviews/component-settings/persistence#binding-dimension) no Customer Journey Analytics.

## Por que usar eVars de comercialização

Manter um valor separado para cada produto é importante quando um único valor não deve receber crédito por tudo o que um visitante compra. Um eVar padrão funciona bem para campanhas externas ou termos de pesquisa externa, onde um valor deve receber crédito por qualquer evento bem-sucedido que ocorrer. Por exemplo, se um cliente clicar em um link em uma campanha de email para visitar seu site, todas as compras feitas como resultado deverão ser creditadas a essa campanha.

A pesquisa interna e a navegação por categorias são diferentes, pois um visitante geralmente as usa para encontrar vários produtos, cada um de uma maneira diferente. Por exemplo, um cliente pesquisa por `"goggles"` em seu site e, em seguida, adiciona um par ao carrinho:

![Exemplo de óculos](assets/merch-example-goggles.png)

Antes do check-out, o cliente pesquisa por `"winter coat"` e, em seguida, adiciona uma jaqueta ao carrinho:

![Exemplo de casacos](assets/merch-example-coat.png)

Quando o visitante conclui esta compra, o termo de pesquisa interna `"winter coat"` recebe crédito pelo pedido inteiro, incluindo os óculos, porque é o valor mais recente da eVar (a alocação padrão de [!UICONTROL Mais recente (Último)]). O termo de pesquisa `"goggles"` não recebe crédito, mesmo que tenha levado a uma parte da compra:

| Termo de pesquisa interna | Receita |
| --- | --- |
| casaco de inverno | $157 |

## Como as eVars de merchandising resolvem esse problema

Se o merchandising for habilitado para a eVar no exemplo anterior, o termo de pesquisa `"goggles"` será vinculado aos óculos de neve, e o termo de pesquisa `"winter coat"` será vinculado à jaqueta. As variáveis de merchandising alocam receita no nível do produto, portanto, cada termo recebe crédito pela quantidade de receita do produto ao qual o termo está vinculado:

| Termo de pesquisa interna | Receita |
| --- | --- |
| casaco de inverno | $119 |
| óculos | $38 |

## Como a vinculação e a alocação funcionam

As eVars de merchandising se baseiam em três conceitos:

* **Ligação**: uma associação entre um produto e um valor de eVar. Cada produto mantém sua própria vinculação para cada eVar de merchandising. Como um valor eVar padrão, uma vinculação persiste em ocorrências posteriores até expirar. Por exemplo, um valor vinculado a um produto em uma página de produto ainda recebe crédito quando esse produto é comprado em uma página posterior, sem definir o valor novamente. A forma como um valor atinge o produto depende da sintaxe do eVar, descrita abaixo.
* **Alocação**: a configuração [!UICONTROL Alocação] determina o que acontece quando um novo valor tenta associar-se a um produto que **já está associado**. A alocação é avaliada separadamente para cada produto, de modo que os valores de eVar de merchandising vinculados a produtos diferentes nunca competem entre si.
  * **[!UICONTROL Valor Original (Primeiro)]**: a associação existente é mantida. O novo valor é ignorado para esse produto até que a vinculação expire.
  * **[!UICONTROL Mais recente (último)]**: o produto se associa novamente ao novo valor.
* **Expiração**: a configuração [!UICONTROL Expirar Após] determina quando as associações terminam. A vinculação de cada produto tem sua própria expiração, contada a partir de quando esse produto foi vinculado. Por exemplo, com a expiração de [!UICONTROL Semana], se o produto A estiver vinculado na segunda-feira e o produto B estiver vinculado na quarta-feira, a vinculação do produto A expirará na segunda-feira seguinte e a vinculação do produto B expirará na quarta-feira seguinte. Quando um vínculo expira, o produto não tem mais um valor para esse eVar, da mesma forma que um eVar padrão não tem valor após a expiração. Os eventos bem-sucedidos para esse produto são atribuídos a `"None"` até que o produto seja vinculado novamente.

Cada eVar de merchandising usa uma das duas sintaxes, definidas na configuração [!UICONTROL Merchandising] das [configurações do conjunto de relatórios](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md). A sintaxe determina como um valor atinge um produto:

* **[Sintaxe do produto](#product-syntax)**: o valor é definido diretamente em cada produto na variável `products` e vinculado a esse produto nessa ocorrência.
* **[Sintaxe da variável de conversão](#conversion-variable-syntax)**: o valor é definido no próprio eVar e persiste como um valor eVar padrão. Ele se vincula aos produtos na mesma ocorrência ou em uma ocorrência posterior que contém um evento compulsório.

Ambas as sintaxes usam o mesmo comportamento de vinculação, alocação e expiração descrito acima. Elas diferem das seguintes maneiras:

| | Sintaxe do produto | Sintaxe de variável de conversão |
| --- | --- | --- |
| Onde o valor é definido | Em cada produto, na variável [`products`](/help/implement/vars/page-vars/products.md) | No próprio [`eVar`](/help/implement/vars/page-vars/evar-merchandising.md), da mesma forma que um eVar padrão |
| Quando ocorre a vinculação | Em qualquer ocorrência em que o valor seja definido no produto | Nas ocorrências que contêm produtos e um evento compulsório configurado |
| Valores por ocorrência | Cada produto pode ter um valor diferente | Cada produto na ocorrência de vinculação recebe o mesmo valor |
| Esforço de implementação | Maior | Lower |

## Sintaxe do produto

Com a sintaxe do produto, o valor do eVar é definido em cada produto na variável `products`. Na cadeia de caracteres `products`, o valor após o último ponto e vírgula de um produto é seu eVar de merchandising. Consulte [Implementar usando a sintaxe do produto](/help/implement/vars/page-vars/evar-merchandising.md#implement-using-product-syntax) para obter a sintaxe completa.

O valor se vincula diretamente a esse produto nessa ocorrência. Os eventos de vinculação não são usados. Ocorrências posteriores que incluem o produto, como uma adição ou compra de carrinho, não precisam repetir o valor. Como cada produto carrega seu próprio valor, a sintaxe do produto é a única opção quando os produtos na **mesma ocorrência** precisam de **valores diferentes**.

+++Exemplo: o mesmo produto recebe dois valores

| Hit | `products` | `events` |
| --- | --- | --- |
| 1 | `;12345;;;;eVar1=internal keyword search` | |
| 2 | `;12345;;;;eVar1=internal campaign` | |
| 3 | `;12345;1;50` | `purchase` |

* **[!UICONTROL Valor Original (Primeiro)]**: a ocorrência 2 é ignorada para o produto `12345`. A compra é creditada a `internal keyword search`.
* **[!UICONTROL Mais recente (último)]**: a ocorrência 2 vincula novamente o produto `12345`. A compra é creditada a `internal campaign`.

+++

+++Exemplo: dois produtos recebem valores diferentes

| Hit | `products` | `events` |
| --- | --- | --- |
| 1 | `;productA;;;;eVar1=value A` | |
| 2 | `;productB;;;;eVar1=value B` | |
| 3 | `;productA;1;50,;productB;1;30` | `purchase` |

Cada produto mantém seu próprio vínculo, portanto, a configuração de alocação não tem efeito neste exemplo. `value A` recebe crédito pela receita do produto A e `value B` recebe crédito pela receita do produto B. Ambos os valores recebem um pedido, pois o pedido contém um produto vinculado a cada valor.

+++

+++Exemplo: produtos com a mesma ID e valores diferentes

Um visitante compra uma camiseta azul média e uma camiseta vermelha grande, ambas com a ID de produto principal `tshirt123` e o `eVar10` captura SKUs secundárias:

```js
s.events = "purchase";
s.products = ";tshirt123;1;20;;eVar10=tshirt123-m-blue,;tshirt123;1;20;;eVar10=tshirt123-l-red";
```

Cada SKU filho recebe crédito pela sua própria instância de `tshirt123`.

+++

A compensação é que a sintaxe do produto requer a string de valor completa em cada produto sempre que a vinculação deve ocorrer. Para métodos de descoberta de produtos, que normalmente usam várias eVars de uma só vez, a string é semelhante a:

```js
s.products = ";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
```

Um método de descoberta só deve receber crédito depois que o visitante interagir com um produto, de modo que essa string geralmente seja definida na página de detalhes do produto ou em uma adição ao carrinho, não na página de resultados da pesquisa. Para isso, os desenvolvedores devem:

* Carregue os detalhes do método de descoberta da página de método de descoberta para a página de detalhes do produto ou disponibilize-os quando a adição de um carrinho for acionada a partir de uma página de resultados.
* Montar a cadeia de caracteres `products` completa sem erros de sintaxe.

A sintaxe de variável de conversão evita ambos os requisitos.

## Sintaxe de variável de conversão

Com a sintaxe da variável de conversão, o valor é definido na própria eVar:

```js
s.eVar1 = "internal keyword search";
```

A eVar atua como uma *área de preparo*. Um valor definido no eVar é mantido lá até que um evento compulsório o vincule aos produtos em uma ocorrência. A vinculação ocorre em dois estágios:

1. **Estágios**: quando o eVar é definido, seu valor persiste em ocorrências subsequentes até expirar. Este valor persistente é a coluna `post_evar` em [feeds de dados](/help/export/analytics-data-feed/data-feed-overview.md). Para eVars de merchandising que usam sintaxe de variável de conversão, o valor em etapas **sempre reflete o valor enviado mais recentemente**, independentemente da configuração [!UICONTROL Allocation]. Cada novo valor substitui o valor preparado anteriormente.
1. **Associação**: quando uma ocorrência contém produtos e um [!UICONTROL Evento de Associação de Merchandising] configurado, o valor da etapa é associado a cada produto nessa ocorrência. Se um produto já estiver vinculado, a [!UICONTROL Alocação] determinará se o novo valor substituirá a associação existente. Os produtos que já estão vinculados mantêm seu valor com [!UICONTROL Valor Original (Primeiro)] ou revincular com [!UICONTROL Mais Recente (Último)].

Se a eVar, a variável `products` e um evento de vinculação estiverem definidos na mesma ocorrência, a preparação e a vinculação ocorrerão simultaneamente. O novo valor se vincula imediatamente aos produtos nessa ocorrência.

Definir o eVar ao lado de um produto sem um evento compulsório não vincula o valor a esse produto. Um valor dividido não recebe crédito até que seja vinculado a um produto.

### O que os eventos de vinculação fazem

Um evento compulsório é o acionador que instrui o Adobe a vincular o valor preparado aos produtos na ocorrência.

* Os eventos de ligação podem ser eventos bem-sucedidos padrão ou personalizados, o código de rastreamento ([!UICONTROL Evento de campanha]) ou eVars. As props não têm efeito na vinculação.
* Você pode configurar vários eventos de associação, como [!UICONTROL Evento de Exibição de Produto], [!UICONTROL Evento de Adição de Carrinho] e [!UICONTROL Evento de Compra]. Se qualquer um desses eventos estiver em uma ocorrência com produtos, o valor dividido em etapas se vinculará a cada produto nessa ocorrência.
* Por padrão ([!UICONTROL Todos]), a associação ocorre sempre que qualquer outro evento ou eVar está na mesma ocorrência que um produto. [!UICONTROL Todos] será usado se nenhum evento de associação for explicitamente selecionado. Com [!UICONTROL Todos], definir a eVar em uma ocorrência que inclui produtos sempre aciona a associação nessa ocorrência. Um valor preparado em uma ocorrência anterior vincula-se na próxima ocorrência que inclui produtos e qualquer outro evento ou eVar.

+++Exemplo: vinculação com um evento compulsório

Considere as seguintes ocorrências:

```js
// Hit 1
s.eVar1 = "internal keyword search";
s.eVar2 = "sandals";

// Hit 2
s.products = ";sandal123";
s.events = "prodView";
```

Se `prodView` for um evento de associação para ambas as eVars, 2 associações serão acessadas de `internal keyword search` (`eVar1`) e `sandals` (`eVar2`) a `sandal123`. Se uma eVar não listar `prodView` como um evento de associação, nenhuma associação ocorrerá para essa eVar.

+++

+++Exemplo: a alocação é avaliada por produto

| Hit | `eVar1` | `products` | `events` |
| --- | --- | --- | --- |
| 1 | `value A` | | |
| 2 | | `;productA,;productB` | Evento compulsório |
| 3 | `value B` | | |
| 4 | | `;productA` | Evento compulsório |
| 5 | | `;productA;1;50,;productB;1;30` | `purchase` |

Após a ocorrência 3, o valor da etapa (`post_evar1`) é `value B` com qualquer configuração de alocação.

* **[!UICONTROL Valor Original (Primeiro)]**: a ocorrência 4 é ignorada para o produto A, pois o produto A já está vinculado. Ambos os produtos permanecem vinculados ao `value A`, que recebe todo o crédito de compra.
* **[!UICONTROL Mais recente (último)]**: a ocorrência 4 vincula novamente o produto A a `value B`. O produto B não está na ocorrência 4, portanto, permanece vinculado a `value A`. O crédito de compra do Produto A vai para `value B`, e o crédito de compra do Produto B vai para `value A`.

Com apenas uma única tentativa de vinculação, como ocorrências 1, 2 e 5 isoladamente, ambas as configurações produzem o mesmo resultado. A alocação é importante somente quando um produto que já está vinculado recebe outra tentativa de vinculação.

+++

## Prática recomendada: métodos de busca de produtos

A maioria dos sites de varejo se beneficia do rastreamento dos seguintes métodos de busca de produtos, cada um como um eVar de merchandising:

* Palavras-chave de pesquisa interna (por exemplo, `eVar2`)
* Códigos de rastreamento de campanha interna (por exemplo, `eVar3`)
* Categorias de merchandising ou navegação (por exemplo, `eVar4`)
* Links de venda cruzada (por exemplo, `eVar5`)
* Um eVar de método de descoberta de produto geral que compara todos os métodos, incluindo métodos como links externos para páginas de produto (por exemplo, `eVar1`)

Quando um visitante usa um método, defina o outro método de descoberta eVars como um valor &quot;não-&quot;. Caso contrário, o valor anterior de um método não utilizado poderia receber crédito por um produto encontrado por meio de outro método. Por exemplo, na página de resultados de uma pesquisa interna por &quot;sandálias&quot;:

```js
s.eVar1 = "internal keyword search";
s.eVar2 = "sandals";
s.eVar3 = "non-internal campaign";
s.eVar4 = "non-browse";
s.eVar5 = "non-cross-sell";
```

Com a sintaxe de variável de conversão, os desenvolvedores podem definir apenas valores simples, como um termo de pesquisa em uma prop, e a lógica na implementação pode preencher as eVars de merchandising. Nada precisa ser passado entre páginas ou incorporado à cadeia de caracteres `products`. A variável `products` ainda é necessária nas ocorrências em que a associação ocorre.

A Adobe recomenda as seguintes configurações para eVars de método de descoberta de produto:

| Configuração | Valor |
| --- | --- |
| [!UICONTROL Alocação] | [!UICONTROL Valor Original (Primeiro)] |
| [!UICONTROL Expirar após] | Por quanto tempo os produtos permanecem no carrinho antes da remoção automática, por exemplo, 14 ou 30 dias usando o [!UICONTROL Personalizado]. Se o carrinho não tiver limite, use [!UICONTROL Comprar]. |
| [!UICONTROL Tipo] | [!UICONTROL Cadeia de caracteres de texto] |
| [!UICONTROL Habilitar merchandising] | [!UICONTROL Habilitado] |
| [!UICONTROL Merchandising] | [!UICONTROL Sintaxe de variável de conversão] |
| [!UICONTROL Evento compulsório de merchandising] | [!UICONTROL Evento de exibição do produto], [!UICONTROL Evento de adição ao carrinho] e [!UICONTROL Evento de compra] |

Consulte [Variáveis de conversão](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md) no Guia do administrador para obter uma descrição de cada configuração.

+++Por que o valor original (primeiro) em vez do mais recente (último)

Muitas vezes, os visitantes encontram novamente um produto que já visualizaram ou adicionaram ao carrinho. Por exemplo:

1. Um visitante pesquisa por &quot;sandálias&quot; e adiciona `sandal123` ao carrinho na página de resultados. O produto está associado a `internal keyword search`.
1. Três dias depois, o visitante navega até **Mulheres > Sapatos > Sandálias** (`eVar1` = `browse`), exibe `sandal123` novamente e o compra.

Com [!UICONTROL Mais Recente (Último)], a exibição de produto na etapa 2 vincula novamente `sandal123` a `browse`, que recebe o crédito de compra. O método que originalmente encontrou o produto não recebe nenhum.

Com [!UICONTROL Valor Original (Primeiro)], a tentativa de associação na etapa 2 é ignorada e `internal keyword search` mantém o crédito.

Se o visitante nunca comprar o produto, a expiração removerá a vinculação, para que o próximo método de descoberta que o visitante usar possa vincular ao produto. É por isso que [!UICONTROL Expirar após] deve corresponder ao tempo em que um produto permanece no carrinho.

+++

## Instâncias em eVars de merchandising

A métrica padrão [Instâncias](../metrics/instances.md) não é recomendada para uso em variáveis de merchandising.

* Para variáveis de merchandising que utilizam sintaxe de produto, as instâncias não são aumentadas.
* Para variáveis de merchandising que utilizam a sintaxe de variável de conversão, as instâncias são contabilizadas cada vez que a eVar é definida. No entanto, a instância atribui ao item de dimensão `"None"` a menos que os seguintes casos aconteçam na mesma ocorrência:
  * A eVar de merchandising é definida com um valor.
  * A variável `products` é definida com um valor.
  * Um evento de vinculação é configurado.

Como a maioria dos casos de uso para a sintaxe da variável de conversão requer a variável eVar e produtos em diferentes ocorrências, a métrica Instâncias padrão não é realista de usar.

Para contar instâncias para cada valor enviado com a sintaxe de variável de conversão, aplique o **modelo de atribuição [Último contato**](/help/analyze/analysis-workspace/attribution/overview.md) à métrica Instâncias. Os modelos de atribuição usam os valores enviados em cada ocorrência, não valores preparados ou associações de produto. A janela de pesquisa não importa, pois Último contato credita cada valor na ocorrência para a qual foi enviado, independentemente da configuração de alocação do eVar.

![Seleção de atribuição](assets/attribution-select.png)
