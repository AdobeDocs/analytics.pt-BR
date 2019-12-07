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


# s_objectID

A variável é uma variável global e deve ser definida no evento [!UICONTROL onClick] de um link.


<!-- 

s_objectID.xml

 -->

Ao criar uma única ID de objeto para um link ou localização de link em uma página, é possível melhorar o rastreamento de atividade do usuário ou usar o [!UICONTROL Activity Map] para fazer um relatório sobre o tipo ou a localização de link, em vez do URL do link.

> [!NOTE] É necessário um ponto e vírgula (;) ao usar s_objectID com o [Activity Map](https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/activitymap-link-tracking-use-case.html).

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 100 bytes | OID | [!UICONTROL Activity Map], [!UICONTROL ClickMap] | A URL absoluta de um link clicado |

Há três motivos comuns para usar *`s_objectID`*:

* Para agregar a atividade do visitante que é alterada durante o dia.
* Para separar a atividade do link combinada pelo [!UICONTROL Activity Map].
* Para aprimorar a precisão dos relatórios de dados do [!UICONTROL Activity Map].

**Agregar cliques em links altamente dinâmicos** {#section_BA730A0393B149DDBCAA272C3C23A1C5}

Se o site for extremamente dinâmico e os links em algumas páginas forem alterados durante o dia, *`s_objectID`* poderá ser usado para identificar o local de um link na página. Se *`s_objectID`* estiver definido como "parte superior esquerda 1" ou "parte superior esquerda 2", que representa o primeiro link na parte superior esquerda da página, por exemplo, todos os links que aparecem nesse local (ou onde *`s_objectID`* estão definidos como o mesmo valor) são reportados juntamente com o mapa de cliques de visitante. Se vocÊ não usar *`s_objectID`*, verá o número de vezes que um link foi clicado, mas perderá o insight sobre como todos os outros links desse local foram usados pelos visitantes do site.

**Clique separados combinados** {#section_1AE91FB8A2D3423CBE064ACF02FEEA47}

Se a variável *`pageName`* do site for usada para mostrar a seção ou o modelo que um visitante está visualizando, em vez da página específica que o visitante está visualizando, você pode usar *`s_objectID`* para separar os links que aparecem em várias versões desse modelo de página. Por exemplo, se você tiver um modelo de página para todos os produtos do seu site, provavelmente há um link para sua homepage e para a caixa de pesquisa desse modelo em todas as páginas. Se você quiser ver como esses links são usados em uma base de produtos individuais (em vez de uma base de modelo), poderá preencher *`s_objectID`* com valor do produto específico, como "prod 123789 página inicial" ou "prod 123789 pesquisa". Após a conclusão, o [!UICONTROL Activity Map] emite relatórios sobre os links em relação a cada produto.

**Melhore a[!UICONTROL Precisão do Activity Map]** {#section_08B3406821294DCCABEEB99C90CF5C52}

Em alguns casos, os navegadores diferentes do Internet Explorer, Firefox, Netscape, Opera e Safari não são suportados. Embora seja um percentual pequeno, ele conta para alguns cliques e outras métricas. Use *`s_objectID`* nos links para identificar unicamente os endereços do navegador que relata o problema. Este é um exemplo de como atualizar seus links para usar a *`s_objectID`*:

```js
<a href="/art.jsp?id=559" onClick="s_objectID='top left 1';">Article 559</a> 
<a href="/home.jsp" onClick="s_objectID='prod 123789 home page';">Home</a> 
```

**Sintaxe e valores possíveis** {#section_85841DF9F06A4680953D9B2A884A1A5A}

s_objectID pode conter qualquer identificador de texto.

```js
s_objectID="unique_id" 
```

Não há limitações nas variáveis *`s_objectID`* além das limitações padrão de variáveis.

**Exemplos** {#section_33F119D532CA4ACAA3426253C42030BB}

```js
s_objectID="top left 2" 
```

```js
s_objectID="prod 123789 search"
```

**Configurações** {#section_95396657D55B41ECB66B83D0534EA827}

Nenhum
