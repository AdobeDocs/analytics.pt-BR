---
title: Solução de problemas de implementação do JavaScript
description: Saiba mais sobre problemas comuns e práticas recomendadas para solucionar problemas da implementação do JavaScript.
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 73%

---


# Solução de problemas de implementação do JavaScript

A seguir estão vários motivos pelos quais sua organização pode ter problemas com a inserção correta dos dados no Adobe Analytics.

## Uso de aspas

A maioria das variáveis enviadas para a Adobe são cadeias de caracteres. No JavaScript, é possível usar aspas simples ou aspas duplas.

### Misturar aspas para definir uma variável

Como prática recomendada, verifique se você está em conforme com os tipos de cotações usadas. Se um aspa simples designar o início de uma cadeia de caracteres, ela deverá ser usada para fechá-la.

Por exemplo, ambos `s.eVar1 = 'Value'` e `s.eVar1 = "Value"` são válidos. `s.eVar1 = 'Value"` não é válido.

### Incluir aspas simples ou duplas em uma cadeia de caracteres

Às vezes, é necessário incluir uma aspa simples ou dupla em uma cadeia de caracteres. Por exemplo, você deseja incluir o valor `Alex's sale` ou `John the "Hunter"` nos relatórios. Há dois métodos para incluir esses valores:

* **Usar o outro tipo de citação**: por exemplo, `s.eVar1 = "Alex's sale"` e `s.eVar1 = 'John the "Hunter"'` são válidos.
* **Evitar aspas**: uma barra invertida para evitar aspas. Por exemplo, `s.eVar1 = 'Alex\'s sale'` e `s.eVar1 = "John the \"Hunter\""` são válidos.

### Evite usar aspas curvas

Alguns programas convertem automaticamente aspas neutras (`"..."` e `'...'`) em aspas curvas (`“...”` e `‘...’`). Evite usar editores de documento (como o Microsoft Word) ou transmitir trechos de código por email. As aspas curvas não podem ser usadas no JavaScript.

## Referência ao objeto do Analytics

Todas as variáveis enviadas para a Adobe usam o objeto do Analytics. A maioria das implementações usa o objeto `s`. Ao referenciar variáveis, certifique-se de incluir o objeto do Analytics na referência.

Por exemplo, `s.eVar1 = 'Value'` é válido, mas `eVar1 = 'Value'` não é.

## Definir cada variável uma vez

Quando uma função de rastreamento (`s.t()`) é executada, o AppMeasurement pega todas as variáveis definidas e as compila em uma solicitação de imagem. Se você definir uma variável mais de uma vez na implementação, somente o valor mais recente será usado. Verifique se todos os valores de variável contêm o valor correto quando a função de rastreamento é executada.

## Corrigir capitalização da variável

Algumas variáveis usam letras maiúsculas. As variáveis JavaScript fazem distinção entre maiúsculas e minúsculas. Certifique-se de usar as letras maiúsculas e minúsculas corretas ao definir as variáveis. Por exemplo, `s.eVar1 = 'Value'` é válido, mas `s.evar1 = 'Value'` não é.

## Plug-ins

Algumas organizações usam plug-ins para melhorar a implementação do Adobe Analytics. Ao atualizar as versões do AppMeasurement, não se esqueça de incluir novamente os plug-ins instalados. O código criado no [!UICONTROL Gerenciador de código] não tem um código de plug-in incluído. Faça uma cópia do código existente caso precise reverter para uma versão anterior do AppMeasurement.

## Espaço em branco em valores da variável

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

Nesse caso, `document.title` preenche `s.pageName`, que deve receber um valor de &quot;Página inicial&quot;. Entretanto, alguns navegadores podem interpretar o espaço em branco de forma diferente. O resultado pode ser um dos dois exemplos a seguir:

```js
s.pageName = "Home Page";
```

```js
s.pageName = "        Home Page";
```

Esses dois valores de variável são considerados separados no Adobe Analytics. Entretanto, o espaço em branco é removido automaticamente para fins de exibição. O resultado é um relatório que exibe dois itens de linha aparentemente idênticos da &quot;Página inicial&quot;. Certifique-se de que os valores de variável não contenham espaços em branco antes ou depois do valor desejado.

## Solicitações de imagem truncadas

As implementações que preenchem muitas variáveis com valores longos às vezes podem ser executadas em solicitações de imagem truncadas. Alguns navegadores mais antigos, como o Internet Explorer, impõem um limite de 2083 caracteres em URLs de solicitação de imagem. Se sua organização encarar solicitações de imagem muito longas, tente o seguinte:

* **Use o serviço** de ID de Experience Cloud: As bibliotecas do AppMeasurement 1.4.1 e posteriores enviam automaticamente solicitações de imagem usando o POST HTTP se forem muito longas. Os dados enviados usando esse método não são truncados independentemente do comprimento. Consulte Serviço [de ID da](https://docs.adobe.com/content/help/pt-BR/id-service/using/home.html) Adobe Experience Cloud para obter mais informações.
* **Usar regras** de processamento: [As regras](/help/admin/admin/c-processing-rules/processing-rules.md) de processamento podem copiar valores de uma variável para outra. Esse método evita que você defina o mesmo valor em várias variáveis. Por exemplo:

   Sempre executar:<br>
Substituir valor de prop1 por eVar1<br>Substituir valor de eVar2 por eVar1<br>Substituir valor de prop2 por eVar1<br>

   Em seguida, defina o eVar 1 na sua implementação:

   ```js
   s.eVar1 = "The quick brown fox jumps over the lazy dog";
   ```

* **Usar variáveis** dinâmicas: Se sua implementação preencher muitas variáveis com o mesmo valor, você poderá usar variáveis [](/help/implement/vars/page-vars/dynamic-variables.md) dinâmicas para encurtar o URL da solicitação:

   ```js
   s.eVar1 = "The quick brown fox jumps over the lazy dog";
   s.eVar2 = "D=v1";
   s.prop1 = "D=v1";
   s.prop2 = "D=v1";
   ```

* **Usar classificações**: Se os nomes de produtos ou páginas forem invulgarmente longos, você poderá usar um valor ou código de identificação e, em seguida, usar [classificações](/help/components/classifications/c-classifications.md) para exibir um nome mais amigável.
