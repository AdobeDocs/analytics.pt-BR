---
title: Visão geral das fontes de dados
description: Importe dados para o Adobe Analytics usando arquivos externos.
source-git-commit: e32a7c85e2f0629c04bcd7ed0fa80ec1593bb6e8
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# Visão geral das fontes de dados

As fontes de dados do Adobe Analytics permitem importar outros dados online ou offline para os relatórios. Elas são valiosas para ajudar a entender facetas de sua empresa fora do site e como elas interagem com seu site. O fluxo de trabalho geral para usar fontes de dados consiste nas seguintes etapas:

1. Sua organização coleta dados de outras fontes. Os exemplos incluem dados pré-clique, dados da central de atendimento ou informações sobre transações que ocorreram fora do seu site.
1. Os dados são formatados de forma que o Adobe Analytics entenda usar um arquivo de texto delimitado por tabulação.
1. Você faz upload do arquivo de texto para um site FTP fornecido pelo Adobe, juntamente com um `.fin` arquivo.
1. O Adobe assimila o arquivo de texto e exibe esses dados ao lado de dimensões e métricas coletadas no site.

Há dois tipos gerais de fontes de dados que o Adobe oferece. Todos os templates de fonte de dados são baseados em um desses dois tipos:

* **Fonte de dados de resumo**: Fornece uma maneira fácil de importar dados de alto nível no Adobe Analytics. Especifique o carimbo de data e hora, o valor da variável e as métricas associadas. Essas métricas para cada item de dimensão são então aumentadas de acordo. Ela é importante se você quiser ver dados offline e online lado a lado. No entanto, ele não vincula dados online e offline.
* **Fonte de dados da ID de transação**: Se uma ocorrência enviada pelo AppMeasurement e uma linha de fontes de dados contiver IDs de transação correspondentes, os valores de dimensão e métrica na fonte de dados anexarão a essa ocorrência.

**Fontes de dados de processamento completo** não são mais oferecidas como fonte de dados a partir de 25 de março de 2021. Consulte a [Anúncio do fim da vida útil](full-processing-eol.md) para obter mais informações.

O Adobe também oferece a variável [API de fontes de dados](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), que permite criar fontes de dados e fazer upload dos dados sem usar a interface do usuário do produto ou um local FTP.

## Próximas etapas

[Introdução às fontes de dados](getting-started.md): Faça upload de uma fonte de dados simples para um conjunto de relatórios de desenvolvimento.
