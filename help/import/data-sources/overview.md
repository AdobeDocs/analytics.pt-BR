---
title: Visão geral das fontes de dados
description: Importar dados para o Adobe Analytics usando arquivos externos.
exl-id: 5ec8bc51-dfd2-497c-aebc-a32d87efc97e
feature: Data Sources
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# Visão geral das fontes de dados

As fontes de dados do Adobe Analytics permitem importar dados online e offline adicionais para os relatórios. Eles são valiosos para ajudar a entender facetas da sua empresa fora do site e como eles interagem com o site. O fluxo de trabalho geral para usar fontes de dados consiste nas seguintes etapas:

1. Sua organização coleta dados de outras fontes. Os exemplos incluem dados de pré-clique, dados da central de atendimento ou informações sobre transações que ocorreram fora do site.
1. Os dados são formatados de uma forma que o Adobe Analytics entende usando um arquivo de texto delimitado por tabulação.
1. Você faz upload do arquivo de texto para um site FTP fornecido pelo Adobe, juntamente com uma `.fin` arquivo.
1. O Adobe assimila o arquivo de texto e exibe esses dados junto com dimensões e métricas coletadas no site.

Há dois tipos gerais de fontes de dados que o Adobe oferece. Todos os modelos de fontes de dados são baseados em um destes dois tipos:

* **Fonte de dados de resumo**: fornece uma maneira fácil de importar dados de alto nível no Adobe Analytics. Especifique o carimbo de data e hora, o valor da variável e as métricas associadas. Essas métricas para cada item de dimensão são aumentadas de maneira apropriada. Isso é importante se você quiser ver os dados offline e online lado a lado. No entanto, não vincula dados online e offline.
* **Fonte de dados da ID da transação**: se uma ocorrência enviada pelo AppMeasurement e uma linha de fontes de dados contiver IDs de transação correspondentes, a dimensão e os valores de métrica na fonte de dados serão anexados a essa ocorrência.

**Fontes de dados de processamento completo** não são mais oferecidos como tipo de fonte de dados a partir de 25 de março de 2021. Consulte a [Anúncio de fim da vida útil](full-processing-eol.md) para obter mais informações.

O Adobe também oferece o [API de fontes de dados](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), que permite criar fontes de dados e carregar dados sem usar a interface do usuário do produto ou um local FTP.

## Próximas etapas

[Introdução às fontes de dados](getting-started.md): carregue uma fonte de dados simples em um conjunto de relatórios de desenvolvimento.
