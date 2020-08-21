---
title: prop
description: Variáveis personalizadas que podem ser usadas na implementação.
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '484'
ht-degree: 100%

---


# prop

*Esta página de ajuda descreve como implementar props. Para obter informações sobre como as props funcionam como uma dimensão, consulte [prop](/help/components/dimensions/prop.md) no guia Usuário de componentes.*

As props são variáveis personalizadas que podem ser usadas da maneira que você desejar. Elas não persistem além da ocorrência definida.

>[!TIP]
>
>A Adobe recomenda usar [eVars](evar.md) na maioria dos casos. Em versões anteriores do Adobe Analytics, props e eVars tinham vantagens e desvantagens entre si. No entanto, a Adobe melhorou as eVars de modo que elas atendem a quase todos os casos de uso de props.

Se você tiver um [documento de design de solução](/help/implement/prepare/solution-design.md), será possível alocar essas dimensões personalizadas para valores específicos da sua organização. O número de props disponíveis depende de seu contrato com a Adobe. Até 75 props estarão disponíveis se seu contrato com a Adobe permitir.

## Props no Adobe Experience Platform Launch

Você pode definir props ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Props].

Você pode definir uma prop a um valor ou um elemento de dados. Também é possível copiar o valor de outra variável do Analytics.

## s.prop1 e s.prop75 no AppMeasurement e no editor de código personalizado do Launch

Cada variável de prop é uma string que contém valores personalizados específicos para sua organização. O comprimento máximo delas é de 100 bytes; valores com mais de 100 bytes são truncados automaticamente quando enviados para a Adobe.

```js
s.prop1 = "Example custom value";
```

## Props de lista

Props de lista são uma configuração aplicada a props que permitem que a variável armazene muitos valores na mesma ocorrência. Se essa configuração não estiver ativada ou se o delimitador errado for usado, a variável será tratada como um valor único.

### Configurar props de lista

Ative props de lista nas configurações do conjunto de relatórios. Consulte [Variáveis de tráfego](/help/admin/admin/c-traffic-variables/traffic-var.md) no Guia do usuário de administração. Verifique se o delimitador desejado está configurado corretamente. A Adobe não fornece um delimitador padrão.

>[!TIP]
>
>Os delimitadores comuns usados em implementações são vírgula (`,`), dois pontos (`:`), ponto e vírgula (`;`) ou barra vertical (`|`). Você pode usar qualquer delimitador que melhor se ajuste à sua implementação.

### Definir props de lista

Depois de configurar as props de lista nas configurações do conjunto de relatórios com o delimitador desejado, não há diferenças de implementação além do uso do delimitador.

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

>[!IMPORTANT]
>
>Propriedades de lista ainda estão sujeitas ao tamanho máximo de 100 bytes. Propriedades de lista atingem mais facilmente esse limite e ficam truncados, pois podem conter vários valores. Considere o uso de abreviações ou a redução de valores for possível atingir o limite de 100 bytes.

Se você definir o mesmo valor mais de uma vez em uma prop de lista, eles serão deduplicados no relatórios. O Analysis Workspace conta o número de ocorrências em que um valor é visto, e não o número de vezes em que um valor existe nos dados.
