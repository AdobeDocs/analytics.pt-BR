---
description: Conjuntos de relatórios de rollup agregam dados de vários conjuntos de relatórios secundários e os exibem em um conjunto de dados resumido.
title: Conjuntos de relatórios globais e de acumulado
topic: Admin tools
uuid: c90b8e38-2c95-4318-8165-a362106b6142
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Conjuntos de relatórios globais e de acumulado

Conjuntos de relatórios de rollup agregam dados de vários conjuntos de relatórios secundários e os exibem em um conjunto de dados resumido. Eles fornecem um local conveniente para ver totais somados, como exibições de página, receita ou outras dimensões básicas. Os rollups são frequentemente utilizados, pois eles não requerem implementação adicional.

## Definições dos tipos de conjunto de relatórios

**Conjunto** de relatórios global: A implementação é alterada para enviar solicitações de imagem entre domínios em um único conjunto de relatórios global. Se as ocorrências também forem enviadas para conjuntos de relatórios individuais, essa prática será conhecida como marcação de vários conjuntos.

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
* O relatório Páginas é substituído pelo relatório Sites mais populares, que relata métricas no nível do conjunto filho.

## Conjuntos de relatórios globais versus de rollup

**Chamadas** secundárias do servidor: Os rollups não incorrem em chamadas de servidor adicionais além do que um único conjunto de relatórios coleta. Se sua organização usar marcação de vários conjuntos, serão feitas chamadas de servidor secundárias para cada conjunto de relatórios adicional incluído em uma solicitação de imagem.

> [!TIP] Se você usar apenas um conjunto de relatórios global com conjuntos [de relatórios](../../components/vrs/vrs-considerations.md)virtuais, nenhuma chamada de servidor secundário será necessária.

**Alterações** de implementação: Os rollups não exigem alterações de implementação, enquanto os conjuntos de relatórios globais exigem que você inclua a ID do conjunto de relatórios global na implementação.

**Duplicação**: os conjuntos de relatórios globais removem a duplicação de visitantes únicos; os rollups, não. Por exemplo, se um usuário visita três de seus domínios no mesmo dia, os rollups contariam três visitantes únicos diários. Os conjuntos de relatórios globais registrariam um visitante único.

**Intervalo de tempo**: os rollups são processados somente à meia-noite a cada noite, ao passo que os conjuntos de relatórios globais relatam dados com latência padrão.

**Abrangência**: Os rollups não têm como se comunicar entre conjuntos de relatórios. Os conjuntos de relatórios globais podem atribuir crédito a variáveis de conversão entre conjuntos de relatórios, bem como fornecer a definição de caminho entre conjuntos de relatórios.

**Dados históricos**: os rollups podem agregar dados históricos, ao passo que os conjuntos de relatórios globais relatam somente dados a partir do ponto em que foram implementados.

**Relatórios**: Os conjuntos globais de relatórios fornecem dados sobre todas as dimensões; os rollups fornecem dados agregados somente em relatórios de alto nível.

**Produtos** suportados: Os rollups só podem ser usados em Relatórios e análises. Eles não são suportados na Analysis Workspace, no Data Warehouse ou na Análise ad hoc. Conjuntos de relatórios globais podem ser usados em todos os produtos.

**Número de conjuntos** de relatórios agregados: Os rollups suportam apenas um máximo de 40 conjuntos de relatórios secundários. Conjuntos de relatórios globais podem ser implementados em qualquer número de domínios ou aplicativos de sua propriedade.
