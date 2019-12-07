---
description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
keywords: Analytics Implementation
subtopic: Variables
title: Variáveis de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# state

As variáveis e são variáveis de conversão.


<!-- 

state.xml

 -->

Elas são semelhantes a eVars, pois capturam eventos capture, mas diferente das eVars, não persistem. A variável *`zip`* são semelhantes a *`state`* eVars, pois expiram imediatamente.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 50 bytes | state | Conversão &gt; Perfil do visitante &gt; Estado do visitante | "" |

Como as variáveis *`state`* e *`zip`* expiram imediatamente, os únicos eventos associados a elas são eventos que são acionados na mesma página em que são preenchidos. Por exemplo, se estiver usando *`state`* para comparar as taxas de conversão por estado, você de preencher a variável *`state`* em cada página do processo de finalização. Para sites de conversão, a Adobe recomenda usar o endereço de cobrança como fonte do código, mas você pode optar por usar o endereço de entrega (supondo que exista apenas um endereço de entrega para o pedido). Um site de mídia pode ser escolhido para usar *`zip`* para registro ou *`state`* rastreamento de click-throughs no anúncio.

**Sintaxe e valores possíveis** {#section_EDD1F5F9EDBC457898E61695F08C1744}

```js
s.state="state"
```

A variável *`state`* não impõe restrições especiais de valor ou formato. Não há limitações nas variáveis *`state`* além das limitações padrão de variáveis.

**Exemplos** {#section_D181B163F79A41D199CA4C70765E583F}

```js
s.state="california" 
```

```js
s.state="prince edward island"
```

**Configurações** {#section_DB0D6DC3F4764AC59C11B10D27D2806C}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_02F1620D0BB14AA6A838966FDB9A234F}

* Preencha *`state`* em todas as páginas em que um evento relevante é acionado (como cada página do processo de finalização).
* As variáveis cep e estado atuam como eVars que expiram na Exibição da página.*`zip`**`state`*
