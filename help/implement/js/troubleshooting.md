---
title: Solução de problemas de implementação do JavaScript
description: Saiba mais sobre problemas comuns e práticas recomendadas para solucionar problemas de sua implementação do JavaScript.
translation-type: tm+mt
source-git-commit: 8aa6932dcbb6dad88c27ba1cd4f5aad3bafcfc52

---


# Solução de problemas de implementação do JavaScript

A seguir estão vários motivos pelos quais sua organização pode ter problemas com a inserção correta dos dados no Adobe Analytics.

## Uso de aspas

A maioria das variáveis enviadas para a Adobe são strings. Em JavaScript, é possível usar aspas simples ou aspas duplas.

### Misturar aspas para definir uma variável

Como prática recomendada, verifique se você está consistente com os tipos de cotações usadas. Se uma aspa simples designar o início de uma string, uma aspa simples deverá ser usada para fechá-la.

Por exemplo, ambos `s.eVar1 = 'Value'` e ambos `s.eVar1 = "Value"` são válidos. `s.eVar1 = 'Value"` não é válido.

### Incluindo aspas simples ou duplas em uma string

Às vezes, é necessário incluir uma aspa simples ou dupla em uma string. Por exemplo, você deseja incluir o valor `Alex's sale` ou `John the "Hunter"` nos relatórios. Há dois métodos para incluir estes valores:

* **Use o outro tipo** de citação: Por exemplo, `s.eVar1 = "Alex's sale"` e ambos `s.eVar1 = 'John the "Hunter"'` são válidos.
* **Escapar aspas**: Use uma barra invertida para escapar das aspas.  Por exemplo, `s.eVar1 = 'Alex\'s sale'` e ambos `s.eVar1 = "John the \"Hunter\""` são válidos.

### Evite usar aspas curvas

Alguns programas convertem automaticamente aspas neutras (`"..."` e `'...'`) em aspas curvas (`“...”` e `‘...’`). Evite usar editores de documento (como o Microsoft Word) ou transmitir trechos de código por email. Aspas curvas não podem ser usadas no JavaScript.

## Referência ao objeto do Analytics

Todas as variáveis enviadas para a Adobe usam o objeto do Analytics. A maioria das implementações usa o `s` objeto. Ao referenciar variáveis, verifique se você inclui o objeto do Analytics em sua referência.

Por exemplo, `s.eVar1 = 'Value'` é válido, mas não `eVar1 = 'Value'` é.

## Definir cada variável uma vez

Quando uma função de rastreamento (`s.t()`) é executada, o AppMeasurement pega todas as variáveis definidas e as compila em uma solicitação de imagem. Se você definir uma variável mais de uma vez na implementação, somente o valor mais recente será usado. Verifique se todos os valores de variável contêm o valor correto quando a função de rastreamento é executada.

## Correção da capitalização da variável

Algumas variáveis usam letras maiúsculas. As variáveis JavaScript fazem distinção entre maiúsculas e minúsculas. Certifique-se de usar as letras maiúsculas e minúsculas corretas ao definir variáveis. Por exemplo, `s.eVar1 = 'Value'` é válido, mas não `s.evar1 = 'Value'` é.

## Plug-ins

Algumas organizações usam plug-ins para melhorar a implementação do Adobe Analytics. Ao atualizar as versões do AppMeasurement, não se esqueça de incluir novamente os plug-ins instalados. O código criado no Gerenciador [!UICONTROL de] código não tem nenhum código de plug-in com ele. Faça uma cópia do código existente caso precise reverter para uma versão anterior do AppMeasurement.

## Espaço em branco em valores variáveis

Em HTML, existem vários caracteres que criam espaço em branco. São eles espaço, tabulação e retorno de carro (ou feed de linha). Considere o exemplo a seguir:

```html
<head>
  <title>
    Home Page
  </title>
</head>
<body>
<script language="javascript">
  s.pageName = document.title;
</script>
</body>
```

In this case, `document.title` populates `s.pageName`, which receives a value of &quot;Home Page&quot;. Entretanto, alguns navegadores podem interpretar o espaço em branco de forma diferente. O resultado pode ser um dos dois exemplos a seguir:

```js
s.pageName = "Home Page";
```

```js
s.pageName = "        Home Page";
```

Esses dois valores variáveis são considerados separados no Adobe Analytics. Entretanto, o espaço em branco é removido automaticamente para fins de exibição. O resultado é um relatório que exibe dois itens de linha aparentemente idênticos da &quot;Página inicial&quot;. Certifique-se de que os valores de variável não contenham espaços em branco antes ou depois do valor desejado.
