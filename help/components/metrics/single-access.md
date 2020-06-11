---
title: Acesso único
description: O número de vezes que um valor de dimensão não foi alterado em uma visita.
translation-type: tm+mt
source-git-commit: 52e00470df0f0c6bff84b26c1548e64ff5114fb8
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 0%

---


# Acesso único

A métrica &#39;Acesso único&#39; mostra o número de visitas em que o valor da dimensão continha apenas um único valor exclusivo para toda a visita. Essa métrica é útil no contexto de qualquer dimensão em que você deseja ver quais valores de dimensão estagnam durante uma visita.

## Como essa métrica é calculada

Essa métrica conta visitas nas quais o valor da dimensão continha um único valor exclusivo. Você pode definir o valor da dimensão várias vezes ou mantê-lo e ainda contar como um único acesso. Assim que um valor de dimensão muda para um segundo valor exclusivo, a visita não se qualifica mais como um único acesso.

## Diferença entre &quot;Acesso único&quot; e &quot;Visita de página única&quot;

No contexto da dimensão [Página](../dimensions/page.md) , &quot;Acesso único&quot; e &quot;Visitas únicas à página&quot; são exatamente idênticos. As diferenças surgem quando se usam outras dimensões.

* **Acesso**&#x200B;único: Mostra o número de visitas nas quais o valor de dimensão especificado não foi alterado para toda a visita. É contextual à dimensão usada no projeto.
* **Visita**&#x200B;única à página: Mostra o número de visitas nas quais a dimensão &#39;Página&#39; não foi alterada para toda a visita. Mesmo que você use outra dimensão em seu relatório, ainda contará visitas que contêm um único valor de dimensão &quot;Página&quot; exclusivo.

Por exemplo, considere o exemplo a seguir de duas visitas de ocorrência. A dimensão em seu relatório é a seção [](../dimensions/site-section.md)Site.

* Um visitante acessa duas páginas, mas ambas estão na mesma seção do site. Como a seção do site permaneceu a mesma durante a visita, conta como um único acesso. Ele não conta como uma visita de página única porque a visita contém mais de um valor de dimensão de Página exclusivo.
* Um visitante acessa duas páginas em diferentes seções do site, mas acontece que ambas sejam nomeadas da mesma forma. A visita não conta como um único acesso porque havia dois valores únicos de seção do site. Ele conta como uma visita de página única porque havia um único valor de dimensão de Página exclusiva.
