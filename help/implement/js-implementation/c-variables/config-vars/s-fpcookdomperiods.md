---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# s.fpCookieDomainPeriods

A variável é para cookies definidos pelo JavaScript (s_sq, s_cc, plug-ins) que são inerentemente cookies primários, mesmo se a implementação do usar os domínios 2o7.net ou omtrdc.net de terceiros.

A variável *`fpCookieDomainPeriods`* nunca deve ser definida dinamicamente. Se você usar *`cookieDomainPeriods`*, é uma boa prática especificar um valor para *`fpCookieDomainPeriods`* também. *`fpCookieDomainPeriods`* herda o valor *`cookieDomainPeriods`*. Observe que *`fpCookieDomainPeriods`* não afeta o domínio em que o cookie da ID de visitante está definido, mesmo se a implementação tratá-lo como um cookie prórprio.

O nome "*`fpCookieDomainPeriods`*" se refere ao número de pontos (".") no domínio quando este começa com www. Por exemplo, `www.mysite.com` contém dois pontos, enquanto `www.mysite.co.jp` contém três pontos. Outra maneira de descrever a variável é o número de seções no domínio principal do site (dois para `mysite.com` e três para `mysite.co.jp`).

O [!DNL AppMeasurement] para arquivo JavaScript usa a variável *`fpCookieDomainPeriods`* para determinar o domínio com o qual você deve definir cookies próprios diferentes do cookie da [!UICONTROL ID de visitante] (s_vi). There are at least two cookies affected by this variable, including `s_sq` and `s_cc` (used for visitor click map and cookie checking respectively). Os cookies usados pelos plug-ins como [!UICONTROL getValOnce] também são afetados.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
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

Espera-se que a variável *`cookieDomainPeriods`* seja uma string, como mostrado abaixo.

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

Nenhum
