---
description: As métricas de participação atribuem crédito total de eventos bem-sucedidos a todos os valores de uma eVar que foram passados durante uma visita. As métricas de participação são úteis para determinar que páginas, campanhas ou outros valores variáveis personalizados estão contribuindo mais para o sucesso do site. A participação é baseada na visita. Todos os valores de eVar em uma visita que sejam anteriores ao e incluam a ocorrência de um evento recebem crédito de participação, independentemente da configuração de expiração.
solution: Analytics
title: Participação
topic: Metrics
uuid: a7fa791d-0a77-429e-808e-4f97bb9ae5fc
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Participação

As métricas de participação atribuem crédito total de eventos bem-sucedidos a todos os valores de uma eVar que foram passados durante uma visita. As métricas de participação são úteis para determinar que páginas, campanhas ou outros valores variáveis personalizados estão contribuindo mais para o sucesso do site. A participação é baseada na visita. Todos os valores de eVar em uma visita que sejam anteriores ao e incluam a ocorrência de um evento recebem crédito de participação, independentemente da configuração de expiração.

See [Visitor Participation - Ad Hoc Analysis](/help/components/c-variables/c-metrics/metrics-visitor-participation.md) for more information about how Ad Hoc Analysis uses participation.

As métricas de participação têm duas configurações por evento de conversão:

* **Desativado**: O estado padrão de cada evento de conversão. Os dados de participação não serão coletado para este evento.
* **Ativado**: os dados participação são coletados para este evento.

> [!NOTE] Você pode ativar a participação para até 100 eventos personalizados. Além disso, você pode criar métricas de participação no construtor de [Métricas calculadas](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/participation_metric.html).

Quando estiver ativado, as métricas de participação ficam automaticamente disponíveis em todos os relatórios de conversão. Contudo, métricas de participação também podem ser exibidas em relatórios de tráfego específicos se você solicitar. Outra opção é solicitar que as métricas de participação sejam disponíveis em alguns relatórios de tráfego personalizados.

## Exemplo de participação de receita {#section_DAB6C348201B454BB4ED01313AA777AF}

Suponha a seguinte sequência:

1. Um usuário navega até o seu site e pesquisa por "sapatos".
1. Em seguida, ele pesquisa "tênis".
1. O usuário então clica no link para a página do produto, adiciona o item ao carrinho e efetua uma compra de R$ 120.

Baseados na distribuição selecionada, você deverá ver o que está listado abaixo quando exibir a Receita no Relatório de termos de pesquisa internos:

* **Primeiro**: "sapatos" receberia o crédito pelos R$ 120. "tênis" receberia R$ 0.
* **Último**: "tênis" receberia o crédito pelos R$ 120. "sapatos" receberia R$ 0.
* **Linear**: Cada campanha receberia o crédito de R$ 60.

   A participação é similar à distribuição linear, com a exceção de que a primeira dá crédito total a todos os valores. Se você usar a Receita (participação) como métrica, a alocação é desconsiderada. Neste exemplo, Receita (participação) receberia R$120 pelos dois termos de pesquisa.

>[!MORELIKETHIS]
>
>* [Cálculos de Métricas](/help/components/c-variables/c-metrics/metrics-calculations.md)

