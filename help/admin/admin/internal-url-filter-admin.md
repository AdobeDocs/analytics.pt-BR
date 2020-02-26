---
description: Os Filtros internos do URL identificam referenciadores que você considera internos ao site. Eles ajudam os relatórios de fontes de tráfego a popular os dados, além de ajudarem a filtrar o tráfego interno.
title: Filtros internos do URL
topic: Admin tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Filtros internos do URL

Os Filtros internos do URL identificam referenciadores que você considera internos ao site. Eles ajudam os relatórios de fontes de tráfego a popular os dados, além de ajudarem a filtrar o tráfego interno.

Um referenciador ou uma página referenciadora é, normalmente, a página a partir da qual o visitante veio ao entrar do site. Para evitar o viés dos dados, você pode filtrar e eliminar os referenciadores internos. Os relatórios excluem os referenciadores filtrados do [Relatório de referenciadores](/help/components/c-variables/dimensionslist/reports-referrers.md), o [Relatório de domínios referenciadores](/help/components/c-variables/dimensionslist/reports-referring-domains.md) e outros relatórios de Métodos de descoberta.

O motivo mais comum para a falha de cálculo dos relatórios de fontes de tráfego é o Filtro de URL interno não definido. Para verificar quais Filtros de URL interno foram configurados em um conjunto de relatórios, siga essas etapas. Para evitar que isso aconteça, remova a regra que lista um ponto (.) como filtro e adicione seu próprio site.

Um ponto é o filtro padrão de URL interno porque permite que os dados sejam coletados para o relatório Páginas. Se as ocorrências não corresponderem aos filtros de URL interno, todas as páginas aparecerão como Outro. Sempre há um ponto (.) no URL, o que garante que o relatório Páginas seja calculado.
