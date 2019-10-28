---
description: Usando adobe.com como exemplo, as implementações descritas aqui fazem referência ao mesmo cookie visid.
keywords: Implementação do Analytics
seo-description: Usando adobe.com como exemplo, as implementações descritas aqui fazem referência ao mesmo cookie visid.
seo-title: Exemplo de implementação
solution: Analytics
title: Exemplo de implementação
topic: Desenvolvedor e implementação
uuid: 17d8d2b2-2303-495a-b0f9-d8d3c05f3893
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Exemplo de implementação

Usando adobe.com como exemplo, as implementações descritas aqui fazem referência ao mesmo cookie visid.

**JavaScript:**

```js
var s_account="omniturecom" 
s.visitorNamespace="omniture" 
s.trackingServer="omniture.112.2o7.net"
```

**Solicitação de imagem codificada:**

```
<img border="0" alt="" src="https://omniture.112.2o7.net/b/ss/omniturecom/5?ns=omniture" width="1" height="1" /> 
```

**Appmeasurement:**

```js
s.account="omniturecom"; 
s.visitorNamespace="omniture"; 
s.trackingServer="omniture.112.2o7.net";
```

E se cookies primários forem usados:

**JavaScript:**

```js
var s_account="omniturecom" 
s.visitorNamespace"omniture" 
s.trackingServer="metrics.omniture.com"
```

**Solicitação de imagem codificada:**

```
<img border="0" alt="" src="https://metrics.omniture.com/b/ss/omniturecom/5" width="1" height="1" />
```

**Appmeasurement:**

```js
s.account="omniturecom"; 
s.visitorNamespace="omniture"; 
s.trackingServer="metrics.omniture.com";
```

