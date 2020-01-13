---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---



# s.doPlugins

A variável é uma referência para a função   e permite que a função   seja chamada no local adequado dentro do arquivo JavaScript.

A função *`s_doPlugins`* é chamada sempre que uma das situações a seguir ocorrer:

* A função *`t()`* é chamada
* A função *`tl()`* é chamada
* Ocorre um clique em uma saída ou link para download.
* Ocorre um clique em um elemento de página sendo acompanhado pelo mapa de cliques do visitante

A variável  *`doPlugins`*&#x200B;é usada para executar rotinas e reunir ou alterar dados. Se você estiver usando um nome de objeto diferente de "s", verifique se *`s_doPlugins`* é renomeado corretamente. Por exemplo, se o nome do objeto for s_mc, a função *`s_doPlugins`* deverá ser chamada de s_mc_doPlugins.

## Sintaxe e valores possíveis

A função *`s_doPlugins`* não deve estar entre aspas e *`doPlugins`* deve ser sempre atribuída ao nome exato da função *`s_doPlugins`* (se essa função for renomeada).

```js
s.doPlugins=s_doPlugins;
```

## Exemplos

```js
s.doPlugins=s_doPlugins;
```

```js
s_mc.doPlugins=s_mc_doPlugins;
```

## Configurações

Nenhum

## Armadilhas, dúvidas e dicas

* O único motivo para alterar o nome do objeto (como de s para s_mc) é se você compartilhar conteúdo ou receber conteúdo de outros clientes. A renomeação da função  A função *`s_doPlugins`* para [!UICONTROL s_mc_doPlugins] garante que outro arquivo JavaScript do cliente não substitua sua função *`doPlugins`*.

* Se você começar a receber conteúdo de outro cliente da Adobe inesperadamente e sua função *`s_doPlugins`* estiver sendo substituída, é possível simplesmente renomear a função *`s_doPlugins`* sem alterar o nome do objeto. Embora a melhor solução seja usar um nome de objeto diferente de outros arquivos JavaScript na mesma página, isso não é obrigatório.
