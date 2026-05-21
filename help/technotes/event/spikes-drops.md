---
title: Solução de problemas de picos e quedas nos dados
description: Saiba mais sobre as possíveis razões pelas quais você pode ver aumentos ou reduções drásticas nos relatórios de tendências.
exl-id: 1a91f95e-818f-423d-9247-e0bb96bd0018
feature: Curate and Share, Data Configuration and Collection
TQID: https://experienceleague.adobe.com/fm9qbkh5RMaAQpgZa20YtZxbXioIO1Dm5DoZCBhEo9k
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 856
ht-degree: 100%

---

# Solução de problemas de picos e quedas nos dados

Conforme seu site coleta os dados, muitos fatores externos podem afetar drasticamente a coleta ou os relatórios. Veja aqui uma lista de possíveis motivos para os aumentos ou reduções drásticas de determinadas variáveis ou do tráfego geral.

Ao determinar a causa e avançar em direção a uma resolução, você pode medir o impacto do evento nos seus dados e determinar como deseja continuar. Consulte a [página de visão geral](overview.md) para obter mais informações.

## Quedas de tráfego

As quedas de tráfego são categorizadas em duas seções: dados parciais e zero.

### Possíveis causas da ausência total de dados (relatórios zeros)

* **Latência do conjunto de relatórios**: ocasionalmente, um conjunto de relatórios pode apresentar [latência](../latency.md) devido a vários fatores. Vários problemas de latência são resolvidos em horas. Se você estiver preocupado com um conjunto de relatórios específico, entre em contato com o Atendimento ao cliente da Adobe e informe a ID do conjunto de relatórios afetado.
* **Remoção da implementação**: às vezes, quando uma organização altera ou reestrutura a implementação de seu site, a reimplementação do Analytics é ignorada. Trabalhe com desenvolvedores em sua organização para reimplementar o código em seu site.
* **Problema de interface/cache do Analytics**: em raras ocasiões, o cache de um navegador contém dados inválidos que fazem com que todos os relatórios retornem zeros. Limpe os cookies e o cache do navegador para resolver o problema. Se a limpeza dos cookies/cache não funcionar, entre em contato com o Atendimento ao cliente com o relatório e o intervalo de datas ausentes; eles podem duplicar o problema e fornecer informações adicionais.
* **Disponibilidade do Analytics**: verifique [status.adobe.com](https://status.adobe.com/br/products/1173/pt) se há problemas com a coleta ou o processamento de dados.

### Possíveis causas da ausência parcial ou tráfego diminuído

* **Alterações de implementação**: use o [depurador](/help/implement/validate/debugger.md) para validar se as dimensões desejadas funcionam.
* **Diminuição do tráfego de referência**: se um anúncio de banner popular ou hiperlink em outro site for removido, o tráfego pode diminuir bastante. Analise a tendência da dimensão [Domínios referenciadores](/help/components/dimensions/referring-domain.md) antes e depois da queda para fazer pesquisas mais detalhadas.
* **Problemas de desempenho do site**: a distribuição incorreta do tráfego por meio de balanceadores de carga ou problemas de servidor que hospedam seu site pode contribuir para uma redução no relatório do Analytics. Trabalhe com a equipe em sua organização que gerencia a integridade do site para investigar possíveis problemas de desempenho.
* **Alterações na classificação de pesquisa natural**: o tráfego pode diminuir se outro site sair da classificação de pesquisa natural para algumas de suas palavras-chave. Essa diminuição pode ser especialmente evidente se o site não estiver mais na primeira página dos resultados da pesquisa. Analise a tendência da dimensão [Mecanismos de pesquisa](/help/components/dimensions/search-engine.md) para fazer pesquisas mais detalhadas.
* **Alterações na publicidade PPC**: alterar os títulos e as descrições dos anúncios para campanhas existentes pode afetar sua Pontuação de qualidade. Em geral, uma Pontuação de alta qualidade significa que sua palavra-chave aciona publicidades em uma posição mais alta e a um custo por clique mais baixo. Analise a tendência da dimensão [Palavras-chave de pesquisa - paga](/help/components/dimensions/search-keyword.md) para fazer pesquisas mais detalhadas.

## Picos de tráfego

Os picos de tráfego são classificados em duas seções: quase o dobro dos dados e outras causas.

### Possíveis causas de ter quase ou exatamente o dobro dos dados esperados

* **Várias solicitações de imagem em uma implementação**: se a sua implementação contiver mais de uma chamada do método [`t()`](/help/implement/vars/functions/t-method.md) por página, ela efetivamente dobra todos os dados coletados. Use o depurador do site e observe várias solicitações de imagem para capturar duplicados.
* **Arquivos de fonte de dados duplicados enviados**: se a sua organização usar [Fontes de dados](/help/import/data-sources/overview.md), um usuário em sua organização poderá fazer upload do mesmo arquivo duas vezes para o Adobe Analytics. Faze o upload desse duplicado efetivamente dobra esses dados nos relatórios, causando o pico de tráfego.

### Outras possíveis causas do aumento do tráfego

* **Aranhas ou bots**: se você observar um aumento súbito no tráfego, a primeira coisa a procurar é a possibilidade de uma aranha ou bot. A identificação de bots pode, às vezes, ser complicada, já que cada um tem sua própria maneira de executar o código em seu site. Crie um relatório do Data Warehouse usando IP como uma dimensão para ver quais endereços causam mais tráfego. Em seguida, você pode usar as [Regras de bot](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md) ou uma regra VISTA para eliminar o tráfego de bot nos próximos relatórios.
* **Campanhas lançadas**: as iniciativas de marketing, como campanhas por email ou otimização de mecanismo de pesquisa, podem causar um pico de tráfego no site. Analise a dimensão [Código de rastreamento](/help/components/dimensions/tracking-code.md) para pesquisar mais detalhadamente. Ela também pode ajudar a entrar em contato com sua equipe de marketing para garantir que o pico seja intencional.
* **Causas ambientais ou circunstanciais**: se um feriado ou evento circunstancial ocorrer (um evento importante em que seu site é um recurso conhecido ou iniciativas residuais de marketing de outras organizações), o tráfego poderá aumentar no site. A solução de problemas da causa exata é difícil, pois há um número quase ilimitado de razões circunstanciais para o aumento do tráfego. Essas causas, no entanto, são algumas das mais importantes para determinar, de modo que sua organização possa se beneficiar delas e tomar decisões de negócios de acordo. Analisar a tendência da dimensão [Página](/help/components/dimensions/page.md) ou [Referenciador](/help/components/dimensions/referrer.md) é provavelmente a melhor maneira de começar a determinar a fonte do tráfego.

Se nenhum dos motivos acima for uma possível causa de aumento ou diminuição do tráfego em seu site, entre em contato com o Atendimento ao cliente da Adobe. Eles podem fornecer assistência para localizar a fonte do pico ou da queda do tráfego. Ao criar o incidente, instrua o agente sobre como recriar um relatório específico que ilustre claramente o pico ou a queda.
