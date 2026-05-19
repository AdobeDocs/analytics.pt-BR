---
description: As informações a seguir podem ajudar a resolver problemas de latência dos conjuntos de relatórios em dados do Analytics.
keywords: ausência de dados;lento
title: Disponibilidade e latência de dados
feature: Data Configuration and Collection
exl-id: fedef3ea-dde6-460f-90e3-1e661ed29b78
TQID: https://experienceleague.adobe.com/tUoPm4FFCjyp9J4w6fHMMe-guBoVzLwbpU0Tbk-lgCA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 823
ht-degree: 78%

---

# Disponibilidade e latência de dados no Adobe Analytics

Normalmente, você pode esperar ver dados completos em relatórios 2 horas depois de dados serem coletados. As informações a seguir podem ajudar a resolver problemas de latência dos conjuntos de relatórios em dados do Analytics.

## Compressão do processamento de dados em lotes

Cada servidor de coleta de dados captura e processa dados brutos de análise e, em seguida, carrega dados em lote de hora em hora para relatórios. O processo de transferência geralmente leva 30 minutos, portanto, a latência normal do tráfego que ocorre diretamente após a conclusão do processo de upload anterior é de cerca de 90 minutos (60 minutos até que o próximo upload em lote ocorra e, em seguida, 30 minutos para a transferência e exibição de arquivos). No caso do tráfego que ocorrer pouco antes de um upload, a latência de dados chegar a 30 minutos (0 minutos até ocorrer o upload do próximo lote e 30 minutos para a transferência e exibição do arquivo).

Se necessário, o Atendimento ao cliente da Adobe pode habilitar uploads de dados em lote de 30 minutos (e não a cada hora) para seus conjuntos de relatórios mais usados.

## Contribuidores para a latência

A latência é um atraso maior do que as 2 horas normais que os servidores de coleta de dados levam para processar os dados por completo. Não afeta a coleta de dados; os dados ainda são coletados para uma implementação em funcionamento, independentemente da latência de um conjunto de relatórios. Sua gravidade (a atualidade dos dados) e a duração (o tempo necessário para resolver) podem variar bastante. Normalmente está limitada a um único conjunto de relatórios.

A latência é causada por uma das seguintes categorias gerais:

* **Pico de tráfego inesperado:** esse tipo de latência ocorre quando mais dados são enviados para um conjunto de relatórios do que foi concordado ou esperado por contrato. É a causa mais comum de latência.
* **Problemas normais de hardware:** a Adobe adota as melhores estratégias do setor para o gerenciamento e monitoramento de data center, redundância de dados e confiabilidade de hardware. O Hardware é atualizado regularmente e juntamente com janelas de manutenção publicadas. A manutenção de emergência de hardware com falhas pode exigir uma parada necessária e temporária de processamento de dados (e não da coleção de dados) enquanto o hardware substituto é colocado online. Essa interrupção temporária de processamento pode resultar em latência.
* **Dados anormais:** os padrões de dados não naturais, como visitas muito longas causadas por um bot ou crawler, podem aumentar temporariamente determinadas cargas de processamento que resultam em latência.

## Recursos que dependem da latência

Alguns recursos do Adobe CX Enterprise vêm com uma latência inata além do tempo de processamento padrão.

* O Analytics for Target (A4T) requer de 5 a 10 minutos adicionais de latência para permitir que os dados coletados de ambas as plataformas sejam armazenados na mesma ocorrência.
* Os dados com carimbo de data e hora exigem mais tempo devido a diferentes servidores em que esses dados são processados. As ocorrências com carimbo de data e hora recebidas em tempo real ou quase em tempo real podem levar até 15 minutos. As ocorrências recebidas com um carimbo de data e hora de ontem podem levar até 2 horas. As ocorrências mais antigas podem demorar mais, com a latência aumentando a cada dia até atingir um limite de aproximadamente 24 horas.

## Maneira de mitigar ou impedir a latência

Há várias estratégias para impedir a latência ou reduzir o tempo de recuperação quando ocorre:

* **Notifique a Adobe sobre picos de tráfego esperados:** embora seja impossível antecipar cada pico de tráfego no site, pode haver casos em que você espera receber um aumento significativo no tráfego. Os exemplos incluem um período de um feriado particularmente bem-sucedido ou pouco depois de promover uma grande campanha. Nesses casos, a Adobe fornece uma maneira de sua organização nos informar sobre os aumentos de tráfego esperados possibilitando a alocação de recursos de processamento adicionais para seu conjunto de relatórios. Consulte [Agendar um pico de tráfego](/help/admin/tools/manage-rs/edit-settings/c-traffic-management/t-traffic-schedule-spike.md) no guia do usuário de Administração para saber como notificar a Adobe sobre aumento de tráfego.
* **Considere processar a carga ao ativar novos recursos:** alguns recursos requerem mais processamento do que outros. Quanto mais recursos estiverem ativados em um conjunto de relatórios, mais difícil será a recuperação da latência. Ao ativar recursos em um conjunto de relatórios, lembre-se dos seguintes recursos que aumentam a quantidade de dados a serem processados:

   * Implementação de mais de 20 eventos na mesma página
   * Regras VISTA complexas
   * Mais de 20 valores na variável products
   * Serialização de eventos

* Habilitar a Filtragem de bot IAB: a [Filtragem de bot](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md) pode reduzir bastante a latência se o conjunto de relatórios for frequentado por bots ou crawlers. É recomendado usar a lista de bot IAB, já que é atualizada e mantida pelo [Interactive Advertising Bureau](https://www.iab.net/about_the_iab). Um usuário pode personalizar suas próprias regras de bot para complementar as da IAB.

## Como lidar com a latência

Nos casos em que a latência ocorre, tenha certeza de que a Adobe monitora de forma proativa a pipeline de processamento e faz tudo o que for possível para retornar o tempo de processamento ao normal o mais rápido possível. Vários problemas de latência são resolvidos em horas. Se você estiver preocupado com um conjunto de relatórios específico, um dos usuários suportados da organização poderá entrar em contato com o Atendimento ao cliente com a ID do conjunto de relatórios que está apresentando latência. O representante da Adobe pode validar a latência e informá-lo quando o problema melhorar e for resolvido.
