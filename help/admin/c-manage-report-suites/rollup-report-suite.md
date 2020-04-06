---
description: Conjuntos de relatórios de rollup agregam dados de vários conjuntos de relatórios secundários e os exibem em um conjunto de dados resumido.
title: Conjuntos de relatórios globais e de acumulado
topic: Admin tools
uuid: c90b8e38-2c95-4318-8165-a362106b6142
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Conjuntos de relatórios globais e de acumulado

Conjuntos de relatórios de rollup agregam dados de vários conjuntos de relatórios secundários e os exibem em um conjunto de dados resumido. Eles fornecem um local conveniente para ver os totais somados, como exibições de página, receita ou outras dimensões básicas. Os rollups são frequentemente utilizados, pois eles não requerem implementação adicional.

## Definições dos tipos de conjunto de relatórios

**Conjunto de relatórios global**: a implementação é alterada para enviar solicitações de imagem nos domínios em um conjunto de relatórios global único. Se as ocorrências também forem enviadas para conjuntos de relatórios individuais, essa prática será conhecida como marcação de vários conjuntos.

**Conjunto de relatórios de rollup**: criado na Ferramenta administrativa. Pega a soma de cada métrica no fim de cada dia.

* Os rollups são gratuitos e não aumentam o uso de chamadas do servidor.
* Os rollups fornecem dados totais, mas não relatam valores individuais nos relatórios. Por exemplo, os valores de eVar1 não estão incluídos, mas seu total de agregações pode ser incluído.
* Os dados não são desduplicados ao combinar os dados nos conjuntos de relatório.
* Os rollups são executados à noite.
* Quando você adiciona um conjunto de relatórios a um rollup existente, os dados históricos não são incluídos no rollup.
* Todos os conjuntos de relatórios secundários devem ter dados neles para que um rollup funcione. Se novos conjuntos de relatórios forem incluídos em um rollup, certifique-se de enviar pelo menos uma visualização de página para esses conjuntos de relatórios.
* Os conjuntos de relatórios de rollup estão limitados a um máximo de 40 conjuntos de relatórios secundários.
* Os conjuntos de relatórios de rollup estão limitados a um máximo de 100 eventos.
* Os dados contidos nos conjuntos de relatórios de rollup não são compatíveis com detalhamentos ou segmentos.
* O relatório Página é substituído pelo relatório Sites mais populares, que usa métricas no nível filho.

## Conjuntos de relatórios globais versus de rollup

**Chamadas secundárias do servidor**: os rollups não incorrem em chamadas de servidor adicionais além do que um único conjunto de relatórios coleta. Se sua organização usar marcação de vários conjuntos, serão feitas chamadas de servidor secundárias para cada conjunto de relatórios adicional incluído em uma solicitação de imagem.

>[!TIP] Se você usar apenas um conjunto de relatórios global com [conjuntos de relatórios virtuais](../../components/vrs/vrs-considerations.md), nenhuma chamada de servidor secundário será necessária.

**Alterações de implementação**: os rollups não exigem alterações de implementação, enquanto os conjuntos de relatórios globais exigem que você inclua a ID do conjunto de relatórios global na implementação.

**Duplicação**: Os conjuntos de relatórios globais desduplicam visitantes únicos, mas os rollups não. Por exemplo, se um usuário visitar três de seus domínios no mesmo dia, os rollups contariam três visitantes únicos diários. Os conjuntos de relatórios globais registrariam um visitante exclusivo.

**Período**: Os rollups são processados somente à meia-noite a cada noite, enquanto os conjuntos de relatórios globais relatam dados com latência padrão.

**Abrangência**: os rollups não possuem uma forma de comunicação entre os conjuntos de relatórios. Os conjuntos de relatórios globais podem atribuir crédito às variáveis de conversão entre conjuntos de relatórios, bem como fornecer a definição de caminho em conjuntos de relatórios.

**Dados históricos**: os rollups podem agregar dados históricos, ao passo que os conjuntos de relatórios globais relatam somente dados a partir do ponto em que foram implementados.

**Relatórios**: todos os conjuntos de relatórios globais fornecem informações adicionais sobre todas as dimensões; os rollups fornecem dados agregados em relatórios de alto nível.

**Produtos compatíveis**: os rollups só podem ser usados no Reports &amp; Analytics. Eles não são compatíveis com a Analysis Workspace, o Data Warehouse ou a Ad Hoc Analysis. Os conjuntos de relatórios globais podem ser usados em todos os produtos.

**Número de conjuntos de relatórios agregados**: oos rollups suportam apenas um máximo de 40 conjuntos de relatórios secundários. Os conjuntos de relatórios globais podem ser implementados em qualquer número de domínios ou aplicativos de sua propriedade.
