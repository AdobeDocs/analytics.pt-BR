---
description: Perguntas frequentes sobre o rastreamento de links no Activity Map.
title: Perguntas frequentes sobre o Rastreamento de links
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: b6ccdf91-98ce-413f-842d-c5423598ed49
translation-type: tm+mt
source-git-commit: 56d272b72d3274057668d3b45c416cb7487d56a2
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 47%

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

A identificação de link e região de Activity Map ocorre quando os usuários clicam em uma página.

## O que é rastreado por padrão?

Se um evento de clique ocorrer em um elemento, ele precisará passar por algumas verificações para determinar se o AppMeasurement o tratará como um link. Essas são as verificações:

* Isso é uma tag `A` ou `AREA` com uma propriedade `href`?
* Existe um atributo `onclick` que define uma variável `s_objectID`?
* Isso é uma tag `INPUT` ou um botão `SUBMIT` com um valor ou texto filho?
* Isso é uma tag `INPUT` com o tipo `IMAGE` e uma propriedade `src`?
* Isso é um `BUTTON`?

Se a resposta for Sim para qualquer uma das perguntas acima, então o elemento é tratado como um link e será rastreado.
 
Importante: tags de botão com o atributo type=&quot;button&quot; não são consideradas links por AppMeasurement. Considere remover type=&quot;button&quot; nas tags de botão e, em vez disso, adicione role=&quot;button&quot; ou submit=&quot;button&quot;.
 
Importante: Uma tag de âncora com um &quot;href&quot; que começa com &quot;#&quot; é considerada um local de destino interno pelo AppMeasurement, não um link (já que você não sai da página). Por padrão, o Activity Map não rastreia esses locais de destino internos. Ele rastreia somente links que levam o usuário a uma nova página.

## Como o Activity Map rastreia outros elementos visuais em HTML?

a. Por meio da função `s.tl()` .

Se o clique ocorreu por meio de uma invocação `s.tl()`, o Activity Map também receberá esse evento de clique e determinará se uma variável de sequência de caracteres `linkName` foi encontrada. Durante a execução de `s.tl()`, o linkName será definido como a ID do link Activity Map. O elemento clicado que originou a chamada `s.tl()` será usado para determinar a região. Exemplo:

```
    
<img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
```

b. Com a variável `s_objectID` . Exemplo:

    &quot;
    
    &lt;a>&lt;img>&lt;/a>
    
    &lt;a>Vincular texto aqui&lt;/a>
    
    
    &quot;

Importante:  Observe que é necessário um ponto e vírgula (;) ao usar `s_objectID` no Activity Map.

## Você pode me dar alguns exemplos de links que serão rastreados?

* `<a hef="/home?lang=en>Home</a>`
* `<input type="submit" value="Submit"/>`
* `<input type="image" src="submit-button.png"/>`
* 

```
    <p onclick="var s_objectID='custom link id';">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </p>
```

* 

```
    <div onclick="s.tl(true,'o','custom link id')">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </div>
```

## Você pode me dar alguns exemplos de links que NÃO serão rastreados?

1. Motivo: A tag de âncora não tem um `href` válido:
   `<a name="innerAnchor">Section header</a>`

1. Motivo: a função `s_ObjectID` e a `s.tl()` não estão presentes:

   ```
   <p onclick="showPanel('market rates')">
     <span class="title">Current Market Rates</span>
     <span class="subtitle">1.45USD</span>
   </p>
   ```

1. Motivo: a função `s_ObjectID` e a `s.tl()` não estão presentes:

   ``` 
   <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
   
   ```  
   
1. Motivo: A propriedade &quot;src&quot; não tem um elemento de entrada de formulário:

   `<input type="image"/>`
