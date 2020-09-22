---
title: Solução de problemas de picos e quedas nos dados
description: Saiba mais sobre as possíveis razões pelas quais você pode ver aumentos ou reduções drásticas nos relatórios de tendências.
translation-type: ht
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: ht
source-wordcount: '855'
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
* **Disponibilidade do Analytics**: verifique [status.adobe.com](https://status.adobe.com/products/1173/pt) se há problemas com a coleta ou o processamento de dados.

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
* **Arquivos de fonte de dados duplicados enviados**: se a sua organização usar [Fontes de dados](/help/import/c-data-sources/datasrc-home.md), um usuário em sua organização poderá fazer upload do mesmo arquivo duas vezes para o Adobe Analytics. Faze o upload desse duplicado efetivamente dobra esses dados nos relatórios, causando o pico de tráfego.

### Outras possíveis causas do aumento do tráfego

* **Aranhas ou bots**: se você observar um aumento súbito no tráfego, a primeira coisa a procurar é a possibilidade de uma aranha ou bot. A identificação de bots pode, às vezes, ser complicada, já que cada um tem sua própria maneira de executar o código em seu site. Crie um relatório do Data Warehouse usando IP como uma dimensão para ver quais endereços causam mais tráfego. Em seguida, você pode usar as [Regras de bot](/help/admin/admin/bot-removal/bot-rules.md) ou uma regra VISTA para eliminar o tráfego de bot nos próximos relatórios.
* **Campanhas lançadas**: as iniciativas de marketing, como campanhas por email ou otimização de mecanismo de pesquisa, podem causar um pico de tráfego no site. Analise a dimensão [Código de rastreamento](/help/components/dimensions/tracking-code.md) para pesquisar mais detalhadamente. Ela também pode ajudar a entrar em contato com sua equipe de marketing para garantir que o pico seja intencional.
* **Causas ambientais ou circunstanciais**: se um feriado ou evento circunstancial ocorrer (um evento importante em que seu site é um recurso conhecido ou iniciativas residuais de marketing de outras organizações), o tráfego poderá aumentar no site. A solução de problemas da causa exata é difícil, pois há um número quase ilimitado de razões circunstanciais para o aumento do tráfego. Essas causas, no entanto, são algumas das mais importantes para determinar, de modo que sua organização possa se beneficiar delas e tomar decisões de negócios de acordo. Analisar a tendência da dimensão [Página](/help/components/dimensions/page.md) ou [Referenciador](/help/components/dimensions/referrer.md) é provavelmente a melhor maneira de começar a determinar a fonte do tráfego.

Se nenhum dos motivos acima for uma possível causa de aumento ou diminuição do tráfego em seu site, entre em contato com o Atendimento ao cliente da Adobe. Eles podem fornecer assistência para localizar a fonte do pico ou da queda do tráfego. Ao criar o incidente, instrua o agente sobre como recriar um relatório específico que ilustre claramente o pico ou a queda.
