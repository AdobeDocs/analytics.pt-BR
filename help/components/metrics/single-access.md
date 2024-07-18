---
title: Acesso único
description: O número de vezes que um item de dimensão não foi alterado em uma visita.
feature: Metrics
exl-id: 973ce835-9d6f-4ead-90c9-0b80aac82cc0
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 93%

---

# Acesso único

A [métrica](overview.md) de &quot;Acesso único&quot; mostra o número de visitas em que o item de dimensão continha apenas um único valor único para toda a visita. Essa métrica é útil no contexto de qualquer dimensão em que você quer ver quais itens de dimensão estagnaram durante uma visita.

## Como essa métrica é calculada

Essa métrica conta visitas em que o item de dimensão continha um único valor único. É possível definir o item de dimensão várias vezes ou mantê-lo e ainda contar como um único acesso. Assim que um item de dimensão mudar para um segundo valor único, a visita não se qualifica mais como um único acesso.

## Diferença entre &quot;Acesso único&quot; e &quot;Visita em única página&quot;

No contexto da dimensão [Página](../dimensions/page.md), o &quot;Acesso único&quot; e as &quot;Visitas em única página&quot; são exatamente idênticos. As diferenças surgem quando se utilizam outras dimensões.

* **Acesso único**: mostra o número de visitas em que determinado item de dimensão não foi alterado em toda a visita. É contextual à dimensão utilizada no projeto.
* **Visita em única página**: mostra o número de visitas em que a dimensão “Página&#39;” não foi alterada em toda a visita. Mesmo se outra dimensão for utilizada no relatório, ainda serão contabilizadas visitas com um único item de dimensão “Página”.

Por exemplo, considere o exemplo a seguir como visitas com duas ocorrências. A dimensão do relatório é a [Seção do site](../dimensions/site-section.md).

* Um visitante acessa duas páginas, mas ambas estão na mesma seção do site. Como a seção do site permaneceu a mesma durante a visita, é contabilizado um Acesso único. Não conta como uma Visita em única página porque a visita contém mais do que um item único de dimensão Página.
* Um visitante acessa duas páginas em seções diferentes do site, mas ambas têm o mesmo nome. A visita não conta como um Acesso único porque havia dois valores específicos de seção do site. Conta como uma Visita em única página porque havia um único item exclusivo de dimensão Página.
