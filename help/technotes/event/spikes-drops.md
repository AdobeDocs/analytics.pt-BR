---
title: Solução de problemas de picos e quedas nos dados
description: Saiba mais sobre as possíveis razões pelas quais você pode ver aumentos ou reduções drásticas nos relatórios de tendências.
translation-type: tm+mt
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 2%

---


# Solução de problemas de picos e quedas nos dados

Conforme seu site coleta os dados, muitos fatores externos podem afetar drasticamente a coleta ou os relatórios. A seguir há uma lista de possíveis explicações sobre por que determinadas variáveis ou o tráfego geral aumenta ou diminui drasticamente.

Conforme você determina a causa e avança em direção a uma resolução, você pode medir o impacto do evento nos seus dados e determinar como deseja continuar. See the [overview page](overview.md) for more information.

## Quedas de tráfego

As quedas de tráfego são categorizadas em duas seções: dados parciais e zero.

### Causas potenciais de dados completamente ausentes (relatórios zeros)

* **Latência** do conjunto de relatórios: Ocasionalmente, um conjunto de relatórios pode experimentar a [latência](../latency.md) devido a vários fatores. Vários problemas de latência são resolvidos em horas. Se você estiver preocupado com um conjunto de relatórios específico, entre em contato com o Atendimento ao cliente da Adobe com a ID do conjunto de relatórios afetado.
* **Remoção** da implementação: Às vezes, quando uma organização faz alterações na implementação ou reestrutura seu site, a reimplementação do Analytics é ignorada. Trabalhe com desenvolvedores em sua organização para reimplementar o código em seu site.
* **Problema** de interface/cache do Analytics: Em raras ocasiões, o cache de um navegador contém dados inválidos que fazem com que todos os relatórios retornem zeros. Limpe os cookies e o cache do navegador para resolver o problema. Se a limpeza dos cookies/cache não funcionar, entre em contato com o Atendimento ao cliente com o relatório e o intervalo de datas ausentes; eles podem duplicado o problema e fornecer informações adicionais.
* **Disponibilidade** Analytics: Verifique [status.adobe.com](https://status.adobe.com/products/1173/) se há problemas com a coleta ou o processamento de dados.

### Causas potenciais de dados parcialmente ausentes ou tráfego diminuído

* **Alterações** de implementação: Use o [depurador](/help/implement/validate/debugger.md) para validar se as dimensões desejadas funcionam.
* **Diminuição do tráfego** de referência: Se um anúncio de banner popular ou hiperlink em outro site for removido, isso pode causar uma diminuição drástica no tráfego. Analise a tendência da dimensão de domínios [](/help/components/dimensions/referring-domain.md) de referência de antes e depois da queda para pesquisar mais a fundo.
* **Problemas** de desempenho do site: A distribuição incorreta do tráfego por meio de balanceadores de carga ou problemas de servidor que hospedam seu site pode contribuir para uma redução no relatórios Analytics. Trabalhe com a equipe em sua organização que gerencia a integridade e a integridade do site para investigar possíveis problemas de desempenho.
* **Alterações na classificação** de pesquisa natural: O tráfego pode diminuir se outro site sair da classificação de pesquisa natural para algumas de suas palavras-chave. Essa diminuição pode ser especialmente evidente se o site não estiver mais na primeira página dos resultados da pesquisa. Analise a tendência da dimensão de mecanismos [de](/help/components/dimensions/search-engine.md) pesquisa para pesquisar mais a fundo.
* **Alterações na publicidade** PPC: Alterar os títulos e as descrições dos anúncios para campanhas existentes pode afetar sua Pontuação de qualidade. Em geral, uma Pontuação de alta qualidade significa que sua palavra-chave aciona publicidades em uma posição mais alta e a um custo por clique mais baixo. Analise a tendência das palavras-chave [de pesquisa - dimensão paga](/help/components/dimensions/search-keyword.md) para pesquisar mais a fundo.

## Picos de tráfego

Os picos de tráfego são classificados em duas seções: perto dos dados do duplo e outras causas.

### Causas potenciais de ter perto ou exatamente o duplo dos dados esperados

* **Várias solicitações de imagem em uma implementação**: Se sua implementação contiver mais de uma chamada de [`t()`](/help/implement/vars/functions/t-method.md) método por página, ela efetivamente duplo todos os dados coletados. Use o depurador do site e observe várias solicitações de imagem para capturar duplicados.
* **Arquivos de fonte de dados do Duplicado carregados**: Se sua organização usar fontes [de](/help/import/c-data-sources/datasrc-home.md)dados, um usuário em sua organização poderá fazer upload do mesmo arquivo duas vezes para a Adobe Analytics. A execução deste duplicado faz o upload dos duplos com eficácia dos dados no relatórios, causando o pico de tráfego.

### Outras causas potenciais do aumento do tráfego

* **Spiders ou bots**: Se você vê um aumento súbito no tráfego, a primeira coisa a procurar é a possibilidade de uma aranha ou bot. A identificação de bots pode, às vezes, ser complicada, já que cada um tem sua própria maneira de executar o código em seu site. Crie um relatório de Data warehouse usando IP como uma dimensão para ver quais endereços causam mais tráfego. Em seguida, você pode usar as Regras [do](/help/admin/admin/bot-removal/bot-rules.md) robô ou uma regra VISTA para eliminar o tráfego do robô do relatórios futuro.
* **campanhas** lançadas: Os esforços de marketing, como campanhas por email ou otimização de mecanismo de pesquisa, podem causar um pico de tráfego no site. Analise a dimensão do código [de](/help/components/dimensions/tracking-code.md) rastreamento para pesquisar mais a fundo. Ele também pode ajudar a entrar em contato com sua equipe de marketing para garantir que o pico seja intencional.
* **Causas** ambientais ou circunstanciais: Se um feriado ou evento circunstancial ocorrer (um evento significativo em que o site é um recurso conhecido ou esforços de marketing residuais de outras organizações), o tráfego poderá aumentar no site. A solução de problemas da causa exata é difícil, pois há um número quase ilimitado de razões circunstanciais para o aumento do tráfego. Essas causas, no entanto, são algumas das mais importantes para determinar, de modo que sua organização possa se beneficiar delas e tomar decisões de negócios de acordo. Tendência da dimensão [Página](/help/components/dimensions/page.md) ou [Quem indicou](/help/components/dimensions/referrer.md) é provavelmente o melhor lugar para start na determinação da fonte do tráfego.

Se nenhum dos motivos acima for uma causa potencial de aumento ou diminuição do tráfego em seu site, entre em contato com o Atendimento ao cliente da Adobe. Eles podem fornecer assistência para localizar a fonte do pico ou da queda do tráfego. Ao criar o incidente, instrua o agente sobre como recriar um relatório específico que ilustre claramente o pico ou a queda.
