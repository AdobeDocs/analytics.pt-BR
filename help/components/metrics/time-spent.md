---
title: Como o Tempo gasto é calculado no Adobe Analytics
description: Uma página agregada de dimensões e métricas de tempo gasto.
feature: Metrics
exl-id: 71e9b856-8a0a-47be-a73f-4dc7d639a5de
source-git-commit: 03502f42473791bec930cc688c0b7905acf12de6
workflow-type: tm+mt
source-wordcount: '1655'
ht-degree: 64%

---

# Visão geral do tempo gasto

Várias [!UICONTROL &#39;tempo gasto&#39;] [métricas](overview.md) e dimensões são oferecidas nos produtos da Adobe Analytics. Esta página pode ajudar a desfazer a ambiguidade da dimensão ou métrica desejada que você está procurando.

## Métricas de ‘tempo gasto’

| Métrica | Definição | Disponível em |
|---|---|---|
| [[!UICONTROL Total de segundos gastos]](total-seconds-spent.md) | Representa a quantidade total de tempo que os visitantes interagem com um item de dimensão específico. Inclui a instância de um valor e persiste em todas as ocorrências subsequentes. No caso de props, o tempo gasto também é contado em relação a eventos de link subsequentes. | Analysis Workspace, Report Builder (chamado de &quot;tempo total gasto&quot;), Data Warehouse |
| [[!UICONTROL Tempo gasto por visita] (Segundos)](time-spent-per-visit.md) | Aproximadamente *Total de segundos gastos / (rejeições de visita)*<br> Representa a quantidade média de tempo que os visitantes interagem com um item de dimensão específico durante cada visita. **Observação**: esta métrica não pode ser calculada independentemente porque o denominador desta função é uma métrica interna. | Analysis Workspace |
| [[!UICONTROL Tempo gasto por visitante] (Segundos)](time-spent-per-visitor.md) | Aproximadamente *Total de segundos gastos / visitante único*<br> Representa a quantidade média de tempo que os visitantes interagem com um item de dimensão específico ao longo da vida do visitante (duração do cookie). **Observação**: esta métrica não pode ser calculada independentemente porque o denominador desta função é uma métrica interna. | Analysis Workspace |
| [!UICONTROL Tempo gasto/usuário (Estado)] | Aproximadamente *Total de segundos gastos do aplicativo móvel/visitantes únicos do aplicativo móvel*<br> Representa a quantidade média de tempo que os visitantes do aplicativo móvel interagem com um item de dimensão específico ao longo da vida do visitante (duração do cookie). **Observação**: esta métrica não pode ser calculada independentemente porque o denominador desta função é uma métrica interna. | Analysis Workspace |
| [[!UICONTROL Tempo médio gasto no site] (Segundos)](average-time-on-site.md) | Representa a quantidade total de tempo que os visitantes interagem com um item de dimensão específico, por sequência com um item de dimensão. Não se limita apenas a médias de &quot;sites&quot;, como o nome sugere. Consulte a seção &quot;Como o tempo gasto é calculado&quot; para obter mais informações sobre as sequências.<br>**Observação**: esta métrica muito provavelmente será diferente do &quot;Tempo gasto por visita&quot; em nível de item de dimensão devido às diferenças no denominador do cálculo. | Analysis Workspace, Report Builder (mostrado em minutos) |
| [[!UICONTROL Tempo médio no site]](average-time-on-site.md) | Esta é a mesma métrica que *Tempo médio no site (Segundos)*, exceto formatada como Tempo (`hh:mm:ss`) | Analysis Workspace |
| [!UICONTROL Tempo médio gasto na página] | Métrica descontinuada.<br> Em vez disso, o Adobe recomenda que você use [[!UICONTROL Tempo médio gasto no site]](average-time-on-site.md) se o tempo médio para um item de dimensão for necessário. | Report Builder (quando uma dimensão está na solicitação) |

## Dimensões de tempo gasto

| Dimensão | Definição | Disponível em |
| --- | --- | --- |
| [[!UICONTROL Tempo gasto por visita - granular]](../dimensions/time-spent-per-visit.md) | O tempo total gasto durante a visita, truncado no segundo mais próximo e aplicado a cada ocorrência que fez parte da visita. Esta é uma dimensão em nível de visitas. | Analysis Workspace |
| [[!UICONTROL Tempo gasto por visita - sementado]](../dimensions/time-spent-per-visit.md) | A dimensão granular segmentada em 9 intervalos diferentes. Esta é uma dimensão em nível de visitas. Os intervalos incluem:<ul><li>Menos de 1 minuto</li><li>1 a 5 minutos</li><li>5 a 10 minutos</li><li>10 a 30 minutos</li><li>30 a 60 minutos</li><li>1 a 2 horas</li><li>2 a 5 horas</li><li>5 a 10 horas</li><li>10 a 15 horas</li></ul>**Observação**: não poderá haver turnos maiores que esses, pois uma visita expira após 12 horas de atividade. | Analysis Workspace, Report Builder |
| [[!UICONTROL Tempo gasto na página - granular]](../dimensions/time-spent-on-page.md) | O tempo total gasto em cada ocorrência, truncado no segundo mais próximo. É uma dimensão em nível de ocorrência e inclui exibições de página e eventos de link. Apesar do nome, não está limitado à dimensão &quot;página&quot;. | Analysis Workspace |
| [[!UICONTROL Tempo gasto na página - segmentado]](../dimensions/time-spent-on-page.md) | A dimensão granular segmentada em 10 intervalos diferentes; entretanto, a dimensão segmentada somente conta exibições de página (e exclui eventos de links). Essa é uma dimensão em nível de ocorrências. Os intervalos incluem:<ul><li>menos de 15 segundos</li><li>15 a 29 minutos</li><li>30 a 59 minutos</li><li>1 a 3 minutos</li><li>3 a 5 minutos</li><li>5 a 10 minutos</li><li>10 a 15 minutos</li><li>15 a 20 minutos</li><li>20 a 30 minutos</li><li>mais de 30 minutos</li></ul> | Analysis Workspace |

## Como o tempo gasto é calculado

O Adobe Analytics usa valores explícitos (incluindo eventos de link e exibições de vídeo) para calcular o tempo gasto.

>[!NOTE]
>
>Sem eventos de link como [!UICONTROL Exibições de vídeo] ou [!UICONTROL Links de saída], não é possível saber o tempo gasto na última ocorrência de uma visita. Por motivos similares, as [!UICONTROL Visitas rejeitadas] (ou seja Visitas com uma única ocorrência) não terão um Tempo gasto associado.

O **numerador** em todos os cálculos de tempo gasto é o total de segundos gastos.

O **denominador** não está disponível como uma métrica separada no Adobe Analytics. Para métricas de &quot;tempo gasto&quot; em nível de ocorrência, o denominador é a sequência. Uma sequência é um conjunto consecutivo de ocorrências em que uma determinada variável contém o mesmo valor (seja por definição, expansão para a frente ou persistente). &quot;Expansão para a frente&quot; refere-se à persistência das props entre exibições de página (ou seja, em eventos de link subsequentes), para calcular o tempo gasto.

* Por exemplo, no caso do [!UICONTROL Nome de página] ou de outras dimensões no nível de ocorrência, o denominador será, essencialmente, [!UICONTROL Instâncias] ou [!UICONTROL Exibições de página], mas os recarregamentos e valores não definidos (por exemplo, eventos de link) serão contados como uma única interação (uma sequência).

* As ocorrências de Retorno e Saída também são removidas do denominador porque o tempo gasto não pode ser determinado.

## Perguntas frequentes

+++Todas as métricas de tempo gasto podem ser aplicadas a qualquer dimensão?

As métricas de tempo gasto que podem ser aplicadas a qualquer dimensão são:

* [[!UICONTROL Total de segundos gastos]](total-seconds-spent.md)

* [[!UICONTROL Tempo gasto por visita] (segundos)](time-spent-per-visit.md)

* [[!UICONTROL Tempo gasto por visitante] (segundos)](time-spent-per-visitor.md)

* [[!UICONTROL Tempo médio gasto no site] (segundos)](average-time-on-site.md)

+++

+++Qual dimensão de tempo gasto é mais adequada para detalhar com outras dimensões?

A dimensão [[!UICONTROL Tempo gasto na página - granular]](../dimensions/time-spent-on-page.md) é uma dimensão em nível de ocorrência. Detalhar por outra dimensão fornecerá os segundos que uma ocorrência durou, em que a dimensão detalhada também estava presente.
No exemplo abaixo, o termo de pesquisa &quot;classificados&quot; está associado a tempos de ocorrência de 54 segundos, 59 segundos etc., talvez para indicar que os visitantes estão gastando tempo lendo o conteúdo retornado para o termo.

![Captura de tela de um tempo gasto no relatório da página](assets/time-spent1.png)

+++

+++Que métrica é apropriada para a dimensão de [!UICONTROL Tempo gasto na página - granular]?

Qualquer métrica. A dimensão mostra o tempo gasto na ocorrência exata em que o evento ocorreu. Um tempo gasto maior significa que um visitante permaneceu mais tempo na página (ocorrência) em que o evento ocorreu.

![Relatório do Workspace mostrando uma métrica personalizada usada com uma dimensão de tempo gasto](assets/time-spent2.png)

+++

+++Como o [!UICONTROL Tempo médio gasto no site] difere de [!UICONTROL Tempo gasto por visita]?

A diferença é o denominador na métrica:

* [[!UICONTROL Tempo médio gasto no site]](average-time-on-site.md) usa as sequências que incluem um item de dimensão.

* [[!UICONTROL Tempo gasto por visita]](time-spent-per-visit.md) usa a contagem de visitas

Como resultado, essas métricas podem gerar resultados semelhantes no nível da visita, mas são diferentes no nível da ocorrência.

+++

+++Por que os totais de detalhamento com [!UICONTROL Tempo médio gasto no site] não correspondem ao item de linha principal?

Porque [!UICONTROL Tempo médio gasto no site] depende de sequências ininterruptas de uma dimensão, e o relatório interno não depende do relatório externo ao calcular essas execuções.

Por exemplo, considere esta visita.

| Ocorrência # | 1 | 2 | 3 |
|---|---|---|---|
| **Segundos gastos** | 30 | 100 | 10 |
| **Nome da página** | Início | Produto | Início |
| **Data** | Jan 1 | Jan 1 | Jan 1 |

Ao calcular o tempo gasto na página inicial, seria (30+10)/2=20, mas se detalharmos por dia daria (30+10)/1=40, já que o dia tem uma única execução ininterrupta de 1º de janeiro.

Como resultado, essas métricas podem gerar resultados semelhantes no nível da visita, mas são diferentes no nível da ocorrência.

+++

## Exemplos de cálculos de [!UICONTROL Tempo gasto]

Suponha que o seguinte conjunto de chamadas de servidor seja para um único visitante em uma única visita:

| Ocorrência de visita nº | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| **Tempo decorrido da visita (segundos)** | 0 | 30 | 80 | 180 | 190 | 230 | 290 |
| **Segundos gastos** | 30 | 50 | 100 | 10 | 40 | 60 | - |
| **Tipo de ocorrência** | Página | Link | Página | Página | Página | Página | Página |
| **Nome da página** | Início | - | Produto | Início | Página inicial (recarregar) | Carrinho | Confirmação de pedido |
|  |  |  |  |  |  |  |  |
| **prop1** | A (conjunto) | A (distribuir para a frente) | não definido | B (conjunto) | B (conjunto) | A (conjunto) | C (conjunto) |
| **segundos gastos da prop1** | 30 | 50 | - | 10 | 40 | 60 | - |
|  |  |  |  |  |  |  |  |
| **eVar1** | Vermelho (definido) | Vermelho (persistente) | (expirado) | Azul (definido) | Azul (definido) | Azul (persistente) | Vermelho (definido) |
| **Segundos gastos da eVar1** | 30 | 50 | - | 10 | 40 | 60 | - |

Com base na tabela acima, as métricas de Tempo gasto são calculadas da seguinte maneira:

| prop1 | Total de segundos gastos | Tempo gasto por visita | Tempo gasto por visitante | Contagem de sequências | Tempo médio gasto no site |
|---|---|---|---|---|---|
| A | 30+50+60=140 | 140/1=140 | 140/1=140 | 2 | 140/2=70 |
| B | 10+40=50 | 50/1=50 | 50/1=50 | 1 | 50/1=50 |
| C | 0 | 0 | 0 | 0 | 0 |
| Tempo não atribuído | 100 | - | - | - | - |

| eVar1 | Total de segundos gastos | Tempo gasto por visita | Tempo gasto por visitante | Contagem de sequências | Tempo médio gasto no site |
|---|---|---|---|---|---|
| Vermelho | 30+50=80 | 80/1=80 | 80/1=80 | 1 | 80/1=80 |
| Azul | 10+40+60=110 | 110/1=110 | 110/1=110 | 1 | 110/1=110 |
| Tempo não atribuído | 100 | - | - | - | - |

Tempo gasto por visita (granular): 290
Tempo gasto na página (granular): 10, 30, 40, 50, 60, 100

Algumas observações adicionais em apoio ao exemplo:

* Todos os cálculos de Tempo gasto se baseiam no tempo decorrido da visita, que começa em zero na primeira ocorrência da visita.

* &quot;Segundos gastos&quot; é a diferença entre o carimbo de data e hora da ocorrência atual e o da próxima ocorrência. Como resultado, a última ocorrência da visita (e rejeições) não tem tempo gasto.

* Uma &quot;sequência&quot; é um conjunto consecutivo de ocorrências em que uma determinada variável contém o mesmo valor (seja por definição, expansão para a frente ou persistente). Por exemplo, prop1 &quot;A&quot; tem duas sequências: ocorrências 1 e 2 e ocorrência 6. Os valores na última ocorrência da visita não iniciam uma nova sequência porque a última ocorrência não tinha tempo gasto. Tempo médio gasto no site usa as sequências no denominador.

   * Para calcular apenas o tempo gasto, as props são &quot;expandidas para a frente&quot; a partir das ocorrências de página para ocorrências de link subsequentes, conforme mostrado acima para prop1 na ocorrência 2. Isso permite que o valor definido para prop1 na ocorrência 1 (&quot;A&quot;) acumule o tempo gasto na ocorrência 2.

   * As eVars acumulam o Tempo gasto em qualquer ocorrência em que a eVar estiver definida ou mantida. A persistência de eVar é definida pelas configurações de eVar no Analytics > Administração.
