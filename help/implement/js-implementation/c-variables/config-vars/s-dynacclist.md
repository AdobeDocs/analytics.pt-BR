---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicAccountList

> [!NOTE] A variável `s.dynamicAccountList` não é compatível com as bibliotecas [AppMeasurement](../../c-appmeasurement-js/appmeasure-mjs.md) atuais. Ela é usada somente no AppMeasurement herdado, como o Código H.

A variável `s.dynamicAccountList` é usada para ajudar a determinar dinamicamente um conjunto de relatórios para o qual enviar dados. É usada em conjunto com as variáveis `dynamicAccountSelection` e `dynamicAccountMatch`. As regras em `dynamicAccountList` são aplicadas se `dynamicAccountSelection` estiverem definidos como `true` e se aplicam à seção do URL especificado em `dynamicAccountMatch`.

## Sintaxe e valores possíveis

```JavaScript
s.dynamicAccountList="rs1[,rs2]=domain1.com[,domain2.com/path][;...]";
```

Uma entrada válida é uma lista de pares nome=valor (regras) separada por ponto e vírgula. Cada lista contém os seguintes itens:

* Uma ou mais IDs do conjunto de relatórios (separadas por vírgulas)
* Um sinal de igual
* Um ou mais filtros de URL (separados por vírgulas)

Somente caracteres ASCII padrão devem ser usados na string (sem espaços).

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
