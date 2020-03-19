---
title: prop
description: Variáveis personalizadas que podem ser usadas na implementação.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# prop

As props são variáveis personalizadas que podem ser usadas da maneira que você desejar.

> [!TIP] A Adobe recomenda usar eVars na maioria dos casos. Em versões anteriores do Adobe Analytics, props e eVars tinham vantagens e desvantagens entre si. No entanto, a Adobe melhorou as eVars para onde elas atendem a quase todos os casos de uso de props. Consulte [eVars](evar.md) para obter uma comparação de recursos entre esses dois tipos de variáveis personalizadas.

Se sua organização usar props, certifique-se de registrar sua utilização e lógica no documento [de design da](../../prepare/solution-design.md)solução.

## Props no Adobe Experience Platform Launch

Você pode definir props ao configurar a extensão do Analytics (variáveis globais) ou em regras.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá para a [!UICONTROL Rules] guia e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Actions], clique em uma [!UICONTROL Adobe Analytics - Set Variables] ação existente ou no ícone &#39;+&#39;.
5. Defina a [!UICONTROL Extension] lista suspensa como Adobe Analytics e [!UICONTROL Action Type] como [!UICONTROL Set Variables].
6. Localize a [!UICONTROL Props] seção.

Você pode selecionar uma prop para definir um valor ou elemento de dados. Também é possível copiar o valor de outra variável do Analytics.

## s.prop1 - s.prop75 no editor de código personalizado do AppMeasurement e Launch

Cada variável prop é uma string que contém valores personalizados específicos para sua organização. Seu comprimento máximo é de 100 bytes; valores com mais de 100 bytes são truncados automaticamente quando enviados para a Adobe.

```js
s.prop1 = "Example custom value";
```

## Propriedades de lista

Propriedades de lista são uma configuração aplicada a props que permitem que a variável mantenha vários valores na mesma ocorrência. Se essa configuração não estiver ativada ou se o delimitador errado for usado, a variável será tratada como um único valor.

### Configurar props de lista

Habilitar props de lista nas configurações do conjunto de relatórios. See [Traffic variables](/help/admin/admin/c-traffic-variables/traffic-var.md) in the Admin user guide. Verifique se o delimitador desejado está configurado corretamente. A Adobe não fornece um delimitador padrão.

> [!TIP] Os delimitadores comuns usados em implementações são vírgula (`,`), dois pontos (`:`), ponto-e-vírgula (`;`) ou barra vertical (`|`). Você pode usar qualquer delimitador que melhor se ajuste à sua implementação.

### Definir props de lista

Depois de configurar as props de lista nas configurações do conjunto de relatórios com o delimitador desejado, não há diferenças de implementação além de usar o delimitador.

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

> [!IMPORTANT] Propriedades de lista ainda estão sujeitos ao comprimento máximo de 100 bytes. Propriedades de lista são mais fáceis de atingir esse limite e ficam truncados, pois podem conter vários valores. Considere o uso de abreviações ou a redução de valores se você puder atingir esse limite de 100 bytes.

Se você definir o mesmo valor mais de uma vez em uma prop de lista, a duplicação será cancelada no relatório. A Analysis Workspace conta o número de ocorrências em que um valor é visto, e não o número de vezes que um valor existe nos dados.
