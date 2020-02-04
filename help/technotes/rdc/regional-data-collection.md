---
title: Coleta de dados regionais
description: Informação sobre a recolha de dados regionais
translation-type: tm+mt
source-git-commit: 449a64e361523d7a68514d60541c443a4f696c9d

---


# Coleta de dados regionais

A Adobe Experience Cloud usa a RDC (Coleta de dados regionais) para que as interações entre os usuários finais e a Adobe Experience Cloud ocorram o mais próximo possível dos usuários finais. Isso melhora o desempenho do site/aplicativo e garante que os dados sejam coletados o mais rápido possível para otimizar a experiência do usuário final. Depois que os dados de suas propriedades digitais forem coletados regionalmente em um Centro de coleta de dados (DCC), eles serão encaminhados por uma conexão segura para um Centro de processamento de dados (DPC), onde serão processados e disponibilizados para produtos na Adobe Experience Cloud.

Atualmente, a RDC inclui as seguintes localidades (sujeitas a mudança)

## Coleta de dados HTTP e de terceiros

| Tipo da RDC | Centros de coleta de dados |
|---------------------|-------------------|
| Padrão | Oregon, Virgínia, Irlanda, Paris, Mumbai, Cingapura, Tóquio, Sydney |

Note: If your Analytics image request is sent to the `2o7.net` or `omtdrc.net` endpoints, then you have third-party data collection. É possível determinar se um desses endpoints aparecem na URL de suas solicitações.

## Coleta de dados HTTPS primários

| Tipo da RDC | Centros de coleta de dados |
|---------------------|-------------------|
| Global (Padrão) | Oregon, Virgínia, Irlanda, Paris, Mumbai, Cingapura, Tóquio, Sydney |
| Somente Américas | Oregon, Virgínia |
| Somente Europa | Irlanda, Paris |
| Somente Pacífico Asiático | Mumbai, Cingapura, Tóquio, Sidney |

Observação: A Experience Edge Global oferece o melhor desempenho para seus usuários finais.  Se quiser usar um tipo RDC alternativo, entre em contato com o Atendimento ao cliente da Adobe para obter assistência.

## Como a RDC funciona

A lista a seguir descreve o processo de coleta de dados usado pela Adobe:

1. A DNS corrige automaticamente o nome de host da coleta para o endereço IP do Centro de coleta de dados mais próximo do visitante.
1. O visitante envia os dados para o local.
1. Os dados são encaminhados imediatamente por meio de uma conexão segura para o Centro de processamento de dados, onde é processado e disponibilizado para os produtos na Adobe Experience Cloud.

## Benefícios da RDC

| Benefícios | Descrição |
|---------|-----------|
| Desempenho | Com a RDC, seus visitantes se conectarão ao DCC mais próximo. Isso significa que os tempos de resposta da sua página diminuirão (quanto menor, melhor), resultando em um rastreamento mais preciso e em tempos de carregamento mais rápidos. |
| Redundância | Em caso de interrupção na comunicação com um DCC, a coleta de dados é roteada automaticamente para o próximo DCC mais próximo, garantindo a continuidade do serviço. |
| Redundância | No caso de uma interrupção na comunicação entre o DCC e sua DPC, a infraestrutura da RDC da Adobe salva os dados localmente e, em seguida, os encaminha para a DPC quando as comunicações são restauradas. |

## Histórico de revisão da documentação

| atualização | Descrição |
|--------|---------|
| 4 de fevereiro de 2020 | Atualizar locais RDC |
| 20 de fevereiro de 2019 | Regravação completa. Informações de rede RDC adicionadas. |
