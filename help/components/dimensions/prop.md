---
title: Prop
description: Uma dimensão personalizada que você pode usar no relatórios.
translation-type: tm+mt
source-git-commit: 10e157e370367374b55ee9c87c0e5c7ca9e99c1a
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 26%

---


# Prop

*Esta página de ajuda descreve como as props funcionam como uma dimensão. Para obter informações sobre como implementar props, consulte[props](/help/implement/vars/page-vars/prop.md)no guia Implementar usuário.*

As props são variáveis personalizadas que podem ser usadas da maneira que você desejar. Eles não persistem além da ocorrência que estão definidos.

> [!TIP][ A Adobe recomenda usar eVars na maioria dos casos. ](evar.md) Em versões anteriores do Adobe Analytics, props e eVars tinham vantagens e desvantagens entre si. No entanto, a Adobe melhorou as eVars de modo que elas atendem a quase todos os casos de uso de props.

Se você tiver um documento [de design de](/help/implement/prepare/solution-design.md)solução, poderá alocar essas dimensões personalizadas para valores específicos da sua organização. O número de props disponíveis depende de seu contrato com a Adobe. Até 75 props estarão disponíveis se seu contrato com a Adobe oferecer suporte para isso.

## Preencher props com dados

Cada prop coleta dados da string [`c1` - `c75` query string](/help/implement/validate/query-parameters.md) em solicitações de imagem. Por exemplo, o parâmetro da string de `c1` query coleta dados para prop1, enquanto o parâmetro da string de `c68` query coleta dados para prop68.

O AppMeasurement, que compila variáveis JavaScript em uma solicitação de imagem para coleta de dados, usa as variáveis `prop1` - `prop75`. Consulte [prop](/help/implement/vars/page-vars/prop.md) no guia Implementar usuário para obter diretrizes de implementação.

## Valores de dimensão

Como as props contêm strings personalizadas na implementação, sua organização determina quais valores de dimensão são para cada prop. Certifique-se de registrar a finalidade de cada prop e os valores de dimensão típicos em um documento [de design de](/help/implement/prepare/solution-design.md)solução.

## Valor de props em eVars

A Adobe recomenda usar eVars na maioria dos casos. As exceções a essa declaração são as seguintes:

* Você pode usar props em relatórios em tempo real. As eVars levam pelo menos 30 minutos para serem exibidas no relatórios.
* Props podem se tornar propriedades de lista, que aceitam vários valores na mesma ocorrência. Variáveis de lista são variáveis separadas e há apenas três variáveis de lista disponíveis.
* Quando você ativa a definição de caminho em uma prop, as dimensões [Entrada](entry-dimensions.md) e [Saída](exit-dimensions.md) tornam-se disponíveis imediatamente. Se quiser dimensões de entrada e saída para eVars, crie um segmento manualmente.

Consulte [eVar](evar.md) para obter mais comparações entre props e eVars.
