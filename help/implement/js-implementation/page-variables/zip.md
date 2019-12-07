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


# zip

As variáveis e são variáveis de conversão.


<!-- 

zip.xml

 -->

Elas são semelhantes a eVars, pois capturam eventos capture, mas diferente das eVars, não persistem. A variável *`zip`* são semelhantes a *`state`* eVars, pois expiram imediatamente.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 50 bytes | zip | Conversão &gt; Perfil do visitante &gt; CEP/Códigos postais | "" |

Since the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events fired on the same page that are populated. Por exemplo, se estiver usando o *`zip`* para comparar taxas de conversão por código postal, você deve preencher o *`zip`* em cada página do processo de finalização. A Adobe recomenda usar o endereço de cobrança como fonte para o CEP. Você pode optar pelo endereço de entrega (supondo que haja apenas um endereço de entrega para o pedido). Um site de mídia pode ser escolhido para usar *`zip`* para registro ou *`state`* rastreamento de click-throughs no anúncio.

**Sintaxe e valores possíveis** {#section_5EDCFCAC8FC241D1B4CC777996858CD7}

```js
s.zip="zip_code"
```

A variável *`zip`* não impõe restrições de valor ou formato. Não há limitações nas variáveis *`zip`* além das limitações padrão de variáveis.

**Exemplos** {#section_F25C0D0CC3C04B81892A662CD605C593}

```js
s.zip="92806"
```

```js
s.zip="92806-4115"
```

**Configurações** {#section_7987084EECC34DD38B643B94F82385CA}

Nenhum

**Armadilhas, dúvidas e dicas** {#section_E86774D5CE8B40EFA36353CDEE3A84D0}

* Preencha [!UICONTROL zip] em cada página em que um evento relevante é acionado (cada página do processo de finalização).
* *`zip`* As *`state`* variáveis cep e estado atuam como eVars que expiram na Exibição da página.

