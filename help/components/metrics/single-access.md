---
title: Acesso único
description: O número de vezes que um item de dimensão não foi alterado em uma visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 0%

---


# Acesso único

A métrica &#39;Acesso único&#39; mostra o número de visitas nas quais o item de dimensão continha apenas um único valor exclusivo para toda a visita. Essa métrica é útil no contexto de qualquer dimensão em que você deseja ver quais itens de dimensão estagnaram durante uma visita.

## Como essa métrica é calculada

Essa métrica conta visitas nas quais o item de dimensão continha um único valor exclusivo. Você pode definir o item de dimensão várias vezes ou mantê-lo e ainda contar como um único acesso. Assim que um item de dimensão muda para um segundo valor exclusivo, a visita não se qualifica mais como um único acesso.

## Diferença entre &quot;Acesso único&quot; e &quot;Visita de página única&quot;

No contexto da dimensão [Página](../dimensions/page.md) , &quot;Acesso único&quot; e &quot;Visitas únicas à página&quot; são exatamente idênticos. As diferenças surgem quando se usam outras dimensões.

* **Acesso**&#x200B;único: Mostra o número de visitas nas quais um determinado item de dimensão não foi alterado para toda a visita. É contextual à dimensão usada no projeto.
* **Visita**&#x200B;única à página: Mostra o número de visitas nas quais a dimensão &#39;Página&#39; não foi alterada para toda a visita. Mesmo que você use outra dimensão em seu relatório, ainda contará visitas que contêm um único item de dimensão &quot;Página&quot; exclusivo.

Por exemplo, considere o exemplo a seguir de duas visitas de ocorrência. A dimensão em seu relatório é a seção [](../dimensions/site-section.md)Site.

* Um visitante acessa duas páginas, mas ambas estão na mesma seção do site. Como a seção do site permaneceu a mesma durante a visita, conta como um único acesso. Ele não conta como uma visita de página única porque a visita contém mais de um item de dimensão de Página exclusivo.
* Um visitante acessa duas páginas em diferentes seções do site, mas acontece que ambas sejam nomeadas da mesma forma. A visita não conta como um único acesso porque havia dois valores únicos de seção do site. Ele conta como uma visita de página única porque havia um único item de dimensão de Página exclusivo.
