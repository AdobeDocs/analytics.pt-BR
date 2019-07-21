---
description: Conjuntos de relatórios de rollup agregam dados de vários conjuntos de relatórios secundários e os exibem em um conjunto de dados resumido.
seo-description: Conjuntos de relatórios de rollup agregam dados de vários conjuntos de relatórios secundários e os exibem em um conjunto de dados resumido.
seo-title: Conjuntos de relatórios globais e de rollup
solution: Analytics
title: Conjuntos de relatórios globais e de rollup
topic: Ferramentas administrativas
uuid: c 90 b 8 e 38-2 c 95-4318-8165-a 362106 b 6142
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Conjuntos de relatórios globais e de rollup

Conjuntos de relatórios de rollup agregam dados de vários conjuntos de relatórios secundários e os exibem em um conjunto de dados resumido.

Para não ser confundido com conjuntos de relatório global, os rollups fornecem um lugar conveniente para visualizar os totais resumidos, tais como Visualizações de Página, Receita ou métricas de Tecnologia. Os rollups são frequentemente utilizados, pois eles não requerem implementação adicional.

## Definições dos tipos de conjunto de relatórios {#section_E51E03E3917040278600A7E9638A91C7}

**Conjunto de relatórios global**: a implementação é alterada para enviar solicitações de imagem nos domínios em um suite de relatório global único, além de conjuntos de relatório individual.

**Conjunto de relatórios de rollup**: criado na Ferramenta administrativa. Pega a soma de cada métrica no fim de cada dia.

* Os Rollups são livres para serem usados e não incrementam chamadas do servidor.
* Os Rollups fornecem os dados totais, mas não reportam valores individuais nos relatórios. Por exemplo, os valores de eVar1 não estão incluídos, mas o seu total agregado pode ser incluído.
* Os dados não são desduplicados ao combinar os dados nos conjuntos de relatório. Um único usuário podem atingir três suites diferentes de relatório em um único dia, e apareceria como três visitantes únicos por dia no rollup.
* A agregação de rollup acontece à noite.
* Quando você adiciona um conjunto de relatórios a um rollup existente, os dados históricos não são incluídos no rollup.
* conjunto de relatórios de rollup têm recursos limitados de relatório. Por exemplo, contagens de visitantes únicos são adicionadas a todos os conjunto de relatórios. Se a mesma pessoa visitar dois conjuntos de relatórios separados, o rollup lista essa pessoa como dois visitantes, enquanto um conjunto de relatórios global padrão mostra um visitante.
* Todos os conjunto de relatórios secundários precisam conter dados para que um rollup possa funcionar. Se os novos conjunto de relatórios forem incluídos em um rollup, certifique-se de enviar pelo menos uma exibição de página para esses conjunto de relatórios.
* Os conjuntos de relatórios de rollup são limitados a, no máximo, 40 conjuntos de relatórios secundários.
* Os conjuntos de relatórios de rollup estão limitados ao máximo de 100 eventos.
* Os dados contidos nos conjuntos de relatórios de rollup não são compatíveis com sub-relações, segmentos ou quaisquer métricas que foram introduzidas no relatório de marketing.
* O relatório Páginas não está disponível em conjuntos de relatórios de rollup. Ele é substituído pelo relatório Sites mais populares, que usa métricas no nível filho.

## Conjuntos de relatórios globais versus de rollup {#section_7B3703DC7ABF4B9EA9DF02A54592CAD0}

**Chamadas de servidor**: os conjuntos de relatórios globais incrementam as chamadas de servidor secundário, ao passo que rollups não realizam quaisquer chamadas de servidor.

**Alterações de implementação**: os rollups não requerem quaisquer alterações de implementação, ao passo que os conjuntos de relatórios globais exigem outra ID do conjunto de relatórios no arquivo s_code.js.

**Duplicação**: os conjuntos de relatórios globais removem a duplicação de visitantes únicos; os rollups, não. Por exemplo, se um usuário visita três de seus domínios no mesmo dia, os rollups contariam três visitantes únicos diários. Os conjuntos de relatórios globais registrariam um visitante único.

**Intervalo de tempo**: os rollups são processados somente à meia-noite a cada noite, ao passo que os conjuntos de relatórios globais relatam dados com latência padrão.

**Abrangência**: os conjuntos de relatórios globais podem atribuir crédito às variáveis de conversão entre conjuntos de relatórios, bem como fornecer a definição de caminho em conjuntos de relatórios. Os rollups não possuem uma forma de comunicação entre os conjuntos de relatórios.

**Dados históricos**: os rollups podem agregar dados históricos, ao passo que os conjuntos de relatórios globais relatam somente dados a partir do ponto em que foram implementados.

**Relatórios**: os conjuntos de relatórios globais fornecem informações adicionais sobre TODOS os relatórios implementados; os rollups fornecem dados agregados em relatórios de alto nível.

**Produtos suportados**: os rollups não são suportados no data warehouse ou em Ad Hoc Analysis. Os relatórios de marketing são limitados a 40 conjuntos de relatórios filhos. Os conjuntos de relatórios globais podem ser usados em todos os produtos e ter um número ilimitado de conjuntos de relatórios secundários.

## Que tipo de conjunto de relatórios você deseja implementar? {#section_868066B9604B49BABBF84074BA5E9C71}

Ao optar entre usar rollups ou conjuntos de relatórios globais, considere o seguinte:

* O número de chamadas de servidor é essencial para minha organização? Caso seja importante manter as chamadas de servidor limitadas, considere usar os rollups. Os conjuntos de relatórios globais quase dobram o número de chamadas de servidor realizadas.
* Basta relatar um total de alto nível de tráfego em todos os conjuntos? Se a remoção de duplicação de visitantes for um requisito, considere implementar um conjunto de relatórios global.
* A definição de caminho e os eventos de conversão/bem-sucedidos nos domínios são importantes? Se as campanhas entre sites forem amplamente usadas, considere implementar um conjunto de relatórios global.
* A visualização total dos dados do site apresenta limite de tempo? Os conjuntos de relatórios individuais ainda relatam em tempo quase real. Caso seja adequado ver os totais do conjunto de relatórios no dia seguinte, os rollups são recomendados.
* Há uma grande quantidade de dados históricos acionáveis? Os conjuntos de relatórios globais não podem relatar retroativamente. Os rollups são recomendados se os dados históricos forem importantes.
* O data warehouse e a Ad Hoc Analysis é essencial para suplementar o relatório? Em caso afirmativo, um conjunto de relatórios global é recomendado.

Nenhuma das escolhas afeta os conjuntos de relatórios individuais. Considere cuidadosamente os prós e contras antes de definir a preferência de sua organização.
