---
description: Os Filtros internos do URL identificam referenciadores que você considera internos ao site. Eles ajudam os relatórios de fontes de tráfego a popular os dados, além de ajudarem a filtrar o tráfego interno.
title: Filtros internos do URL
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: ht
source-wordcount: '212'
ht-degree: 100%

---


# Filtros internos do URL

Os Filtros internos do URL identificam referenciadores que você considera internos ao site. Eles ajudam os relatórios de fontes de tráfego a popular os dados, além de ajudarem a filtrar o tráfego interno.

**[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]** > **[!UICONTROL Editar configurações]** > **[!UICONTROL Geral]** > **[!UICONTROL Filtros de URL internos]**

Um referenciador ou uma página referenciadora é, normalmente, a página a partir da qual o visitante veio ao entrar do site. Para evitar o viés dos dados, você pode filtrar e eliminar os referenciadores internos. Os relatórios excluem os referenciadores filtrados do  Dimensão [Referenciadores](/help/components/dimensions/referrer.md), a dimensão [Domínios do referenciador](/help/components/dimensions/referring-domain.md) e outras dimensões de fonte de tráfego.

O motivo mais comum para a falha de cálculo dos relatórios de fontes de tráfego é o Filtro de URL interno não definido. Para verificar quais Filtros de URL interno foram configurados em um conjunto de relatórios, siga essas etapas. Para evitar que isso aconteça, remova a regra que lista um ponto (.) como filtro e adicione seu próprio site.

Um ponto é o filtro padrão de URL interno porque permite que os dados sejam coletados para o relatório Páginas. Se as ocorrências não corresponderem aos filtros de URL interno, todas as páginas aparecerão como Outro. Sempre há um ponto (.) no URL, o que garante que o relatório Páginas seja calculado.
