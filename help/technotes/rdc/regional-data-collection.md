---
title: Coleta de dados regionais
description: Informação sobre a recolha de dados regionais
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Coleta de dados regionais

Saiba mais sobre a Coleta de dados (RDC) da regional e sobre como alterar a rede de coleta, se necessário.

Para melhorar o desempenho da coleta de dados, todos os clientes da Adobe Experience Cloud foram convertidos para a Coleta de dados regional (RDC) para que a coleta ocorra o mais próximo possível dos usuários finais. Isso melhora o desempenho do site/aplicativo e garante que os dados sejam coletados o mais rápido possível para otimizar a experiência do usuário final. Uma vez que os dados das propriedades digitais forem coletados regionalmente em um Centro de coleta de dados (DCC), eles serão transferidos por uma conexão segura para um Centro de processamento de dados (DPC), onde serão processados e disponibilizados para os produtos na Adobe Experience Cloud. A RDC tem sido o padrão para novas implementações por desde 2009.

Atualmente, a RDC inclui as seguintes localidades (sujeitas a mudança)

## Coleta de dados de terceiros

| Tipo da RDC | Centros de coleta de dados |
|---------------------|-------------------|
| Padrão | San Jose, Virginia, Londres, Singapura, Hong Kong, Sydney, Amsterdam |
| Somente China | Pequim |

Note: If your Analytics image request is sent to the `2o7.net` or `omtdrc.net` endpoints, then you have third-party data collection. É possível determinar se um desses endpoints aparecem na URL de suas solicitações.

## Coleta de dados primária

| Tipo da RDC | Centros de coleta de dados |
|---------------------|-------------------|
| Padrão | San Jose, Virginia, Londres, Singapura |
| Todos | Standard plus Hong Kong, Sydney, Amsterdam |
| Somente EUA | San Jose, Virginia |
| Somente UE | Londres, Amsterdam |
| Somente Índia | Mumbai |

## Como a RDC funciona

A lista a seguir descreve o processo de coleta de dados usado pela Adobe:

1. A DNS corrige automaticamente o nome de host da coleta para o endereço IP do Centro de coleta de dados mais próximo do visitante.
1. O visitante envia os dados para o local.
1. Os dados são encaminhados imediatamente por meio de uma conexão segura para o Centro de processamento de dados, onde é processado e disponibilizado para os produtos na Adobe Experience Cloud.

## Benefícios da RDC

| Benefícios | Descrição |
|---------|-----------|
| Desempenho | Com a RDC, seus visitantes se conectarão ao DCC mais próximo. Isso significa que os tempos de resposta da sua página diminuirão (quanto menor, melhor), resultando em um rastreamento mais preciso e em tempos de carregamento mais rápidos. Você pode encontrar mais informações detalhadas sobre o tempo de resposta na seção Melhorias no desempenho com a RDC. |
| Redundância | Em caso de interrupção na comunicação com um DCC, a coleta de dados é roteada automaticamente para o próximo DCC mais próximo, garantindo a continuidade do serviço. |
| Redundância | No caso de uma interrupção na comunicação entre o DCC e sua DPC, a infraestrutura da RDC da Adobe salva os dados localmente e, em seguida, os encaminha para a DPC quando as comunicações são restauradas. |

## Histórico de revisão da documentação

| atualização | Descrição |
|--------|---------|
| 20 de fevereiro de 2019 | Regravação completa. Informações de rede RDC adicionadas. |
