---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.fpCookieDomainPeriods

A variável é para cookies definidos pelo JavaScript (s_sq, s_cc, plug-ins) que são inerentemente cookies primários, mesmo se a implementação do usar os domínios 2o7.net ou omtrdc.net de terceiros.

The *`fpCookieDomainPeriods`* variable should never be dynamically set . Se você usar *`cookieDomainPeriods`*, é uma boa prática especificar um valor para *`fpCookieDomainPeriods`* também. *`fpCookieDomainPeriods`* herda o *`cookieDomainPeriods`* valor. Note that *`fpCookieDomainPeriods`* does not affect the domain on which the visitor ID cookie is set, even if your implementation treats this as a first-party cookie.

The name " *`fpCookieDomainPeriods`*" refers to the number of periods (".") no domínio quando este começa com www. For example, `www.mysite.com` contains two periods, while `www.mysite.co.jp` contains three periods. Another way to describe the variable is the number of sections in the main domain of the site (two for `mysite.com` and three for `mysite.co.jp`).

O arquivo [!DNL AppMeasurement] para JavaScript usa a *`fpCookieDomainPeriods`* variável para determinar o domínio com o qual definir cookies primários diferentes do cookie da ID [!UICONTROL do] visitante (s_vi). There are at least two cookies affected by this variable, including `s_sq` and `s_cc` (used for visitor click map and cookie checking respectively). Os cookies usados pelos plug-ins como [!UICONTROL getValOnce] também são afetados.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | cookieDomainPeriods |

## Exemplo de código para definir variáveis de domínio do cookie

```js
s.fpCookieDomainPeriods="2" 
var d=window.location.hostname 
if(d.indexOf('.co.uk')>-1||d.indexOf('.com.au')>-1) 
  s.fpCookieDomainPeriods="3" 
```

## Sintaxe e valores possíveis

A sintaxe de variável *`cookieDomainPeriods`* seja uma string, como mostrado abaixo.

```js
s.fpCookieDomainPeriods="3"
```

## Exemplos

```js
s.fpCookieDomainPeriods="3"
```

```js
s.fpCookieDomainPeriods="2"
```

## Configurações

Nenhuma