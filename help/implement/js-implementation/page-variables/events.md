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



# Eventos

A variável é usada para registrar eventos bem-sucedidos do carrinho de compras, bem como eventos bem-sucedidos personalizados.


<!-- 

events.xml

 -->

<table id="table_9EB9D08C80544CD68C4B1A2012440472"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamanho máximo </th> 
   <th class="entry"> Parâmetro de depuração </th> 
   <th class="entry"> Relatórios preenchidos </th> 
   <th class="entry"> Valor padrão </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Sem limite </td> 
   <td> events </td> 
   <td> <p>Eventos do carrinho de compras </p> <p>Eventos Personalizados </p> </td> 
   <td> N/D </td> 
  </tr> 
 </tbody> 
</table>

Um [!UICONTROL evento] deve ser considerado um marco em um site. Eventos bem-sucedidos são preenchidos mais frequentemente na página de confirmação final de um processo, como processo de registro ou assinatura de boletins informativos. Os eventos personalizados são definidos com o preenchimento da variável events com valores literais definidos na seção Valores possíveis abaixo.

Por padrão, os eventos bem-sucedidos são configurados como eventos *contadores*. Eventos contadores contam o número de vezes que um evento bem-sucedido foi definido (x + 1). Os eventos também podem ser configurados como *numéricos*. Os eventos numéricos permitem especificar o número de incremento (como pode ser necessário na contagem de valores dinâmicos ou arbitrários, como o número de resultados retornados por uma pesquisa interna).

Um tipo de evento final, *moeda*, permite definir o valor a ser adicionado (semelhante a eventos numéricos), mas é exibido como moeda em relatórios e está sujeito a conversões de moeda com base no valor s. *`currencyCode`* e na configuração padrão de moeda do seu conjunto de relatórios. Para obter informações adicionais sobre o uso de eventos numéricos e de moedas, consulte [Produtos](/help/implement/js-implementation/page-variables/page-variables.md).

**Configuração da variável**

A variável `s.events` é ativada por padrão para todas as implementações. Os sete eventos de conversão pré-configurados são ativados automaticamente para todos os novos conjuntos de relatórios. Qualquer usuário com nível administrativo pode ativar novos eventos personalizados (event1- [event100 ou event1000](/help/implement/js-implementation/page-variables/page-variables.md)) usando o Admin Console.

**Valores possíveis**

A seguir está uma lista de valores possíveis para a variável events:

| Evento | Descrição | Relatórios preenchidos |
|---|---|---|
| prodView | Exibições do produto | Produtos |
| scOpen | Abrir/inicializar um novo carrinho de compras | Carrinhos |
| scAdd | Adicionar itens ao carrinho | Adições ao carrinho |
| scRemove | Remover itens do carrinho | Remoções do carrinho |
| scView | Exibir carrinho de compras | Exibições do carrinho |
| scCheckout | Iniciando o processo de checkout | Finalizações |
| purchase | Conclusão de uma compra (pedido) | Pedidos |
| event1 - event1000 (event100 para um produto pontual) | Eventos personalizados | Eventos Personalizados |

**Sintaxe e exemplos**

Os eventos contadores são definidos com a inserção dos eventos desejados na variável `s.events`, em uma lista separada por vírgulas (se vários eventos forem transmitidos).

```js
s.events="scAdd"
```

```js
s.events="scAdd,event1,event7"
```

```js
s.events="event5"
```

```js
s.events="purchase,event10"
```

Se houver um código H23 ou posterior, os eventos contadores poderão ter inteiros maiores que um atribuídos a eles.

```js
s.events="event1=10"
```

```js
s.events="scRemove=3,event6,event2=4"
```

A implementação de eventos contadores com valores inteiros atribuídos trata os eventos como se eles tivessem sido acionados várias vezes dentro da solicitação de imagem. Os eventos contadores não permitem decimais. É recomendável usar eventos numéricos, caso essa funcionalidade seja necessária.
É necessário incluir os eventos numéricos e de moeda na variável [!UICONTROL s.events], embora eles geralmente recebam seu valor numérico (p. ex. 24,99) na variável [!UICONTROL s.products]. Isso permite especificar valores numéricos e de moeda às entradas individuais de produtos.

**Serialização de eventos**

Por padrão, um evento é contado sempre que é definido no seu site.

Consulte [Serialização de eventos](/help/implement/js-implementation/event-serialization.md) para obter mais informações.

**Sintaxe**

```js
s.events="event1:3167fhjkah"
```

**Exemplos**

```js
s.events="scAdd:003717174"
```

```js
s.events="scAdd:user228197,event1:577247280,event7:P7fhF8571"
```
