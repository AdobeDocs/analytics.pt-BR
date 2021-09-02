---
title: s_objectID
description: Ajude o Activity Map a identificar links exclusivos em seu site.
exl-id: 7c0cb750-2bfe-41ca-ab27-30dda4b3a7fa
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '404'
ht-degree: 100%

---

# s_objectID

A variável `s_objectID` fornece um identificador exclusivo para cada link. É usado para tornar os relatórios no [Activity Map](/help/analyze/activity-map/activity-map.md) mais precisos. Se você tiver links em uma página que muda com frequência, é possível usar a variável `s_objectID` para informar ao Activity Map um local de link exclusivo para que ele possa agrupar os dados corretamente, conforme desejado.

Se a precisão do Activity Map for crucial para sua organização, a Adobe recomenda incluir a variável `s_objectID` no evento `onClick` dos links no site. Consulte [Casos de uso do rastreamento de link do Activity Map](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-use-case.md) no Guia do usuário Analisar para obter mais informações.

## ID de objeto usando tags na Adobe Experience Platform

Não há um campo dedicado na interface da Coleção de dados para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s_objectID no AppMeasurement e no editor de código personalizado do 

A variável `s_objectID` é global, o que significa que ela opera independentemente do objeto de rastreamento do Analytics (`s` por padrão). Os valores válidos para essa variável podem ser qualquer string de até 100 bytes de tamanho. Se essa variável não estiver definida, o Activity Map usará o URL do link como identificador desse link.

Normalmente, essa variável é definida no evento `onClick` de um link HTML.

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

>[!NOTE]
>
>Sempre inclua o ponto e vírgula que conclui uma instrução JavaScript. O ponto e vírgula é necessário para que o Activity Map funcione.

## Casos de uso

A variável `s_objectID` é valiosa sempre que você deseja aumentar a precisão nos relatórios do Activity Map.

### Links agregados para conteúdo altamente dinâmico

Alguns sites têm conteúdo altamente dinâmico, como sites de notícias ou sites de varejo com itens em frequente rotação. Como o Activity Map usa o URL do link como um identificador por padrão, é difícil entender as áreas mais clicadas nas páginas em que os links são alterados com frequência. Se você usar o `s_objectID` nesses links, o Activity Map entende quais links podem ser agregados, independentemente dos URLs para os quais eles apontam.

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

Independentemente do local para onde os links apontem ou com que frequência você altera esses links, o Activity Map agrega dados com base no valor em `s_objectID`.

### Manter os links em uma página separados

Alguns sites têm links que apontam para o mesmo local em lugares diferentes. Por exemplo, um link para a página inicial no cabeçalho e no rodapé do site. Como esses links têm o mesmo URL, o Activity Map agrega seus dados. É possível separá-los usando a variável `s_objectID`:

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

Mesmo que os links apontem para o mesmo URL, o Activity Map pode usar a variável `s_objectID` para diferenciá-los corretamente nos relatórios.
