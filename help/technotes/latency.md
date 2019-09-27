---
description: The following information can help troubleshoot report suite latency issues in Analytics data.
keywords: dados ausentes;lento
seo-description: As seguintes informações podem ajudar a solucionar problemas de latência do conjunto de relatórios nos dados do Analytics.
seo-title: Data availability and latency
solution: Analytics
subtopic: Dados atuais
title: Disponibilidade e latência de dados
topic: Relatórios
uuid: 1f0e67e3-6cea-4af8-8b18-7ae9223df7c8
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Data availability and latency in Adobe Analytics

Geralmente, você pode esperar ver dados completos em relatórios 2 horas após a coleta dos dados. As seguintes informações podem ajudar a solucionar problemas de latência do conjunto de relatórios nos dados do Analytics.

## Como entender o agrupamento de dados

Cada servidor de coleção de dados captura e processa dados analíticos brutos e, então, carrega os dados em lotes a cada hora para fins de relatório. O processo de transferência normalmente leva 30 minutos, de modo que a latência normal para o tráfego que ocorre logo depois de o processo de upload anterior ser concluído é de cerca de 90 minutos (60 minutos até ocorrer o upload do próximo lote e 30 minutos para a transferência e exibição do arquivo). For traffic that occurs directly before an upload, data latency could be as short as 30 minutes (0 minutes until the next batch upload occurs, then 30 minutes for file transfer and display).

Se necessário, o Atendimento ao cliente da Adobe pode ativar carregamentos de dados em lote de 30 minutos (em vez de por hora) para os conjuntos de relatórios mais usados.

## Contribuidores para a latência

A latência é um atraso maior do que as 2 horas normais que os servidores de coleta de dados levam para processar os dados por completo. Não afeta a recolha de dados; os dados ainda são coletados para uma implementação em funcionamento, independentemente da latência de um conjunto de relatórios. Sua gravidade (a atualidade dos dados) e a duração (o tempo necessário para resolver) podem variar bastante. Geralmente, ela é limitada a um único conjunto de relatórios.

A latência é causada por uma das seguintes categorias gerais:

* **** Unexpected traffic spike: This type of latency occurs when more data is sent to a report suite than was contractually committed or expected. É a causa mais comum de latência.
* **** Problemas normais de hardware: A Adobe emprega as melhores estratégias do setor para gerenciamento e monitoramento de data center, redundância de dados e confiabilidade de hardware. O Hardware é atualizado regularmente e juntamente com janelas de manutenção publicadas. A manutenção de emergência de hardware com falha pode exigir uma interrupção necessária e temporária no processamento de dados (e não na coleta de dados) à medida que o hardware de substituição é colocado on-line. Essa interrupção temporária de processamento pode resultar em latência.
* **** Dados anormais: Padrões de dados não naturais, como visitas invulgarmente longas causadas por um bot ou crawler, podem aumentar temporariamente determinadas cargas de processamento que resultam em latência.

## Recursos que dependem da latência

Alguns recursos na Adobe Experience Cloud vêm com uma latência inata além do tempo de processamento padrão.

* O Analytics for Target (A4T) requer de 5 a 10 minutos adicionais de latência para permitir que os dados coletados de ambas as plataformas sejam armazenados na mesma ocorrência.
* Os dados com carimbo de data e hora exigem mais tempo devido a diferentes servidores em que esses dados são processados. As ocorrências com carimbo de data e hora recebidas em tempo real ou quase em tempo real podem levar até 15 minutos. As ocorrências recebidas com um carimbo de data e hora de ontem podem levar até 2 horas. As ocorrências mais antigas podem demorar mais, aumentando a cada dia até atingir um limite de aproximadamente 24 horas.

## Formas de mitigar ou impedir a latência

Há várias estratégias para impedir a latência ou reduzir o tempo de recuperação quando ocorre:

* **** Notificar a Adobe sobre picos de tráfego esperados: Embora seja impossível antecipar cada pico de tráfego no site, pode haver casos em que você espera receber um aumento significativo no tráfego. Os exemplos incluem um período de feriado particularmente bem-sucedido ou pouco depois de um grande push de campanha. Nesses casos, a Adobe fornece uma maneira de sua organização nos informar sobre os aumentos de tráfego esperados possibilitando a alocação de recursos de processamento adicionais para seu conjunto de relatórios. Consulte [Agendar um pico](../admin/c-traffic-management/t-traffic-schedule-spike.md) de tráfego no Guia do usuário de administração para saber como notificar a Adobe sobre aumento de tráfego.
* **** Consider processing load when activating new features: Some features are more processing intensive than others. Quanto mais recursos são ativados em um conjunto de relatórios, mais difícil será a recuperação da latência. Ao ativar recursos em um conjunto de relatórios, lembre-se de que os seguintes recursos aumentam a quantidade de dados para processamento:

   * Implementação de mais de 20 eventos na mesma página
   * Regras VISTA complexas
   * Mais de 20 valores nos produtos disponíveis
   * Serialização de eventos

* Enable IAB Bot filtering: [Bot filtering](https://marketing.adobe.com/resources/help/en_US/admin/c_bot_rules.html) can greatly reduce latency if your report suite is frequented by bots or crawlers. É recomendado usar a lista de bot IAB, já que é atualizada e mantida pelo [Interactive Advertising Bureau](https://www.iab.net/about_the_iab). Um usuário pode personalizar suas próprias regras de bot para complementar as da IAB.

## Como lidar com a latência

Nos casos em que a latência ocorre, tenha certeza de que a Adobe monitora de forma proativa o pipeline de processamento e faz tudo o que for possível para retornar o tempo de processamento ao normal o mais rápido possível. Vários problemas de latência são resolvidos em horas. Se estiver preocupado com um conjunto de relatórios específico, um dos usuários suportados de sua organização pode entrar em contato com o atendimento ao cliente com a ID do conjunto de relatórios com latência. O representante da Adobe pode validar a latência e informar você conforme o problema é melhorado e resolvido.
