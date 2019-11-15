---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicAccountList

> [!NOTE] A `s.dynamicAccountList` variável não é suportada nas bibliotecas [AppMeasurement](../../c-appmeasurement-js/appmeasure-mjs.md)atuais. Ela é usada somente no AppMeasurement herdado, como o Código H.

A `s.dynamicAccountList` variável é usada para ajudar a determinar dinamicamente um conjunto de relatórios para o qual enviar dados. É usado em conjunto com as variáveis `dynamicAccountSelection` e `dynamicAccountMatch` . The rules in `dynamicAccountList` are applied if `dynamicAccountSelection` is set to `true`, and they apply to the section of the URL specified in `dynamicAccountMatch`.

## Sintaxe e valores possíveis

```JavaScript
s.dynamicAccountList="rs1[,rs2]=domain1.com[,domain2.com/path][;...]";
```

A entrada válida é uma lista separada por ponto-e-vírgula de pares de nome=valor (regras). Cada lista contém os seguintes itens:

* Uma ou mais IDs de conjunto de relatórios (separadas por vírgulas)
* Um sinal de igual
* Um ou mais filtros de URL (separados por vírgulas)

Somente caracteres ASCII padrão devem ser usados na string (sem espaços).

## Exemplos

Para todos os exemplos a seguir, o URL da página é `https://example.com/path2/?prod_id=12345`, a `dynamicAccountSelection` variável é definida como `true`e a `s_account` variável é definida como `examplersid`.

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

* As regras listadas nesta variável são aplicadas em uma ordem da esquerda para a direita. If the `dynamicAccountMatch` variable matches more than one rule, the left-most rule is used to determine the report suite. Como resultado, coloque regras mais genéricas à direita da lista.
* If no rules match, the default report suite in `s_account` is used.
* Se sua página for salva no disco rígido de alguém ou traduzida por um mecanismo de tradução baseado na Web (como as páginas traduzidas do Google), a seleção da conta dinâmica provavelmente não funcionará.
* As regras `dynamicAccountSelection` se aplicam à seção do URL especificada em `dynamicAccountMatch`.
* Use the [!DNL Adobe Experience Cloud Debugger] to test the destination report suite.
