---
title: prop
description: Variáveis personalizadas que podem ser usadas na implementação.
feature: Appmeasurement Implementation
exl-id: 0d0ff8cd-1d8c-4263-866d-e51ad66148b0
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 85%

---

# prop

*Esta página de ajuda descreve como implementar props. Para obter informações sobre como as props funcionam como uma dimensão, consulte [prop](/help/components/dimensions/prop.md) no guia Usuário de componentes.*

As props são variáveis personalizadas que podem ser usadas da maneira que você desejar. Elas não persistem além da ocorrência definida.

>[!TIP]
>
>A Adobe recomenda usar [eVars](evar.md) na maioria dos casos. Em versões anteriores do Adobe Analytics, props e eVars tinham vantagens e desvantagens entre si. No entanto, a Adobe melhorou as eVars a ponto de agora atenderem a quase todos os casos de uso de props.

Se você tiver um [documento de design de solução](/help/implement/prepare/solution-design.md), será possível alocar essas dimensões personalizadas para valores específicos da sua organização. O número de props disponíveis depende de seu contrato com a Adobe. Até 75 props estarão disponíveis se seu contrato com a Adobe permitir.

## Props usando o SDK da Web

As props são mapeadas para as seguintes variáveis:

* [Objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm._experience.analytics.customDimensions.props.prop1` - `xdm._experience.analytics.customDimensions.props.prop75` - propriedades de lista estão especificadas em um [conjunto separado de campos](#list-props-web-sdk).
* [Objeto de dados](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75`; ou `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` - propriedades de lista são incluídas nestes campos.

## Props usando a extensão do Adobe Analytics

Você pode definir props ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o [!UICONTROL Tipo de Ação] como [!UICONTROL Definir Variáveis].
6. Localize a seção [!UICONTROL Props].

Você pode definir uma prop a um valor ou um elemento de dados. Também é possível copiar o valor de outra variável do Analytics.

## s.prop1 - s.prop75 no AppMeasurement e no editor de código personalizado da extensão do Analytics

Cada variável de prop é uma string que contém valores personalizados específicos para sua organização. O comprimento máximo delas é de 100 bytes; valores com mais de 100 bytes são truncados automaticamente quando enviados para a Adobe.

```js
s.prop1 = "Example custom value";
```

## Props de lista

Props de lista são uma configuração aplicada a props que permitem que a variável armazene muitos valores na mesma ocorrência. Se essa configuração não estiver habilitada ou se o delimitador errado for usado, a variável será tratada como um valor único.

### Configurar props de lista

Habilitar propriedade de lista em [Variáveis de tráfego](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md) em configurações do conjunto de relatórios. Verifique se o delimitador desejado está configurado corretamente. A Adobe não fornece um delimitador padrão.

>[!TIP]
>
>Os delimitadores comuns usados em implementações são vírgula (`,`), dois pontos (`:`), ponto e vírgula (`;`) ou barra vertical (`|`). Você pode usar qualquer delimitador ASCII não estendido que melhor se ajuste à sua implementação.

### Definir propriedade de lista usando o SDK da Web {#list-props-web-sdk}

Se estiver usando o [**objeto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), as props de lista serão mapeadas para `xdm._experience.analytics.customDimensions.listProps.prop1.values[]` - `xdm._experience.analytics.customDimensions.listProps.prop75.values[]`. O SDK da Web usa automaticamente o delimitador correto listado nas configurações do conjunto de relatórios. Se você definir o delimitador no campo XDM (por exemplo, `xdm._experience.analytics.customDimensions.props.prop1.delimiter`), que substitui o delimitador recuperado automaticamente das configurações do conjunto de relatórios e pode levar à análise incorreta da string de propriedade da lista.

Se estiver usando o [**objeto de dados**](/help/implement/aep-edge/data-var-mapping.md), as props de lista usarão os mesmos campos que as props padrão e seguirão a sintaxe do AppMeasurement.

### Definir propriedades de lista usando a extensão do Adobe Analytics e o AppMeasurement

Depois de configurar as props de lista nas configurações do conjunto de relatórios com o delimitador desejado, não há diferenças de implementação além do uso do delimitador.

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

>[!IMPORTANT]
>
>Propriedades de lista ainda estão sujeitas ao tamanho máximo de 100 bytes. Propriedades de lista atingem mais facilmente esse limite e ficam truncados, pois podem conter vários valores. Considere o uso de abreviações ou a redução de valores for possível atingir o limite de 100 bytes.

Se você definir o mesmo valor mais de uma vez em uma prop de lista, eles serão deduplicados no relatórios. O Analysis Workspace conta o número de ocorrências em que um valor é visto, e não o número de vezes em que um valor existe nos dados.
