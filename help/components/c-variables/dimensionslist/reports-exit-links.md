---
description: Mostra os links mais comuns que são clicados pelas pessoas e levam a lugares fora de seu site. Normalmente, esses links indicam sites de parceiros ou afiliados. Contudo, podem ser qualquer local em que você tenha implementado um link externo. Você pode usar esse relatório para visualizar os links afiliados mais populares, ou para ajudar a validar o número de referências que seus parceiros afirmam receber de você.
seo-description: Mostra os links mais comuns que são clicados pelas pessoas e levam a lugares fora de seu site. Normalmente, esses links indicam sites de parceiros ou afiliados. Contudo, podem ser qualquer local em que você tenha implementado um link externo. Você pode usar esse relatório para visualizar os links afiliados mais populares, ou para ajudar a validar o número de referências que seus parceiros afirmam receber de você.
seo-title: Links de saída
solution: Analytics
title: Links de saída
topic: 'Relatórios  '
uuid: e 1452 f 04-389 d -4 aa 3-8763-732880284302
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Links de saída

Mostra os links mais comuns que são clicados pelas pessoas e levam a lugares fora de seu site. Normalmente, esses links indicam sites de parceiros ou afiliados. Contudo, podem ser qualquer local em que você tenha implementado um link externo. Você pode usar esse relatório para visualizar os links afiliados mais populares, ou para ajudar a validar o número de referências que seus parceiros afirmam receber de você.

Há vários requisitos que devem ser cumpridos para que a página seja preenchida corretamente:

* Se estiver usando um rastreamento de link personalizado manual, uma solicitação *`s.tl()`* deve ser acionada com o parâmetro intermediário definido como *e*.

* Se usar o rastreamento de link personalizado automático, todos os requisitos devem ser cumpridos:
* 

   * [s.trackExternalLinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_trackexlinks) deve ser definido para *verdadeiro*.

   * O usuário do link clicou em não corresponder a quaisquer valores na variável [s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_linkinfilters).
   * Se [s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_linkinfilters) for implementado, o link externo deve corresponder, no mínimo, a um dos valores definidos nessa variável.

* Se algum dos requisitos acima não for cumprido, a ocorrência não preencherá este relatório.

* 
* Como em todas as ocorrências de rastreamento de link personalizado, a variável [s.pageName](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_pagename) é removida da solicitação de imagem para impedir a inflação da exibição de página.
* É possível visualizar esse relatório nos formatos de tendência e de classificação.
* Este relatório pode usar um filtro de pesquisa para localizar itens de linha específicos.
* É possível criar [detalhamentos](/help/analyze/reports-analytics/reports-customize/breakdowns.md) com qualquer outra variável por meio das Ferramentas administrativas.
* [As Instâncias](../../../components/c-variables/c-metrics/metrics-instance.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF) são as únicas métricas disponíveis por padrão neste relatório, contando o número de vezes em que o link de saída foi acionado.
* Os visitantes diários, semanais, mensais e trimestrais podem ser ativados para esse relatório. Contudo, somente um representante da Adobe pode habilitá-los, mediante um custo adicional. Ativar visitantes exclusivos para quaisquer variáveis de rastreamento de link personalizado aumenta em muito a latência do conjunto de relatórios.

