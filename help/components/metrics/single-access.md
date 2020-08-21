---
title: Acesso único
description: O número de vezes que um item de dimensão não foi alterado em uma visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 45%

---


# Acesso único

A métrica &#39;Acesso único&#39; mostra o número de visitas nas quais o item de dimensão continha apenas um único valor exclusivo para toda a visita. Essa métrica é útil no contexto de qualquer dimensão em que você deseja ver quais itens de dimensão estagnaram durante uma visita.

## Como essa métrica é calculada

Essa métrica conta visitas nas quais o item de dimensão continha um único valor exclusivo. Você pode definir o item de dimensão várias vezes ou mantê-lo e ainda contar como um único acesso. Assim que um item de dimensão muda para um segundo valor exclusivo, a visita não se qualifica mais como um único acesso.

## Diferença entre &quot;Acesso único&quot; e &quot;Visita em única página&quot;

No contexto da dimensão [Página](../dimensions/page.md), o &quot;Acesso único&quot; e as &quot;Visitas em única página&quot; são exatamente idênticos. As diferenças surgem quando se utilizam outras dimensões.

* **Acesso**&#x200B;único: Mostra o número de visitas nas quais um determinado item de dimensão não foi alterado para toda a visita. É contextual à dimensão utilizada no projeto.
* **Visita em única página**: mostra o número de visitas em que a dimensão “Página&#39;” não foi alterada em toda a visita. Mesmo que você use outra dimensão em seu relatório, ainda contará visitas que contêm um único item de dimensão &quot;Página&quot; exclusivo.

Por exemplo, considere o exemplo a seguir como visitas com duas ocorrências. A dimensão do relatório é a [Seção do site](../dimensions/site-section.md).

* Um visitante acessa duas páginas, mas ambas estão na mesma seção do site. Como a seção do site permaneceu a mesma durante a visita, é contabilizado um Acesso único. Ele não conta como uma visita de página única porque a visita contém mais de um item de dimensão de Página exclusivo.
* Um visitante acessa duas páginas em seções diferentes do site, mas ambas têm o mesmo nome. A visita não conta como um Acesso único porque havia dois valores específicos de seção do site. Ele conta como uma visita de página única porque havia um único item de dimensão de Página exclusivo.
