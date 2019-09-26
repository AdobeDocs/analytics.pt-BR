---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountMatch

A variável usa o objeto do DOM com a finalidade de recuperar a seção do URL a qual todas as regras em se aplicam.

This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' Como o valor padrão é [!DNL window.location.host], essa variável não é necessária para que a [!UICONTROL Seleção de Conta Dinâmica] funcione. For additional information, see [dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

As regras encontradas em `dynamicAccountList` são aplicadas ao valor de `dynamicAccountMatch`. Se `dynamicAccountMatch` contiver apenas [!DNL window.location.host] (padrão), as regras em `dynamicAccountList` serão aplicadas somente ao domínio da página.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | window.location.host |

## Sintaxe e valores possíveis

A sintaxe de variável `dynamicAccountMatch` geralmente é preenchida pelo consultor da Adobe que fornece o AppMeasurement para o arquivo JavaScript. Entretanto, os valores listados abaixo podem ser aplicados a qualquer momento.

```js
s.dynamicAccountMatch=[DOM object]
```

| Descrição | Valor |
|---|---|
| Domínio (padrão) | window.location.host |
| Caminho | window.location.pathname |
| String de consulta | (window.location.search?window.location.search:"?") |
| Domínio e caminho | window.location.host+window.location.pathname |
| Caminho e string de consulta | window.location.pathname+(window.location.search?window.location.search:"?") |
| URL completo | window.location.href |

## Exemplos

```js
s.dynamicAccountMatch=window.location.pathname
```

```js
s.dynamicAccountMatch=window.location.host+window.location.pathname
```

## Configurações

Nenhuma

## Armadilhas, dúvidas e dicas

* A seleção de conta dinâmica não é suportada pelo [AppMeasurement para JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Quando as páginas são salvas em um disco rígido, [!DNL window.location.host] fica em branco, fazendo com que as exibições de página sejam enviadas para o conjunto de relatórios padrão (em `s_account`).

* Quando a página é traduzida por um mecanismo de tradução baseado na Web, como o Google, a [!UICONTROL Seleção de Conta Dinâmica] não funciona conforme projetado. Para obter um rastreamento mais preciso, preencha o lado do servidor da variável [!UICONTROL s_account].
