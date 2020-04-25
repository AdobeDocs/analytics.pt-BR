---
description: As informações a seguir podem ajudar a resolver problemas de latência dos conjuntos de relatórios em dados do Analytics.
keywords: missing data;slow
subtopic: Current data
title: Disponibilidade e latência de dados
topic: Reports
uuid: 1f0e67e3-6cea-4af8-8b18-7ae9223df7c8
translation-type: tm+mt
source-git-commit: a4a4d9e6e2d3e3ed88b4ef66e9da3b05865a9b79

---


# Disponibilidade e latência de dados no Adobe Analytics

Normalmente, você pode esperar ver dados completos em relatórios 2 horas depois de dados serem coletados. As informações a seguir podem ajudar a resolver problemas de latência dos conjuntos de relatórios em dados do Analytics.

## Compressão do processamento de dados em lotes

Cada servidor de coleção de dados captura e processa dados analíticos brutos e, então, carrega os dados em lotes a cada hora para fins de relatório. O processo de transferência normalmente leva 30 minutos, de modo que a latência normal para o tráfego que ocorre logo depois de o processo de upload anterior ser concluído é de cerca de 90 minutos (60 minutos até ocorrer o upload do próximo lote e 30 minutos para a transferência e exibição do arquivo). No caso do tráfego que ocorrer pouco antes de um upload, a latência de dados chegar a 30 minutos (0 minutos até ocorrer o upload do próximo lote e 30 minutos para a transferência e exibição do arquivo).

Se necessário, o Atendimento ao cliente da Adobe pode ativar uploads de dados em lote de 30 minutos (e não a cada hora) para seus conjuntos de relatórios mais usados.

## Contribuidores para a latência

A latência é um atraso maior do que as 2 horas normais que os servidores de coleta de dados levam para processar os dados por completo. Não afeta a coleta de dados; os dados ainda são coletados para uma implementação em funcionamento, independentemente da latência de um conjunto de relatórios. Sua gravidade (a atualidade dos dados) e a duração (o tempo necessário para resolver) podem variar bastante. Normalmente está limitada a um único conjunto de relatórios.

A latência é causada por uma das seguintes categorias gerais:

* **Pico de tráfego inesperado:** esse tipo de latência ocorre quando mais dados são enviados para um conjunto de relatórios do que foi concordado ou esperado por contrato. É a causa mais comum de latência.
* **Problemas normais de hardware:** a Adobe adota as melhores estratégias do setor para o gerenciamento e monitoramento de data center, redundância de dados e confiabilidade de hardware. O Hardware é atualizado regularmente e juntamente com janelas de manutenção publicadas. A manutenção de emergência de hardware com falhas pode exigir uma parada necessária e temporária de processamento de dados (e não da coleção de dados) enquanto o hardware substituto é colocado online. Essa interrupção temporária de processamento pode resultar em latência.
* **Dados anormais:** os padrões de dados não naturais, como visitas muito longas causadas por um bot ou crawler, podem aumentar temporariamente determinadas cargas de processamento que resultam em latência.

## Recursos que dependem da latência

Alguns recursos na Adobe Experience Cloud vêm com uma latência inata além do tempo de processamento padrão.

* O Analytics for Target (A4T) requer de 5 a 10 minutos adicionais de latência para permitir que os dados coletados de ambas as plataformas sejam armazenados na mesma ocorrência.
* Os dados com carimbo de data e hora exigem mais tempo devido a diferentes servidores em que esses dados são processados. As ocorrências com carimbo de data e hora recebidas em tempo real ou quase em tempo real podem levar até 15 minutos. As ocorrências recebidas com um carimbo de data e hora de ontem podem levar até 2 horas. As ocorrências mais antigas podem demorar mais, com a latência aumentando a cada dia até atingir um limite de aproximadamente 24 horas.

## Maneira de mitigar ou impedir a latência

Há várias estratégias para impedir a latência ou reduzir o tempo de recuperação quando ocorre:

* **Notifique a Adobe sobre picos de tráfego esperados:** embora seja impossível antecipar cada pico de tráfego no site, pode haver casos em que você espera receber um aumento significativo no tráfego. Os exemplos incluem um período de um feriado particularmente bem-sucedido ou pouco depois de promover uma grande campanha. Nesses casos, a Adobe fornece uma maneira de sua organização nos informar sobre os aumentos de tráfego esperados possibilitando a alocação de recursos de processamento adicionais para seu conjunto de relatórios. Consulte [Agendar um pico de tráfego](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) no guia do usuário de Administração para saber como notificar a Adobe sobre aumento de tráfego.
* **Considere processar a carga ao ativar novos recursos:** alguns recursos requerem mais processamento do que outros. Quanto mais recursos são ativados em um conjunto de relatórios, mais difícil será a recuperação da latência. Ao ativar recursos em um conjunto de relatórios, lembre-se de que os seguintes recursos aumentam a quantidade de dados para processamento:

   * Implementação de mais de 20 eventos na mesma página
   * Regras VISTA complexas
   * Mais de 20 valores nos produtos disponíveis
   * Serialização de eventos

* Ativar a Filtragem de bot IAB: a [Filtragem de bot](/help/admin/admin/bot-removal/bot-removal.md) pode reduzir bastante a latência se o conjunto de relatórios for frequentado por bots ou crawlers. É recomendado usar a lista de bot IAB, já que é atualizada e mantida pelo [Interactive Advertising Bureau](https://www.iab.net/about_the_iab). Um usuário pode personalizar suas próprias regras de bot para complementar as da IAB.

## Como lidar com a latência

Nos casos em que a latência ocorre, tenha certeza de que a Adobe monitora de forma proativa a pipeline de processamento e faz tudo o que for possível para retornar o tempo de processamento ao normal o mais rápido possível. Vários problemas de latência são resolvidos em horas. Se estiver preocupado com um conjunto de relatórios específico, um dos usuários suportados de sua organização pode entrar em contato com o atendimento ao cliente com a ID do conjunto de relatórios com latência. O representante da Adobe pode validar a latência e informar você conforme o problema é melhorado e resolvido.
