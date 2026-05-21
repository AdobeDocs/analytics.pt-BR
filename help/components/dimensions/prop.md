---
title: Prop
description: Uma dimensão personalizada que você pode usar nos relatórios.
feature: Dimensions
exl-id: cf8ad65b-bc54-473e-bcfc-9c981d23e782
TQID: https://experienceleague.adobe.com/2WMG5X3GNmogf-9Bbapq78pjVg5ibQQw7Bgb0qNpF1E
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 475
ht-degree: 93%

---

# Prop

*Esta página de ajuda descreve como as props funcionam como uma [dimensão](overview.md). Para obter informações sobre como implementar props, consulte [props](/help/implement/vars/page-vars/prop.md) no guia de usuário Implementar.*

As props são variáveis personalizadas que podem ser usadas da maneira que você desejar. Elas não persistem além da ocorrência definida.

>[!TIP]
>
>A Adobe recomenda usar [eVars](evar.md) na maioria dos casos. Em versões anteriores do Adobe Analytics, props e eVars tinham vantagens e desvantagens entre si. No entanto, a Adobe melhorou as eVars de modo que elas atendem a quase todos os casos de uso de props.

Se você tiver um [documento de design de solução](/help/implement/prepare/solution-design.md), será possível alocar essas dimensões personalizadas para valores específicos da sua organização. O número de props disponíveis depende de seu contrato com a Adobe. Até 75 props estarão disponíveis se seu contrato com a Adobe permitir.

## Preencher props com dados

Cada prop coleta dados da [`c1` - `c75` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. Por exemplo, o parâmetro da sequência de consulta `c1` coleta dados para prop1, enquanto o parâmetro da sequência de consulta `c68` coleta dados para prop68.

O AppMeasurement, que compila variáveis JavaScript em uma solicitação de imagem para coleta de dados, usa as variáveis `prop1` - `prop75`. Consulte [prop](/help/implement/vars/page-vars/prop.md) no guia de usuário Implementar para obter diretrizes de implementação.

## Itens de dimensão

Como as props contêm strings personalizadas na implementação, sua organização determina quais itens de dimensão são para cada prop. Registre a finalidade de cada prop e os itens de dimensão típicos em um [documento de design de solução](/help/implement/prepare/solution-design.md).

## Diferencia maiúsculas de minúsculas

As props, por padrão, não diferenciam maiúsculas de minúsculas. Se você enviar o mesmo valor em letra maiúscula ou minúscula (por exemplo, `"DOG"` e `"Dog"`), o Analysis Workspace os agrupará no mesmo item de dimensão. É utilizada a forma do primeiro valor observado no início do mês do relatórios. O Data Warehouse mostra o primeiro valor encontrado durante o período de solicitação.

É possível fazer com que qualquer prop diferencie maiúsculas e minúsculas. Você também pode desabilitar a diferenciação entre maiúsculas e minúsculas para qualquer prop depois que ela estiver habilitada. Entre em contato com o Atendimento ao cliente da Adobe com a ID do conjunto de relatórios e as variáveis desejadas para alterar a diferenciação entre maiúsculas e minúsculas.

>[!WARNING]
>
>Alterar a diferenciação entre maiúsculas e minúsculas pode cortar itens de dimensão, causar resultados inesperados com segmentos e causar problemas com filtros. A Adobe recomenda que essa configuração seja alterada entre dois períodos principais, como o início de um mês ou ano.

## Valor de props em relação a eVars

A Adobe recomenda usar eVars na maioria dos casos. As exceções a essa declaração são as seguintes:

* Você pode usar props em relatórios em tempo real. As eVars levam pelo menos 30 minutos para serem exibidas no relatórios.
* Props podem se tornar propriedades de lista, que aceitam vários valores na mesma ocorrência. Variáveis de lista são variáveis separadas e há apenas três variáveis de lista disponíveis.
* Quando você habilita a definição de caminho em uma prop, as dimensões [Entrada](entry-dimensions.md) e [Saída](exit-dimensions.md) ficam disponíveis imediatamente. Se quiser dimensões de entrada e saída para eVars, crie um segmento manualmente.

Consulte [eVar](evar.md) para obter mais comparações entre props e eVars.
