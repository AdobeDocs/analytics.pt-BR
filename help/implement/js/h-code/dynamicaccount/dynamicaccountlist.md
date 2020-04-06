---
title: dynamicAccountList
description: Estabeleça lógica sobre como a implementação determina o conjunto de relatórios.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# s.dynamicAccountList

>[!IMPORTANT] As contas dinâmicas só compatíveis com implementações JavaScript herdadas (Código H). Essas variáveis não são compatíveis com as bibliotecas atuais do AppMeasurement nem no Adobe Experience Platform Launch.

A variável `s.dynamicAccountList` determina dinamicamente o valor de `s_account`. Se `dynamicAccountSelection` estiver definida como `true`, a variável `dynamicAccountMatch` será comparada com `dynamicAccountList`. Se uma correspondência for encontrada, a ID do conjunto de relatórios correspondente será usada.

## Sintaxe

Essa variável é uma cadeia de caracteres que é analisada automaticamente pelo arquivo JavaScript.

```JavaScript
s.dynamicAccountList = "[rsid]=[valuetomatch],[rsid2]=[valuetomatch]";
```

A entrada válida é uma lista separada por ponto e vírgula de pares de rsid e valor. Cada lista contém os seguintes itens:

* Uma ou mais IDs do conjunto de relatórios (separadas por vírgulas)
* Um sinal de igual
* Uma ou mais cadeias de caracteres para corresponder (separadas por vírgulas)

Somente caracteres ASCII padrão devem ser usados na cadeia de caracteres. Não inclua espaços.

## Exemplos

Em todos os exemplos a seguir, o URL da página é `https://example.com/path2/?prod_id=12345`, a variável `dynamicAccountSelection` é definida como `true`, e a `s_account` variável é definida como `examplersid`.

```js
// In this example, the report suite that receives data is examplersid1.
s.dynamicAccountMatch = "window.location.hostname";
s.dynamicAccountList = "examplersid2=www2.example.com;examplersid1=example.com";

// In this example, the report suite that receives data is examplersid2.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid2=path2;examplersid3=path3";

// In this example, no rules match so it resorts to the default rsid in s_account, examplersid.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid4=path4;examplersid5=path5";
```

## Armadilhas, dúvidas e dicas

* As regras listadas nesta variável são aplicadas em uma ordem da esquerda para a direita. Se a variável `dynamicAccountMatch` corresponder a mais de uma regra, a regra mais à esquerda será usada para determinar o conjunto de relatórios. Como resultado, mova mais genéricas para a direita na lista.
* Se nenhuma regra for correspondente, o conjunto de relatórios padrão em `s_account` será usado.
* Se a página for salva no disco rígido de uma pessoa ou traduzida por um mecanismo de tradução baseado na Web (como as páginas traduzidas do Google), a seleção de conta dinâmica provavelmente não funcionará.
* As regras `dynamicAccountSelection` se aplicam à seção do URL especificada em `dynamicAccountMatch`.
* Use o [!DNL Adobe Experience Cloud Debugger] para testar o conjunto de relatórios de destino.
