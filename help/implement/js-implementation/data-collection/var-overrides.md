---
description: As substituições de variáveis permitem alterar um valor de variável por um único rastreamento ou chamada de link de rastreamento.
keywords: Implementação do Analytics
seo-description: As substituições de variáveis permitem alterar um valor de variável por um único rastreamento ou chamada de link de rastreamento.
seo-title: Substituições de variáveis
solution: Analytics
subtopic: Variáveis
title: Substituições de variáveis
topic: Desenvolvedor e implementação
uuid: 3 ec 09 ae 8-b 9 df -426 f -8065-42 b 4518 e 6 c 5 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Substituições de variáveis

As substituições de variáveis permitem alterar um valor de variável por um único rastreamento ou chamada de link de rastreamento.

To override variables, create a new object, assign variable values, and pass this object as the first parameter to `s.t()`, or as the fourth parameter to `s.tl()`:

```js
s.eVar1="one"; 
s.eVar2="two"; 
s.eVar3="three"; 
  
overrides = new Object(); 
overrides.eVar1="1_one"; 
overrides.eVar2=""; 
  
s.t(overrides);  
// values passed: eVar1="1_one", eVar2="", eVar3="three"
```

```js
s.linkTrackVars="eVar1,eVar2,eVar3,events"; 
s.eVar1="one"; 
s.eVar2="two"; 
s.eVar3="three"; 
 
overrides = new Object(); 
overrides.eVar1="1_one"; 
overrides.eVar2=""; 
 
s.tl(this,'e','AnotherSite',overrides,'navigate')  
// values passed: eVar1="1_one", eVar2="", eVar3="three"
```

