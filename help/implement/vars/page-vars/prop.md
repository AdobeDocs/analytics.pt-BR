---
title: prop
description: Variáveis personalizadas que podem ser usadas na implementação.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# prop

As props são variáveis personalizadas que podem ser usadas da maneira que você desejar.

>[!TIP] A Adobe recomenda usar eVars na maioria dos casos. Em versões anteriores do Adobe Analytics, props e eVars tinham vantagens e desvantagens entre si. No entanto, a Adobe melhorou as eVars de modo que elas atendem a quase todos os casos de uso de props. Consulte [eVars](evar.md) para obter uma comparação de recursos entre esses dois tipos de variáveis personalizadas.

Se a sua organização usar props, certifique-se de registrar o uso e a lógica deles no [documento de design da solução](../../prepare/solution-design.md).

## Props no Adobe Experience Platform Launch

Você pode definir props ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Em [!UICONTROL Actions], clique em uma [!UICONTROL Adobe Analytics - Set Variables] ação existente ou no ícone &#39;+&#39;.
5. Defina a [!UICONTROL Extension] lista suspensa como Adobe Analytics e [!UICONTROL Action Type] como [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Props] section.

Você pode selecionar uma prop para definir um valor ou um elemento de dados. Também é possível copiar o valor de outra variável do Analytics.

## s.prop1 e s.prop75 no AppMeasurement e no editor de código personalizado do Launch

Cada variável de prop é uma string que contém valores personalizados específicos para sua organização. O comprimento máximo delas é de 100 bytes; valores com mais de 100 bytes são truncados automaticamente quando enviados para a Adobe.

```js
s.prop1 = "Example custom value";
```

## Props de lista

Props de lista são uma configuração aplicada a props que permitem que a variável armazene muitos valores na mesma ocorrência. Se essa configuração não estiver ativada ou se o delimitador errado for usado, a variável será tratada como um valor único.

### Configurar props de lista

Ative props de lista nas configurações do conjunto de relatórios. Consulte [Variáveis de tráfego](/help/admin/admin/c-traffic-variables/traffic-var.md) no Guia do usuário de administração. Verifique se o delimitador desejado está configurado corretamente. A Adobe não fornece um delimitador padrão.

>[!TIP] Os delimitadores comuns usados em implementações são vírgula (`,`), dois pontos (`:`), ponto e vírgula (`;`) ou barra vertical (`|`). Você pode usar qualquer delimitador que melhor se ajuste à sua implementação.

### Definir props de lista

Depois de configurar as props de lista nas configurações do conjunto de relatórios com o delimitador desejado, não há diferenças de implementação além do uso do delimitador.

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

>[!IMPORTANT] Propriedades de lista ainda estão sujeitas ao tamanho máximo de 100 bytes. Propriedades de lista atingem mais facilmente esse limite e ficam truncados, pois podem conter vários valores. Considere o uso de abreviações ou a redução de valores for possível atingir o limite de 100 bytes.

Se você definir o mesmo valor mais de uma vez em uma prop de lista, eles serão deduplicados no relatórios. A Área de trabalho de Análise conta o número de ocorrências em que um valor é visto, e não o número de vezes em que um valor existe nos dados.
