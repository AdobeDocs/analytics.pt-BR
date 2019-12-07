---
description: As substituições de variáveis permitem alterar um valor de variável por um único rastreamento ou chamada de link de rastreamento.
keywords: Analytics Implementation
subtopic: Variables
title: Substituições de variável
topic: Developer and implementation
uuid: 3ec09ae8-b9df-426f-8065-42b4518e6c5f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Substituições de variável

As substituições de variáveis permitem alterar um valor de variável por um único rastreamento ou chamada de link de rastreamento.

Para substituir variáveis, crie um novo objeto, atribua os valores da variável e transmita esse objeto como o primeiro parâmetro para `s.t()` ou como oquarto parâmetro para `s.tl()`:

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

