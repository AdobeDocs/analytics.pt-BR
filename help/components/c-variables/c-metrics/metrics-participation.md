---
description: As métricas de participação atribuem crédito total de eventos bem-sucedidos a todos os valores de uma eVar que foram passados durante uma visita. As métricas de participação são úteis para determinar que páginas, campanhas ou outros valores variáveis personalizados estão contribuindo mais para o sucesso do site. A participação é baseada na visita. Todos os valores de eVar em uma visita que sejam anteriores ao e incluam a ocorrência de um evento recebem crédito de participação, independentemente da configuração de expiração.
title: Participação
topic: Metrics
uuid: a7fa791d-0a77-429e-808e-4f97bb9ae5fc
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Participação

As métricas de participação atribuem crédito total de eventos bem-sucedidos a todos os valores de uma eVar que foram passados durante uma visita. As métricas de participação são úteis para determinar que páginas, campanhas ou outros valores variáveis personalizados estão contribuindo mais para o sucesso do site. A participação é baseada na visita. Todos os valores de eVar em uma visita que sejam anteriores ao e incluam a ocorrência de um evento recebem crédito de participação, independentemente da configuração de expiração.

Consulte [Participação do visitante - Ad Hoc Analysis](/help/components/c-variables/c-metrics/metrics-visitor-participation.md) para obter mais informações sobre como a Ad Hoc Analysis utiliza a participação.

As métricas de participação têm duas configurações por evento de conversão:

* **Desativado**: O estado padrão de cada evento de conversão. Os dados de participação não serão coletado para este evento.
* **Ativado**: os dados participação são coletados para este evento.

> [!NOTE] Você pode ativar a participação de até 100 eventos personalizados. Além disso, você pode criar métricas de participação no construtor de [Métricas calculadas](https://marketing.adobe.com/resources/help/pt_BR/analytics/calcmetrics/participation_metric.html).

Quando estiver ativado, as métricas de participação ficam automaticamente disponíveis em todos os relatórios de conversão. Contudo, métricas de participação também podem ser exibidas em relatórios de tráfego específicos se você solicitar. Outra opção é solicitar que as métricas de participação sejam disponíveis em alguns relatórios de tráfego personalizados.

## Exemplo de participação de receita  {#section_DAB6C348201B454BB4ED01313AA777AF}

Suponha a seguinte sequência:

1. Um usuário navega até o seu site e pesquisa por &quot;sapatos&quot;.
1. Em seguida, ele pesquisa &quot;tênis&quot;.
1. O usuário então clica no link para a página do produto, adiciona o item ao carrinho e efetua uma compra de R$ 120.

Baseados na distribuição selecionada, você deverá ver o que está listado abaixo quando exibir a Receita no Relatório de termos de pesquisa internos:

* **Primeiro**: &quot;sapatos&quot; receberia o crédito pelos R$ 120. &quot;tênis&quot; receberia R$ 0.
* **Último**: &quot;tênis&quot; receberia o crédito pelos R$ 120. &quot;sapatos&quot; receberia R$ 0.
* **Linear**: Cada campanha receberia o crédito de R$ 60.

   A participação é similar à distribuição linear, com a exceção de que a primeira dá crédito total a todos os valores. Se você usar a Receita (participação) como métrica, a alocação é desconsiderada. Neste exemplo, Receita (participação) receberia R$120 pelos dois termos de pesquisa.

>[!MORELIKETHIS]
>
>* [Cálculos de Métricas](/help/components/c-variables/c-metrics/metrics-calculations.md)

