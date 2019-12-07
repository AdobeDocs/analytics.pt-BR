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



# Propriedades de lista

As list props são uma lista de valores delimitados que são passados para uma variável e, em seguida, reportados como itens individuais. A list prop é implementada normalmente em páginas que contenham valores selecionáveis pelo usuário, como itens listados com caixas de seleção ou botões de opção. Elas são úteis em qualquer circunstância em que você deseje definir vários valores em uma variável sem enviar várias solicitações de imagem.


<!-- 

list_props.xml

 -->

**Considerações**

* Propriedades de lista são habilitados somente em variáveis de tráfego ( [props](/help/implement/js-implementation/page-variables/propn.md)).
* Não é possível ativar definição de caminho e correlações para as props de lista.
* O Analytics oferece visitas e visitantes exclusivos em quase todos os relatórios, incluindo todos os relatórios de prop de lista.
* Classificações são suportadas para propriedades de lista.
* Qualquer variável de tráfego personalizado pode se tornar um pro de lista. (Exceções: [pageName](/help/implement/js-implementation/page-variables/pagename.md), [canal](/help/implement/js-implementation/page-variables/channel.md) e [servidor](/help/implement/js-implementation/page-variables/server.md).)

* Na definição de valores duplicados na mesma solicitação de imagem, não ocorre cancelamento de duplicatas nas instâncias.

Um prop pode ser alterado na lista de propriedades, em Ferramentas administrativas &gt; Report Suite &gt; página Variáveis de tráfego, habilitando o Suporte à lista e selecionando o delimitador. Os delimitadores populares são dois pontos, ponto e vírgula, vírgulas ou barra vertical. Tecnicamente, pode ser qualquer um dos primeiros 127 caracteres ASCII.

**Exemplos de implementação**

Ao solicitar a habilitação de propriedades de lista, indique o delimitador que deseja usar. Depois que o *`s.prop`* de sua escolha estiver habilitado, vários valores podem ser definidos na variável, como é mostrado nos exemplos a seguir:

Um list prop delimitado por uma barra vertical, passando em dois valores:

```js
s.prop1="Banner ad impression|Sidebar impression"
```

Um list prop delimitado por uma vírgula, passando em vários valores:

```js
s.prop2="cerulean,vermilion,saffron"
```

Propriedades de lista também podem ser enviados com um único valor:

```js
s.prop3="Single value"
```

O delimitador pode ser alterado a qualquer momento. Contudo, a implementação deve corresponder ao novo delimitador. A falha ao utilizar o delimitador correto resulta que o valor do list prop é tratado como um item de linha único concatenado no relatório.

Como a prop de lista ainda é uma variável de tráfego, está sujeita às limitações das Variáveis de tráfego. As props de lista estão limitadas a 100 bytes de dados e são afetadas pelas configurações de diferenciação de maiúsculas e minúsculas.

