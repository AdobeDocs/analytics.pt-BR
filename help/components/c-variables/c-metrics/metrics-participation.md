---
description: As métricas de participação atribuem crédito total de eventos bem-sucedidos a todos os valores de uma eVar que foram passados durante uma visita. As métricas de participação são úteis para determinar quais páginas, campanhas ou outros valores de variável personalizados estão contribuindo mais para o sucesso do site. A participação é baseada em visitas. Todos os valores de eVar em uma visita antes e incluindo a ocorrência quando um evento ocorre recebem crédito de participação independentemente da configuração de expiração.
title: Participação
topic: Metrics
uuid: a7fa791d-0a77-429e-808e-4f97bb9ae5fc
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Participação

As métricas de participação atribuem crédito total de eventos bem-sucedidos a todos os valores de uma eVar que foram passados durante uma visita. As métricas de participação são úteis para determinar quais páginas, campanhas ou outros valores de variável personalizados estão contribuindo mais para o sucesso do site. A participação é baseada em visitas. Todos os valores de eVar em uma visita antes e incluindo a ocorrência quando um evento ocorre recebem crédito de participação independentemente da configuração de expiração.

Consulte [Participação do visitante - Ad Hoc Analysis](/help/components/c-variables/c-metrics/metrics-visitor-participation.md) para obter mais informações sobre como a Ad Hoc Analysis utiliza a participação.

As métricas de participação têm duas configurações por evento de conversão:

* **Desativado**: O estado padrão de cada evento de conversão. Os dados de participação não serão coletados para este evento.
* **Ativado**: Os dados de participação são coletados para este evento.

>[!NOTE] Você pode ativar a participação de até 100 eventos personalizados. Além disso, você pode criar métricas de participação no construtor de [Métricas calculadas](https://marketing.adobe.com/resources/help/pt_BR/analytics/calcmetrics/participation_metric.html).

Depois de ativadas, as métricas de participação ficam automaticamente disponíveis em todos os relatórios de conversão. No entanto, as métricas de participação também podem ser visualizadas em relatórios de tráfego específicos, a seu pedido. Como opção, é possível solicitar que as métricas de participação estejam disponíveis em determinados relatórios de tráfego personalizados.

## Exemplo de participação de receita  {#section_DAB6C348201B454BB4ED01313AA777AF}

Considere a seguinte sequência:

1. Um usuário navega até seu site e procura por &quot;sapatos&quot;.
1. O usuário então procura &quot;tênis&quot;.
1. O usuário clica em um link para a página do produto, adiciona o item ao carrinho e efetua uma compra de US$ 120.

Ao exibir a Receita no Relatório de termos de pesquisa interna, você verá o seguinte com base na alocação selecionada:

* **Primeiro**: &quot;sapatos&quot; receberia crédito pelos 120 dólares. &quot;tênis&quot; receberia $0.
* **Último**: &quot;tênis&quot; receberia crédito pelos 120 dólares. &quot;sapatos&quot; receberia $0.
* **Linear**: Cada campanha receberia um crédito de 60 dólares.

   A participação é semelhante à atribuição linear, exceto que todos os valores são creditados na totalidade. Se você usar a Receita (Participação) como métrica, a alocação será desconsiderada. Receita (Participação) neste exemplo relataria R$ 120 para ambos os termos de pesquisa.

>[!MORELIKETHIS]
>
>* [Cálculos de Métricas](/help/components/c-variables/c-metrics/metrics-calculations.md)

