---
description: A função s.sa() permite que você altere dinamicamente um conjunto de relatórios a qualquer momento na página, antes ou depois do acionamento de uma solicitação de imagem.
keywords: Analytics Implementation
subtopic: Functions
title: A função s.sa()
topic: Developer and implementation
uuid: a6aacd10-2a5b-448b-b3b7-bed5590b71d4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# A função s.sa()

A função s.sa() permite que você altere dinamicamente um conjunto de relatórios a qualquer momento na página, antes ou depois do acionamento de uma solicitação de imagem.

É recomendável usar essa função se a sua organização deseja enviar dados para conjuntos de relatórios diferentes sem que a página recarregue.

Essas informações são para usuários avançados que conhecem bem os relatórios e a implementação. Não tente editar sua implementação sem conhecer totalmente as consequências. Se for necessário efetuar alterações na implementação, entre em contato com o Gerente de conta da sua organização.

## Propriedades da função {#section_E10CB41A0CF749F4A24C8377958E3671}

A configuração dessa função pega todas as variáveis definidas anteriormente e permite que sejam usadas em um conjunto de relatórios diferente.

## Exemplos de implementação {#section_14B0B8C853244D5F82B08B995773640C}

Como enviar dados de vídeo para um conjunto de relatório ao enviar o resto para outro:

```js
// Set in the core JS file by default 
var s=s_gi('prodrsid'); 
 
// Define this when a user interacts with a video 
s.sa('videorsid'); 
s.t(); // Sends an image request
```

Como usar s.sa() e marcação multiconjuntos:

```js
// Set in the core JS file by default 
var s=s_gi('rsid1'); 
 
// Call the function when you wish to change report suites 
s.sa('rsid1,rsid2'); 
s.t();
```

