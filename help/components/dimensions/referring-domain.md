---
title: Domínio de referência
description: O domínio abrangente no qual um visitante estava ativado antes de clicar até o site.
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 1%

---


# Domínio de referência

A dimensão &#39;Domínio de referência&#39; relata quais domínios os visitantes clicam para chegar ao site. Essa dimensão é útil para entender quais sites de terceiros direcionam mais tráfego para o seu. Um link deve existir no site externo e um visitante deve clicar nele para que o valor da dimensão seja exibido.

>[!IMPORTANT] Você deve configurar os filtros [de URL](/help/admin/admin/internal-url-filter-admin.md) internos do conjunto de relatórios para usar essa dimensão. A falha ao configurar filtros internos de URL pode incluir domínios internos ou impedir que domínios externos apareçam.

## Preencher esta dimensão com dados

Essa dimensão requer configuração na interface do Analytics e dados em solicitações de imagem.

* Em sua implementação, essa dimensão recupera dados da sequência de caracteres [`r` do](/help/implement/validate/query-parameters.md) query em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `document.referrer` no navegador. Se você usar uma biblioteca do AppMeasurement (por exemplo, por meio do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente. Se você usar um método de coleta de dados fora do AppMeasurement (por exemplo, por meio da API), certifique-se de incluir o parâmetro da string de `r` query em solicitações de imagem.
* Na interface do Analytics, é necessário configurar os filtros [de URL](/help/admin/admin/internal-url-filter-admin.md)internos do conjunto de relatórios. A falha ao configurar filtros internos de URL pode incluir domínios internos ou impedir que domínios externos apareçam.

A Adobe persiste no domínio de referência para uma visita. Se um visitante sair e clicar em um link em um domínio diferente em uma única visita, o novo valor será atualizado e persistirá pelo restante da visita. Se quiser ver apenas o valor original, consulte Domínio [de referência](original-referring-domain.md)original.

## Valores de dimensão

Os valores de dimensão incluem domínios que os visitantes clicam até o site. Se uma ocorrência não tiver dados quens indicou (definidos ou persistentes), ela será agrupada sob o valor da dimensão `"Typed/Bookmarked"`. Esse valor de dimensão significa que não havia valor de quem indicou, como se o visitante digitasse manualmente o endereço do navegador na barra de endereços, ou clicasse em um marcador.
