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


# marketing

A variável usada com mais frequência para identificar uma seção do site.


<!-- 

channel.xml

 -->

Por exemplo, um vendedor pode ter seções como Eletrônicos, Brinquedos ou Vestuário. Um site de mídia pode ter seções como Notícias, Esportes ou Negócios.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 100 bytes | CH | Conteúdo do site &gt; Seções do site | "" |

A Adobe recomenda preencher a variável de canal em todas as páginas. Você também pode ativar uma correlação entre as variáveis *`channel`* e [!UICONTROL page name].

Quando as seções têm um ou mais níveis de subseções, é possível exibir essas seções na variável *`channel`* ou usar variáveis separadas para identificar esses níveis.

**Sintaxe e valores possíveis**

```js
s.channel="value"
```

A variável *`channel`* não tem limitações extras em seus valores.

**Exemplos** {#section_2527B2BB1CFD46CB952178ABF7A9028A}

```js
s.channel="Electronics"
```

```js
s.channel="Media"
```

**Armadilhas, dúvidas e dicas** {#section_61941D5E4E644B59A267A4F44FD5DE8C}

Se o site contiver vários níveis, é possível usar *`hierarchy`* ou outra variável para designar esses níveis. O valor *`channel`* não persiste, mas os eventos bem-sucedidos acionados na mesma página são atribuídos ao valor *`channel`*.
