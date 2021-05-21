---
title: Prop
description: Uma dimensão personalizada que você pode usar nos relatórios.
exl-id: cf8ad65b-bc54-473e-bcfc-9c981d23e782
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '467'
ht-degree: 100%

---

# Prop

*Esta página de ajuda descreve como as props funcionam como uma dimensão. Para obter informações sobre como implementar props, consulte [props](/help/implement/vars/page-vars/prop.md) no guia de usuário Implementar.*

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

É possível fazer com que qualquer prop diferencie maiúsculas e minúsculas. Você também pode desativar a diferenciação entre maiúsculas e minúsculas para qualquer prop depois que ela estiver ativada. Entre em contato com o Atendimento ao cliente da Adobe com a ID do conjunto de relatórios e as variáveis desejadas para alterar a diferenciação entre maiúsculas e minúsculas.

>[!IMPORTANT]
>
>Alterar a diferenciação entre maiúsculas e minúsculas pode cortar itens de dimensão, causar resultados inesperados com segmentos e causar problemas com filtros. A Adobe recomenda que essa configuração seja alterada entre dois períodos principais, como o início de um mês ou ano.

## Valor de props em relação a eVars

A Adobe recomenda usar eVars na maioria dos casos. As exceções a essa declaração são as seguintes:

* Você pode usar props em relatórios em tempo real. As eVars levam pelo menos 30 minutos para serem exibidas no relatórios.
* Props podem se tornar propriedades de lista, que aceitam vários valores na mesma ocorrência. Variáveis de lista são variáveis separadas e há apenas três variáveis de lista disponíveis.
* Quando você ativa a definição de caminho em uma prop, as dimensões [Entrada](entry-dimensions.md) e [Saída](exit-dimensions.md) ficam disponíveis imediatamente. Se quiser dimensões de entrada e saída para eVars, crie um segmento manualmente.

Consulte [eVar](evar.md) para obter mais comparações entre props e eVars.
