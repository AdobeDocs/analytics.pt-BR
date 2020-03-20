---
title: Links de saída
description: Relatar os links mais comuns que as pessoas clicam para sair do site.
translation-type: tm+mt
source-git-commit: be4c3ec95b9e93dda7603c0bdb178c0a54d800a0

---


# Links de saída

Mostra os links mais comuns que as pessoas clicam para sair do site. Normalmente, esses links apontam para sites de parceiros ou afiliados; no entanto, eles podem ser qualquer local onde você tenha um link externo. Você pode usar esse relatório para visualizar os links afiliados mais populares, ou para ajudar a validar o número de referências que seus parceiros afirmam receber de você.

Há vários requisitos que devem ser cumpridos para que a página seja preenchida corretamente:
* Se estiver usando o rastreamento de link personalizado manual, uma `tl()` solicitação deve ser acionada com o parâmetro intermediário definido como `e`.
* Se usar o rastreamento de link personalizado automático, todos os requisitos devem ser cumpridos:
   * A variável [trackExternalLinks](/help/implement/vars/config-vars/trackexternallinks.md) deve estar ativada.
   * The link the user clicked on must not match any values within the [linkInternalFilters](/help/implement/vars/config-vars/linkinternalfilters.md) variable.
   * If the [linkExternalFilters](/help/implement/vars/config-vars/linkexternalfilters.md) variable exists, the external link must match at least one of the values set in this variable.
* Se algum dos requisitos acima não for atendido, a ocorrência não preencherá este relatório.
* Como em todas as ocorrências de rastreamento de link personalizado, a variável [pageName](/help/implement/vars/page-vars/pagename.md) é removida da solicitação de imagem para evitar inflação para a métrica de exibições de página.
* É possível visualizar esse relatório nos formatos de tendência e de classificação.
* Este relatório pode usar um filtro de pesquisa para localizar itens de linha específicos.
* É possível criar [detalhamentos](/help/analyze/reports-analytics/reports-customize/breakdowns.md) com qualquer outra variável.
