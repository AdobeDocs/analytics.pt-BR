---
description: Usando adobe.com como exemplo, as implementações descritas aqui fazem referência ao mesmo cookie visid.
keywords: Analytics Implementation
title: Exemplo de implementação
topic: Developer and implementation
uuid: 17d8d2b2-2303-495a-b0f9-d8d3c05f3893
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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

