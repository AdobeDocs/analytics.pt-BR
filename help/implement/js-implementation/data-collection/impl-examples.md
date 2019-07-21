---
description: Usando adobe.com como exemplo, as implementações descritas aqui fazem referência ao mesmo cookie visid.
keywords: Implementação do Analytics
seo-description: Usando adobe.com como exemplo, as implementações descritas aqui fazem referência ao mesmo cookie visid.
seo-title: Exemplo de implementação
solution: Analytics
title: Exemplo de implementação
topic: Desenvolvedor e implementação
uuid: 17 d 8 d 2 b 2-2303-495 a-b 0 f 9-d 8 d 3 c 05 f 3893
translation-type: tm+mt
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

