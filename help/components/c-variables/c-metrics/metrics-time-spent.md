---
description: O Adobe Analytics oferta várias métricas e dimensões de Tempo gasto. Descubra o que eles são e como são calculados.
title: Tempo gasto
topic: Metrics
translation-type: tm+mt
source-git-commit: 8df1fdfb048dd69b4926b7b812ec5dfea4a97b89

---


# [!UICONTROL Time spent]

Various [!UICONTROL 'time spent'] metrics and dimensions are offered across Adobe Analytics products.

## [!UICONTROL 'Time spent'] métricas

| Métrica | Definição | Disponível em |
|---|---|---|
| [!UICONTROL Total seconds spent] | Representa a quantidade total de tempo que os visitantes interagem com um item de dimensão específico. Inclui a instância de um valor e persiste em todas as ocorrências subsequentes. No caso de props, o tempo gasto também é contado em relação a eventos de link subsequentes. | Analysis Workspace, Reports &amp; Analytics, Report Builder (chamado de &quot;tempo total gasto&quot;), Data Warehouse, Ad Hoc Analysis |
| [!UICONTROL Time spent per visit] (Segundos) | *Tempo total gasto / (rejeições de visita)*<br>Representa a quantidade média de tempo que os visitantes interagem com um item de dimensão específico durante cada visita. | Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis |
| [!UICONTROL Time spent per visitor] (Segundos) | *Segundos totais gastos / visitante único *<br>Representa a quantidade média de tempo que os visitantes interagem com um item de dimensão específico ao longo da vida do visitante (duração do cookie). | Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis |
| [!UICONTROL Average time spent on site] (Segundos) | Representa a quantidade total de tempo que os visitantes interagem com um item de dimensão específico, por sequência com um item de dimensão. Não se limita apenas às médias do &quot;site&quot;, como o nome sugere. Consulte a seção &quot;Como o tempo gasto é calculado&quot; para obter mais informações sobre as sequências.<br>**Observação **: esta métrica muito provavelmente será diferente do &quot;Tempo gasto por visita&quot; em nível de item de dimensão devido às diferenças no denominador do cálculo. | Analysis Workspace, Reports &amp; Analytics (mostrado em minutos), Report Builder (mostrado em minutos), Ad Hoc Analysis |
| [!UICONTROL Average time spent on page] | Métrica descontinuada.<br> Em vez disso, é recomendado usar &quot;Tempo médio gasto no site&quot; se o tempo médio para um item de dimensão for necessário. | Report Builder (quando uma dimensão está na solicitação) |
| [!UICONTROL Total session length], t.c.p. [!UICONTROL Previous session length] | Somente SDK do aplicativo para dispositivo móvel. <br>Determinada na próxima vez que o aplicativo for inicializado, para a sessão anterior. Calculada em segundos, essa métrica não conta quando o aplicativo está em segundo plano, somente quando está em uso. Esta é uma métrica em nível de sessão.<br>Exemplo: você instala o aplicativo ABC e o inicializa; em seguida, usa o aplicativo por 2 minutos e o fecha. Nenhum dado é enviado sobre este tempo de sessão. The next time we launch the app, [!UICONTROL Previous Session Length] will be sent with a value of 120. | Analysis Workspace, Reports &amp; Analytics, Report Builder, Interface do usuário do Mobile Services |
| [!UICONTROL Average session length] (dispositivo móvel) | *Duração total da sessão / (Inicializações - Primeiras inicializações)*<br>Somente SDK do aplicativo móvel. Esta é uma métrica em nível de sessão. | Report Builder, interface do usuário do Mobile Services, Ad Hoc Analysis |

## Dimensões de tempo gasto

| Dimensão | Definição | Disponível em |
|---|---|---|
| [!UICONTROL Time spent per visit - granular] | O tempo total gasto durante a visita, truncado no segundo mais próximo e aplicado a cada ocorrência que fez parte da visita. Esta é uma dimensão em nível de visitas. | Analysis Workspace, Ad Hoc Analysis |
| [!UICONTROL Time spent per visit - bucketed] | A dimensão granular segmentada em 9 intervalos diferentes. Esta é uma dimensão em nível de visitas. Os intervalos incluem:<ul><li>Menos de 1 minuto</li><li>1 a 5 minutos</li><li>5 a 10 minutos</li><li>10 a 30 minutos</li><li>30 a 60 minutos</li><li>1 a 2 horas</li><li>2 a 5 horas</li><li>5 a 10 horas</li><li>10 a 15 horas</li></ul>**Observação**: não poderá haver turnos maiores que esses, pois uma visita expira após 12 horas de atividade. | Analysis Workspace, Reports &amp; Analytics, Report Builder, Ad Hoc Analysis |
| [!UICONTROL Time spent on page - granular] | O tempo total gasto em cada ocorrência, truncado no segundo mais próximo. É uma dimensão em nível de ocorrência e inclui exibições de página e eventos de link. Apesar do nome, não está limitado à dimensão &quot;página&quot;. | Analysis Workspace, Ad Hoc Analysis |
| [!UICONTROL Time spent on page - bucketed] | A dimensão granular dividida em 10 intervalos diferentes; no entanto, a dimensão segmentada conta somente visualizações de página (e exclui eventos de link). Esta é uma dimensão de nível de ocorrência. Os intervalos incluem:<ul><li>menos de 15 segundos</li><li>15 a 29 minutos</li><li>30 a 59 minutos</li><li>1 a 3 minutos</li><li>3 a 5 minutos</li><li>5 a 10 minutos</li><li>10 a 15 minutos</li><li>15 a 20 minutos</li><li>20 a 30 minutos</li><li>mais de 30 minutos</li></ul> | Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis |

## Como o tempo gasto é calculado

Adobe Analytics uses explicit values (including link events and video views) to calculate [!UICONTROL Time Spent].

>[!NOTE]
>
>Without link events like [!UICONTROL Video Views] or [!UICONTROL Exit Links], time spent on the last hit of a visit cannot be known. For similar reasons, [!UICONTROL Bounce Visits] (i.e. visits with a single hit) also does not have a &#39;time spent&#39; associated with it.

O **numerador** em todos os cálculos de tempo gasto é o total de segundos gastos.

O **denominador** não está disponível como uma métrica separada no Adobe Analytics. Para métricas de &quot;tempo gasto&quot; em nível de ocorrência, o denominador é a sequência. Uma sequência é um conjunto consecutivo de ocorrências em que uma determinada variável contém o mesmo valor (seja por definição, expansão para a frente ou persistente). &quot;Expansão para a frente&quot; refere-se à persistência das props entre exibições de página (ou seja, em eventos de link subsequentes), para calcular o tempo gasto.

* For example, in the case of [!UICONTROL Page Name] or other dimensions at the hit level, the denominator is essentially [!UICONTROL 'Instances'] or [!UICONTROL 'Page Views'], but with reloads and unset values (e.g. link events) counted as a single interaction (a sequence).

* As ocorrências de Retorno e Saída também são removidas do denominador porque o tempo gasto não pode ser determinado.

## Perguntas frequentes

**P1: Todas as métricas de tempo gasto podem ser aplicadas a qualquer dimensão?**

R: As métricas de &quot;tempo gasto&quot; que podem ser aplicadas a qualquer dimensão são:

* [!UICONTROL Total seconds spent]

* [!UICONTROL Time spent per visit] (Segundos)

* [!UICONTROL Time spent per visitor] (Segundos)

* [!UICONTROL Average time spent on site] (Segundos)

**P2: Qual dimensão de tempo gasto é mais adequada para detalhar com outras dimensões?**

A: A [!UICONTROL Time Spent on Page – granular] dimensão é uma dimensão em nível de ocorrência. Detalhar por outra dimensão fornecerá os segundos que uma ocorrência durou, em que a dimensão detalhada também estava presente.
No exemplo abaixo, o termo de pesquisa “classificados” está associado a tempos de ocorrência de 54 segundos, 59 segundos etc., talvez para indicar que os visitantes estão gastando tempo lendo o conteúdo retornado para o termo.

![](assets/time-spent1.png)

**T3: Qual métrica é apropriada em relação à dimensão de[!UICONTROL Time Spent on Page – granular]?**

R: Qualquer métrica. A dimensão mostra o tempo gasto na ocorrência exata em que o evento ocorreu. Um tempo gasto maior significa que um visitante permaneceu mais tempo na página (ocorrência) em que o evento ocorreu.

![](assets/time-spent2.png)

**T4: Qual é a diferença entre[!UICONTROL Average Time Spent on Site]a[!UICONTROL Time Spent per Visit]?**

R: A diferença é o denominador na métrica:

* [!UICONTROL Average time spent on site] usa as sequências que incluem um item de dimensão.

* [!UICONTROL Time spent per visit] usa a contagem de visitas

Como resultado, essas métricas também podem fornecer resultados semelhantes em nível de visita, mas serão diferentes em nível de ocorrência.

**P5: Por que os totais de detalhamento[!UICONTROL Average Time Spent on Site]não correspondem ao item de linha pai?**

A: Como [!UICONTROL Average Time Spent on Site] depende de sequências não quebradas de uma dimensão, o relatório interno não depende do relatório externo ao calcular essas execuções.

Por exemplo, considere a seguinte visita.
|hit#|1|2|3||—|—|—||**Segundos gastos**|30|100|10||Nome **da** página|Início|Produto|Início||**data**|Jan 1|Jan 1|Jan 1|

Ao calcular o tempo gasto para a página inicial, seria (30+10)/2=20, mas detalhar isso por dia daria (30+10)/1=40, já que o dia tem uma única execução ininterrupta de 1º de janeiro.

Como resultado, essas métricas também podem fornecer resultados semelhantes em nível de visita, mas serão diferentes em nível de ocorrência.

## Exemplos de [!UICONTROL Time Spent] cálculos

Suponha que o seguinte conjunto de chamadas de servidor seja para um único visitante em uma única visita:

| Ocorrência de visita nº | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| **Tempo decorrido da visita** (segundos) | 0 | 30 | 80 | 180 | 190 | 230 | 290 |
| **Segundos gastos** | 30 | 50 | 100 | 10 | 40 | 60 | - |
| **Tipo de ocorrência** | Página | Link | Página | Página | Página | Página | Página |
| **Nome da página** | Início | - | Product | Início | Início  (recarga) | Carrinho | Confirmação de pedido |
|  |  |  |  |  |  |  |  |
| **prop1** | A (conjunto) | A (distribuir para a frente) | não definido | B (conjunto) | B (conjunto) | A (conjunto) | C (conjunto) |
| **segundos gastos de prop1** | 30 | 50 | - | 10 | 40 | 60 | - |
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
| Vermelho  | 30+50=80 | 80/1=80 | 80/1=80 | 1 | 80/1=80 |
| Azul  | 10+40+60=110 | 110/1=110 | 110/1=110 | 1 | 110/1=110 |
| Tempo não atribuído | 100 | - | - | - | - |

Tempo gasto por visita (granular): 290
Tempo gasto na página (granular): 10, 30, 40, 50, 60, 100

Algumas observações adicionais em apoio ao exemplo:

* Todos os cálculos de Tempo gasto se baseiam no tempo decorrido da visita, que começa em zero na primeira ocorrência da visita.

* “Segundos gastos” é a diferença entre o registro de data e hora da ocorrência atual e o registro de data e hora da próxima ocorrência. Como resultado, a última ocorrência da visita (e rejeições) não tem tempo gasto.

* Uma &quot;sequência&quot; é um conjunto consecutivo de ocorrências em que uma determinada variável contém o mesmo valor (seja por definição, expansão para frente ou persistente). Por exemplo, prop1 &quot;A&quot; tem duas sequências: ocorrências 1 e 2 e ocorrência 6. Os valores na última ocorrência da visita não start uma nova sequência porque a última ocorrência não tem tempo gasto. O tempo médio gasto no site usa sequências no denominador.

   * Para calcular apenas o Tempo gasto, as props são “expandidas para a frente” a partir das ocorrências de página para ocorrências de link subsequentes, conforme mostrado acima para prop1 na ocorrência 2. Isso permite que o valor definido para prop1 na ocorrência 1 (“A”) acumule o tempo gasto na ocorrência 2.

   * As eVars acumulam o Tempo gasto em qualquer ocorrência em que a eVar estiver definida ou mantida. A persistência de eVar é definida pelas configurações de eVar no Analytics > Administração.

