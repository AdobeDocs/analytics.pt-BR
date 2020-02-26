---
description: Conjuntos de relatórios de rollup agregam dados de vários conjuntos de relatórios secundários e os exibem em um conjunto de dados resumido.
title: Conjuntos de relatórios globais e de acumulado
topic: Admin tools
uuid: c90b8e38-2c95-4318-8165-a362106b6142
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Conjuntos de relatórios globais e de acumulado

Conjuntos de relatórios de rollup agregam dados de vários conjuntos de relatórios secundários e os exibem em um conjunto de dados resumido. Eles fornecem um local conveniente para ver os totais somados, como exibições de página, receita ou outras dimensões básicas. Os rollups são frequentemente utilizados, pois eles não requerem implementação adicional.

## Definições dos tipos de conjunto de relatórios

**Conjunto de relatórios global**: a implementação é alterada para enviar solicitações de imagem nos domínios em um conjunto de relatórios global único. Se as ocorrências também forem enviadas para conjuntos de relatórios individuais, essa prática será conhecida como marcação de vários conjuntos.

**Conjunto de relatórios de rollup**: criado na Ferramenta administrativa. Pega a soma de cada métrica no fim de cada dia.

* Os rollups são gratuitos e não aumentam o uso de chamadas do servidor.
* Os Rollups fornecem os dados totais, mas não reportam valores individuais nos relatórios. Por exemplo, os valores de eVar1 não estão incluídos, mas o seu total agregado pode ser incluído.
* Os dados não são desduplicados ao combinar os dados nos conjuntos de relatório.
* Os rollups são executados à noite.
* Quando você adiciona um conjunto de relatórios a um rollup existente, os dados históricos não são incluídos no rollup.
* Todos os conjunto de relatórios secundários precisam conter dados para que um rollup possa funcionar. Se os novos conjunto de relatórios forem incluídos em um rollup, certifique-se de enviar pelo menos uma exibição de página para esses conjunto de relatórios.
* Os conjuntos de relatórios de rollup são limitados a, no máximo, 40 conjuntos de relatórios secundários.
* Os conjuntos de relatórios de rollup estão limitados ao máximo de 100 eventos.
* Os dados contidos nos conjuntos de relatórios de rollup não são compatíveis com detalhamentos ou segmentos.
* O relatório Página é substituído pelo relatório Sites mais populares, que usa métricas no nível filho.

## Conjuntos de relatórios globais versus de rollup

**Chamadas secundárias do servidor**: os rollups não incorrem em chamadas de servidor adicionais além do que um único conjunto de relatórios coleta. Se sua organização usar marcação de vários conjuntos, serão feitas chamadas de servidor secundárias para cada conjunto de relatórios adicional incluído em uma solicitação de imagem.

> [!TIP] Se você usar apenas um conjunto de relatórios global com [conjuntos de relatórios virtuais](../../components/vrs/vrs-considerations.md), nenhuma chamada de servidor secundário será necessária.

**Alterações de implementação**: os rollups não exigem alterações de implementação, enquanto os conjuntos de relatórios globais exigem que você inclua a ID do conjunto de relatórios global na implementação.

**Duplicação**: os conjuntos de relatórios globais removem a duplicação de visitantes únicos; os rollups, não. Por exemplo, se um usuário visita três de seus domínios no mesmo dia, os rollups contariam três visitantes únicos diários. Os conjuntos de relatórios globais registrariam um visitante único.

**Intervalo de tempo**: os rollups são processados somente à meia-noite a cada noite, ao passo que os conjuntos de relatórios globais relatam dados com latência padrão.

**Abrangência**: os rollups não possuem uma forma de comunicação entre os conjuntos de relatórios. Os conjuntos de relatórios globais podem atribuir crédito às variáveis de conversão entre conjuntos de relatórios, bem como fornecer a definição de caminho em conjuntos de relatórios.

**Dados históricos**: os rollups podem agregar dados históricos, ao passo que os conjuntos de relatórios globais relatam somente dados a partir do ponto em que foram implementados.

**Relatórios**: todos os conjuntos de relatórios globais fornecem informações adicionais sobre todas as dimensões; os rollups fornecem dados agregados em relatórios de alto nível.

**Produtos compatíveis**: os rollups só podem ser usados no Reports &amp; Analytics. Eles não são compatíveis com a Analysis Workspace, o Data Warehouse ou a Ad Hoc Analysis. Os conjuntos de relatórios globais podem ser usados em todos os produtos.

**Número de conjuntos de relatórios agregados**: oos rollups suportam apenas um máximo de 40 conjuntos de relatórios secundários. Os conjuntos de relatórios globais podem ser implementados em qualquer número de domínios ou aplicativos de sua propriedade.
