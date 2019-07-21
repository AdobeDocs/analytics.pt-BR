---
description: As informações a seguir podem ajudar a solucionar problemas de latência do conjunto de relatórios nos dados do Analytics.
keywords: dados ausentes; slow
seo-description: As informações a seguir podem ajudar a solucionar problemas de latência do conjunto de relatórios nos dados do Analytics.
seo-title: Disponibilidade e latência dos dados
solution: Analytics
subtopic: Dados atuais
title: Disponibilidade e latência dos dados
topic: 'Relatórios  '
uuid: 1 f 0 e 67 e 3-6 cea -4 af 8-8 b 18-7 ae 9223 df 7 c 8
translation-type: tm+mt
source-git-commit: 1fdd14497171dbf5850ec1b1d873a06931d58435

---


# Disponibilidade e latência de dados no Adobe Analytics

Normalmente, você pode esperar visualizar dados completos nos relatórios 2 horas após a coleta dos dados. As informações a seguir podem ajudar a solucionar problemas de latência do conjunto de relatórios nos dados do Analytics.

## Noções básicas sobre o agrupamento de dados

Cada servidor de coleção de dados captura e processa dados analíticos brutos e, então, carrega os dados em lotes a cada hora para fins de relatório. O processo de transferência normalmente leva 30 minutos, de modo que a latência normal para o tráfego que ocorre logo depois de o processo de upload anterior ser concluído é de cerca de 90 minutos (60 minutos até ocorrer o upload do próximo lote e 30 minutos para a transferência e exibição do arquivo). Para o tráfego que ocorre diretamente antes de um upload, a latência de dados pode ser de 30 minutos (0 minutos até ocorrer o carregamento do próximo lote e 30 minutos para a transferência e exibição do arquivo).

Se necessário, o Atendimento ao cliente da Adobe pode ativar carregamentos de dados em lote de 30 minutos (em vez de por hora) para seus conjuntos de relatórios mais usados.

## Contribuidores para latência

A latência é um atraso que é maior do que as 2 horas típicas necessárias para os servidores de coleta de dados processarem dados totalmente. Ela não afeta a coleta de dados; ainda são coletados para uma implementação de trabalho, independentemente de como um conjunto de relatórios é latente. A gravidade (a atualidade dos dados) e a duração (o tempo que leva para resolver) podem variar. Geralmente está limitada a um único conjunto de relatórios.

A latência é causada por uma das seguintes categorias gerais:

* **Pico de tráfego inesperado:** Esse tipo de latência ocorre quando mais dados são enviados para um conjunto de relatórios do que foi acordado ou esperado por contrato. É a causa mais comum de latência.
* **Problemas normais de hardware:** A Adobe emprega estratégias de melhor nível para o gerenciamento e monitoramento de data center, redundância de dados e confiabilidade do hardware. O Hardware é atualizado regularmente e juntamente com janelas de manutenção publicadas. A manutenção de emergência de hardware com falhas pode exigir uma parada necessária e temporária de processamento de dados (e não na coleção de dados) enquanto o hardware substituto é colocado online. Essa interrupção temporária de processamento pode resultar em latência.
* **Dados anormais:** Os padrões de dados não naturais, como visitas muito longas causadas por um bot ou rastreador, podem aumentar temporariamente determinadas cargas de processamento que resultam em latência.

## Recursos que dependem da latência

Alguns recursos na Adobe Experience Cloud vêm com uma quantidade innata de latência sobre o tempo de processamento padrão.

* O Analytics para Target (A 4 T) requer mais de 5a 10 minutos de latência para permitir que dados coletados de ambas as plataformas sejam armazenados na mesma ocorrência.
* Os dados com carimbo de data e hora exigem mais tempo devido a diferentes servidores que são processados. As ocorrências com carimbo de data e hora recebidas em tempo real podem levar até 15 minutos. As ocorrências recebidas com um carimbo de data e hora de ontem podem levar até 2 horas. As ocorrências mais antigas podem demorar mais, aumentando cada dia até um cap de aproximadamente 24 horas.

## Maneiras de mitigar ou impedir a latência

Há várias estratégias para impedir a latência ou reduzir o tempo de recuperação quando ocorre:

* **Notificar a Adobe sobre picos de tráfego esperados:** Embora seja impossível antecipar cada pico de tráfego ao site, pode haver casos em que você está esperando receber um aumento significativo do tráfego. Os exemplos incluem um período de feriado específico, ou pouco depois de um push de campanha grande. Nesses casos, a Adobe fornece uma maneira de sua organização nos informar sobre os aumentos de tráfego esperados possibilitando a alocação de recursos de processamento adicionais para seu conjunto de relatórios. See [Schedule a traffic spike](../admin/c-traffic-management/t-traffic-schedule-spike.md) in the Admin user guide to learn how to notify Adobe of increased traffic.
* **Considere processar a carga ao ativar novos recursos:** Alguns recursos requerem mais processamento do que outros. Quanto mais recursos são ativados em um conjunto de relatórios, mais difícil será a recuperação da latência. Ao ativar recursos em um conjunto de relatórios, lembre-se de que os seguintes recursos aumentam a quantidade de dados para processamento:

   * Implementar mais de 20 eventos na mesma página
   * Regras VISTA complexas
   * Mais de 20 valores nos produtos disponíveis
   * Serialização de eventos

* Enable IAB Bot filtering: [Bot filtering](https://marketing.adobe.com/resources/help/en_US/admin/index.html?f=c_bot_rules) can greatly reduce latency if your report suite is frequented by bots or crawlers. É recomendado usar a lista de bot IAB, já que é atualizada e mantida pelo [Interactive Advertising Bureau](https://www.iab.net/about_the_iab). Um usuário pode personalizar suas próprias regras de bot para complementar as da IAB.

## Como lidar com a latência

Nos casos em que a latência ocorre, tenha certeza de que a Adobe monitora ativamente o pipeline de processamento e faz tudo o que está sendo possível para retornar o tempo de processamento ao normal o mais rápido possível. Vários problemas de latência são resolvidos em horas. Se estiver preocupado com um conjunto de relatórios específico, um dos usuários suportados de sua organização pode entrar em contato com o atendimento ao cliente com a ID do conjunto de relatórios com latência. O representante da Adobe pode validar a latência e informar você conforme o problema é melhorado e resolvido.
