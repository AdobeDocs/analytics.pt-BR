---
description: Perguntas frequentes sobre o rastreamento de links no Activity Map.
title: Perguntas frequentes sobre o Rastreamento de links
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: User, Admin
exl-id: b6ccdf91-98ce-413f-842d-c5423598ed49
source-git-commit: 2a20ce50f773c82856da59154bb212f1fca2b7ea
workflow-type: ht
source-wordcount: '516'
ht-degree: 100%

---

# Perguntas frequentes sobre o Rastreamento de links

Perguntas frequentes sobre o rastreamento de links no Activity Map.

>[!CAUTION]
>
>Ao ativar o rastreamento do Activity Map, **você poderá coletar dados de informações pessoalmente identificáveis (PII).** Tais dados podem ser usados isoladamente ou junto a outras informações para identificar, contactar ou localizar uma pessoa, ou para identificar um indivíduo em um contexto.

Veja a seguir alguns casos conhecidos nos quais dados de PII podem ser coletados usando o Rastreamento do Activity Map:

* `Mailto` links. Um link mailto é um tipo de link HTML que ativa o cliente de email padrão no computador para enviar um email.
* `User ID` links que podem ser exibidos no cabeçalho/rodapé de um site depois que o usuário fizer logon.
* Para instituições financeiras, o número da conta pode ser mostrado como um link. Clicar nele coletará o texto do link.
* Sites de instituições de saúde também podem ter dados de PII mostrados como links. Clicar nesses links coletará o texto do link e, portanto, coletará dados de PII.

## Quando ocorre o rastreamento de links?

A identificação de link e região do Activity Map ocorre quando os usuários clicam em uma página.

## O que é rastreado por padrão?

Se um evento de clique ocorrer em um elemento, este terá de passar por algumas verificações para determinar se o AppMeasurement vai tratá-lo como um link. Estas são as verificações:

* Isso é uma `A` ou uma tag `AREA` com uma propriedade `href`?
* Existe um atributo `onclick` que define uma variável `s_objectID`?
* Isso é uma tag `INPUT` ou um botão `SUBMIT` com um valor ou texto filho?
* Isso é uma tag `INPUT` do tipo `IMAGE` e uma propriedade `src`?
* Isso é um `BUTTON`?

Se a resposta for Sim para qualquer uma das perguntas acima, então o elemento é tratado como um link e será rastreado.

>[!IMPORTANT]
>
>Tags de botão com o atributo type=&quot;button&quot; não são consideradas links pelo AppMeasurement. Considere remover type=&quot;button&quot; nas tags de botão e adicionar role=&quot;button&quot; ou submit=&quot;button&quot;.

>[!IMPORTANT]
>
>Uma tag âncora com uma &quot;href&quot; que começa com &quot;#&quot; é considerada um local de destino interno pelo AppMeasurement, não um link (já que você não sai da página). Por padrão, o Activity Map não rastreia esses locais de destino internos. Ele rastreia somente links que levam o usuário a uma nova página.

## Como o Activity Map rastreia outros elementos visuais em HTML?

a. Por meio da função `s.tl()`.

Se o clique ocorreu por meio de uma invocação `s.tl()`, então o Activity Map também receberá esse evento de clique e determinará se uma variável de sequência de caracteres `linkName` foi encontrada. Durante a execução da `s.tl()`, esse linkName será definido como a ID do link no Activity Map. O elemento clicado que originou a chamada `s.tl()` será utilizado para determinar a região. Exemplo:

```
<img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
```

b. Por meio da variável `s_objectID`. Exemplo:

    ``` 
    
    &lt;img onclick=&quot;s_objectID=&#39;abc&#39;;&quot; src=&quot;someimageurl.png&quot;/>
    &lt;a href=&quot;some-url.html&quot; onclick=&quot;s_objectID=&#39;abc&#39;;&quot; >
    Texto do link aqui
    &lt;/a>
    
    ```

>[!IMPORTANT]
>
>É necessário um ponto e vírgula (;) ao usar `s_objectID` no Activity Map.

## Poderia fornecer alguns exemplos de links que serão rastreados?

### Exemplo 1

```
  <a hef="/home?lang=en>Home</a>
```

### Exemplo 2

```
 <input type="submit" value="Submit"/>
```

### Exemplo 3

```
  <input type="image" src="submit-button.png"/>
```

### Exemplo 4

```
    <p onclick="var s_objectID='custom link id';">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </p>
```

### Exemplo 5

```
    <div onclick="s.tl(true,'o','custom link id')">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </div>
```

## Poderia fornecer alguns exemplos de links que NÃO serão rastreados?

1. Motivo: a tag âncora não tem um `href` válido:
   `<a name="innerAnchor">Section header</a>`

1. Motivo: `s_ObjectID` ou `s.tl()` não estão presentes:

   ```
   <p onclick="showPanel('market rates')">
     <span class="title">Current Market Rates</span>
     <span class="subtitle">1.45USD</span>
   </p>
   ```

1. Motivo: `s_ObjectID` ou `s.tl()` não estão presentes:

   ``` 
   <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
   
   ```  
   
1. Motivo: a propriedade src tem um elemento de entrada de formulário ausente:

   `<input type="image"/>`

