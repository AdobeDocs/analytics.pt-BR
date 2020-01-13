---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicAccountMatch

A variável usa o objeto do DOM com a finalidade de recuperar a seção do URL a qual todas as regras em se aplicam.

Essa variável é válida somente quando *`dynamicAccountSelection`* está definida como "Verdadeiro". Como o valor padrão é [!DNL window.location.host], essa variável não é necessária para que a [!UICONTROL Seleção de Conta Dinâmica] funcione. Para obter mais informações, consulte [dynamicAccountList](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

As regras encontradas em `dynamicAccountList` são aplicadas ao valor de `dynamicAccountMatch`. Se `dynamicAccountMatch` contiver apenas [!DNL window.location.host] (padrão), as regras em `dynamicAccountList` serão aplicadas somente ao domínio da página.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/D | N/D | N/D | window.location.host |

## Sintaxe e valores possíveis

Geralmente, a variável `dynamicAccountMatch` é preenchida pelo consultor da Adobe que fornece o AppMeasurement para o arquivo JavaScript. Entretanto, os valores listados abaixo podem ser aplicados a qualquer momento.

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

Nenhum

## Armadilhas, dúvidas e dicas

* A seleção de conta dinâmica não é compatível com [AppMeasurement para JavaScript](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Quando as páginas são salvas em um disco rígido, [!DNL window.location.host] fica em branco, fazendo com que as exibições de página sejam enviadas para o conjunto de relatórios padrão (em `s_account`).

* Quando a página é traduzida por um mecanismo de tradução baseado na Web, como o Google, a [!UICONTROL Seleção de Conta Dinâmica] não funciona conforme projetado. Para obter um rastreamento mais preciso, preencha o lado do servidor da variável [!UICONTROL s_account].
