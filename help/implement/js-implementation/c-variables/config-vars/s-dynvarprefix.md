---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

A variável permite a implantação de variáveis de sinalização que devem ser preenchidas dinamicamente.

Os cookies, cabeçalhos de solicitação e parâmetros da string de consulta da imagem estão disponíveis para preenchimento dinâmico.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/D | D= | Qualquer | D= |

## Sintaxe e valores possíveis

```js
s.prop1="D=User-Agent"
```

OU USE SINALIZAÇÃO PERSONALIZADA PARA VARIÁVEIS DINÂMICAS

```js
s.dynamicVariablePrefix=".."
```

## Exemplos

```js
s.prop1="D=User-Agent"
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
