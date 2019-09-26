---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

A variável permite a implantação de variáveis de sinalização que devem ser preenchidas dinamicamente.

Os cookies, cabeçalhos de solicitação e parâmetros da string de consulta da imagem estão disponíveis para preenchimento dinâmico.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | D= | Qualquer | D= |

## Sintaxe e valores possíveis

```js
s.prop1="D=User-Agent”
```

OU USE SINALIZAÇÃO PERSONALIZADA PARA VARIÁVEIS DINÂMICAS

```js
s.dynamicVariablePrefix=".."
```

## Exemplos

```js
s.prop1="D=User-Agent”
```

OU USE SINALIZAÇÃO PERSONALIZADA PARA VARIÁVEIS DINÂMICAS

```js
s.dynamicVariablePrefix=".."
```

```js
s.prop1="..User-Agent"
```

## Armadilhas, dúvidas e dicas

* As variáveis dinâmicas podem ser usadas para reduzir significativamente o tamanho total do URL, copiando valores em outras variáveis.

* As variáveis dinâmicas podem ser usadas para coletar dados de cabeçalhos e cookies não disponíveis de outra forma na coleta de dados.
