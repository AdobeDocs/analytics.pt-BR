---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---



# s.doPlugins

A variável é uma referência à função e permite que a função seja chamada no local apropriado no arquivo JavaScript.

The *`s_doPlugins`* function is called each time any of the following occurs:

* A *`t()`* função é chamada
* A *`tl()`* função é chamada
* Ocorre um clique em uma saída ou link para download.
* Ocorre um clique em um elemento de página sendo acompanhado pelo mapa de cliques do visitante

A variável *`doPlugins`*&#x200B;é usada para executar rotinas e reunir ou alterar dados. If you are using an object name other than "s," make sure that the *`s_doPlugins`* is renamed appropriately. Por exemplo, se o nome do objeto for s_mc, a *`s_doPlugins`* função deverá ser chamada de s_mc_doPlugins.

## Sintaxe e valores possíveis

A *`s_doPlugins`* função não deve estar entre aspas e *`doPlugins`* deve ser sempre atribuída ao nome exato da *`s_doPlugins`* função (se essa função for renomeada).

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

Nenhuma

## Armadilhas, dúvidas e dicas

* O único motivo para alterar o nome do objeto (como de s para s_mc) é se você compartilhar conteúdo ou receber conteúdo de outros clientes. A renomeação da função *`s_doPlugins`* function to [!UICONTROL s_mc_doPlugins] ensures that another client's JavaScript file does not overwrite your *`doPlugins`* function.

* Se você começar a extrair conteúdo de outro cliente Adobe inesperadamente e sua *`s_doPlugins`* função estiver sendo substituída, será possível simplesmente renomear a *`s_doPlugins`* função sem alterar o nome do objeto. Embora a melhor solução seja usar um nome de objeto diferente de outros arquivos JavaScript na mesma página, isso não é obrigatório.