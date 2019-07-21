---
description: Retorna o valor de um parâmetros da string de consulta especificada, se for encontrada no URL da página atual ou na string fornecida.
keywords: Implementação do Analytics
seo-description: Retorna o valor de um parâmetros da string de consulta especificada, se for encontrada no URL da página atual ou na string fornecida.
seo-title: Util.getQueryParam
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.getQueryParam
topic: Desenvolvedor e implementação
uuid: 1 fasu 148-3 e 52-46 f 2-a 73 f -003563 f 7 a 62 c
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Util.getQueryParam

Retorna o valor de um parâmetros da string de consulta especificada, se for encontrada no URL da página atual ou na string fornecida.

Como os dados importantes (tais como códigos de rastreamento de campanha, palavras-chave de pesquisa interna etc.) estão disponíveis na sequência de caracteres de consulta em uma página, O getQueryParam ajuda a capturar os dados nas variáveis do Analytics.

Esse utilitário substitui [o plug-in getQueryParam](../../implement/js-implementation/plugins/getqueryparam.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF).

**Sintaxe:**

```
s.Util.getQueryParam(key, [url], [delim])
```

>[!NOTE]
>
>A sintaxe do utilitário difere da sintaxe do plug-in.

**Parâmetros:**

| Parâmetro | Descrição |
|---|---|
| key | (obrigatório) O nome do parâmetro da string de consulta que você quer obter. Este parâmetro diferencia maiúsculas de minúsculas. |
| url | (optional) Default url is `s.pageURL` or `window.location`. A especificação de um valor para esse parâmetro substitui a URL de onde o parâmetro de consulta é recuperado para aquele especificado. |
| delim | (opcional) Delimitador de parâmetro no URL. O delimitador padrão é "&amp;". Ele permite especificar um delimitador alternativo para a string de consulta, como ";". |

**Retorna:**

A função retornará uma sequência vazia "se nenhuma chave for fornecida ou se nenhuma das opções de URL existir, ou se a tecla não for encontrada no URL. Se um delimitador de fragmento # for encontrado no URL, tudo o que estiver seguindo o delimitador do fragmento não será considerado. Se a tecla existir e for atribuída a um valor, o URL será decodificado e retornado.

**Exemplo:**

```js
s.doPlugins = function(s) { 
  s.campaign = s.Util.getQueryParam("cid"); 
};
```

