---
description: O Adobe Analytics oferece várias métricas e dimensões de Tempo gasto. Descubra o que são e como são calculadas.
seo-description: O Adobe Analytics oferece várias métricas e dimensões de Tempo gasto. Descubra o que são e como são calculadas.
seo-title: Tempo gasto
solution: Analytics
title: Tempo gasto
topic: Métricas
uuid: a 9 f 63 da 3-7 e 79-49 c 3-9 b 0 b -6 dcd 2 ae 6 aadc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Tempo gasto

O Adobe Analytics oferece várias métricas e dimensões de Tempo gasto. Descubra o que são e como são calculadas.

* [Métricas de tempo gasto](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_4F54D70300944748A62088F5870E4B6C)
* [Dimensões de tempo gasto](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_D51606544CB046FC902E2E317318892C)
* [Como o tempo gasto é calculado](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_90A3882638974969A4B8B674FFDB7624)
* [Perguntas frequentes sobre tempo gasto](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_51C2735BACAB42CCBA1DD3CBF238E2F7)
* [Exemplos de cálculos](../../../components/c-variables/c-metrics/metrics-time-spent.md#section_3D63D6A601F34E42AD5366435CB610D5)

## Métricas de tempo gasto {#section_4F54D70300944748A62088F5870E4B6C}

Esta tabela lista as diferentes métricas de Tempo gasto, suas definições e onde você pode usá-las no Adobe Analytics.

<table id="table_7095406DF1614F3CAD5E437B919598D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Métrica </th> 
   <th colname="col2" class="entry"> Definição </th> 
   <th colname="col3" class="entry"> Disponível em </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Total de segundos gastos </p> </td> 
   <td colname="col2"> <p>Representa a quantidade total de tempo que os visitantes interagem com um item de dimensão específico. </p> <p>Inclui a instância de um valor e persiste em todas as ocorrências subsequentes. No caso de props, o tempo gasto também é contado em relação a eventos de link subsequentes. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> <p>Report Builder (chamado de “tempo total gasto”) </p> <p>Data Warehouse </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo gasto por visita (segundos) </p> </td> 
   <td colname="col2"> <p><i>Total de segundos gastos / (rejeições de visitas)</i> </p> <p>Representa a quantidade média de tempo que os visitantes interagem com um item de dimensão específico durante cada visita. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo gasto por visitante (segundos) </p> </td> 
   <td colname="col2"> <p><i>Total de segundos gastos / (visitante único - rejeição de visitantes únicos)</i> </p> <p>Representa a quantidade média de tempo que os visitantes interagem com um item de dimensão específico ao longo da vida do visitante (duração do cookie). </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo médio gasto no site (segundos) </p> </td> 
   <td colname="col2"> <p>Representa a quantidade total de tempo que os visitantes interagem com um item de dimensão específico, por sequência com um item de dimensão. Não está limitado a médias de “site” como o nome sugere. Veja como a seção Tempo gasto é calculada para obter mais informações sobre as sequências. </p> <p>Observação: esta métrica muito provavelmente será diferente do Tempo gasto por visita em nível de item de dimensão devido às diferenças no denominador do cálculo. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics (mostrado em minutos) </p> <p>Report Builder (mostrado em minutos) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo médio gasto na página </p> </td> 
   <td colname="col2"> <p><b>Métrica descontinuada. </b> </p> <p>É recomendado usar “Tempo médio gasto no site” se o tempo médio para um item de dimensão for necessário. </p> </td> 
   <td colname="col3"> <p>Report Builder (quando uma dimensão está na solicitação) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Duração total da sessão </p> <p>(Também conhecido como: duração da sessão anterior) </p> </td> 
   <td colname="col2"> <p>Somente SDK do aplicativo para dispositivo móvel. Determinada na próxima vez que o aplicativo for inicializado, para a sessão anterior. Calculado em segundos, esta métrica não contabiliza quando o aplicativo está em segundo plano, somente quando está em uso. Esta é uma métrica em nível de sessão. </p> <p>Por exemplo: você instala o aplicativo ABC e o inicializa; em seguida, usa o aplicativo por 2 minutos e o fecha. Nenhum dado é enviado sobre isso neste tempo de sessão. Na próxima vez que você inicializar o aplicativo, a Duração total da sessão será enviada com um valor de 120. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> <p>Report Builder </p> <p>Interface do usuário do Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Duração média da sessão (dispositivos móveis) </p> </td> 
   <td colname="col2"> <p>Duração total da sessão/(Inicializações - Primeiras inicializações) </p> <p>Somente SDK do aplicativo para dispositivo móvel. Esta é uma métrica em nível de sessão. </p> </td> 
   <td colname="col3"> <p>Report Builder </p> <p>Interface do usuário do Mobile Services </p> </td> 
  </tr> 
 </tbody> 
</table>

## Dimensões de tempo gasto {#section_D51606544CB046FC902E2E317318892C}

Esta tabela lista as diferentes dimensões de Tempo gasto, suas definições e onde você pode usá-las no Adobe Analytics.

<table id="table_BF1B7B8620714105BFB5C1AC37ABE02C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimensão </th> 
   <th colname="col2" class="entry"> Definição </th> 
   <th colname="col3" class="entry"> Disponível em </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Tempo gasto por visita - granular </p> </td> 
   <td colname="col2"> <p>O tempo total gasto durante a visita, truncado no segundo mais próximo e aplicado a cada ocorrência que fez parte da visita. Esta é uma dimensão em nível de visitas. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo gasto por visita - sementado </p> </td> 
   <td colname="col2"> <p>A dimensão granular segmentada em 9 intervalos diferentes. Esta é uma dimensão em nível de visitas. Os intervalos incluem: </p> 
    <ul id="ul_BC909A2D22ED4D48A3F7CE6A666F26E5"> 
     <li id="li_0FB28A1F0D894B7C95724A8C6BD5B00B">Menos de 1 minuto </li> 
     <li id="li_10223656420A475AAB3443981D49D10E">1 a 5 minutos </li> 
     <li id="li_0DEE723B81C64EAFB5BD1125D48D3AD2">5 a 10 minutos </li> 
     <li id="li_B736AC970E0049EB8844480702F345A6">10 a 30 minutos </li> 
     <li id="li_21B8ECC3EE66497E8D870A004351B04B">30 a 60 minutos </li> 
     <li id="li_79FB658128FD4F97AAE1A803F1687BD1">1 a 2 horas </li> 
     <li id="li_CCC0746FEB954BECB9E670ECCDBF30F3">2 a 5 horas </li> 
     <li id="li_BD7AFC524C814F9FAE423A4E301661D4">5 a 10 horas </li> 
     <li id="li_C9B5F1A83F99437A98A61756EE286687">10 a 15 horas </li> 
     <li id="li_8CC5A279D5804C5EA34C1B3589EF07BA">15+ horas </li> 
    </ul> <p>Observação: pode haver visitas com mais de 12 horas de duração quando ocorrências são recebidas fora de ordem. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> <p>Report Builder </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo gasto na página - granular </p> </td> 
   <td colname="col2"> <p>O tempo total gasto em cada ocorrência, truncado no segundo mais próximo. É uma dimensão em nível de ocorrência e inclui exibições de página e eventos de link. Não está limitado à dimensão de “página”, como o nome sugere. </p> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tempo gasto na página - segmentado </p> </td> 
   <td colname="col2"> <p>A dimensão granular segmentada em 10 intervalos diferentes; entretanto, a dimensão segmentada somente conta exibições de página (e exclui eventos de links). Essa é uma dimensão em nível de ocorrências. Os intervalos incluem: </p> 
    <ul id="ul_D5F067A2520646A99AA261F9A4625C03"> 
     <li id="li_82307DE66EC548F0AD79DB1505A21F0D">menos de 15 segundos </li> 
     <li id="li_585965B82C4D43B6870978A5CE63B5B6">15 a 29 minutos </li> 
     <li id="li_5C20DC78E126472A838818EBA1D954D0">30 a 59 minutos </li> 
     <li id="li_2579C0B9279340ABA3AD4A527D758239">1 a 3 minutos </li> 
     <li id="li_E0FD800E948049A48DB4329A3E7A2478">3 a 5 minutos </li> 
     <li id="li_D9DBBFE6004F42BD80BB4F9268DF7DA7">5 a 10 minutos </li> 
     <li id="li_20F146799679456E8D6434D79EE12C31">10 a 15 minutos </li> 
     <li id="li_A38951A553A14AE7A0F23A904EEE35DE">15 a 20 minutos </li> 
     <li id="li_D44D773A344E47BFAA771302A49D8BD4">20 a 30 minutos </li> 
     <li id="li_8766683DB29147CD8470D2317F750E97">mais de 30 minutos </li> 
    </ul> </td> 
   <td colname="col3"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> </td> 
  </tr> 
 </tbody> 
</table>

## Como o tempo gasto é calculado {#section_90A3882638974969A4B8B674FFDB7624}

O Adobe Analytics usa valores explícitos (incluindo eventos de link e exibições de vídeo) para calcular o [!UICONTROL Tempo gasto].

>[!NOTE]
>
>Without link events like [!UICONTROL Video Views] or [!UICONTROL Exit Links], time spent on the last hit of a visit cannot be known. Adicionalmente, por motivos similares, as [!UICONTROL Visitas rejeitadas] (ou seja [!UICONTROL Visitas] com uma única ocorrência) não terão um [!UICONTROL Tempo gasto] associado.

O **numerador** em todos os cálculos de tempo gasto é “Total de segundos gastos”.

O **denominador** não está disponível como uma métrica separada no Analytics. Para métricas de tempo gasto em nível de ocorrência, o denominador é as sequências. Uma sequência é um conjunto consecutivo de ocorrências em que uma determinada variável contém o mesmo valor (seja por definição, expansão para a frente ou persistente). “Expansão para a frente” refere-se à persistência das props entre exibições de página (ou seja, em eventos de link subsequentes), para calcular o tempo gasto.

* Por exemplo, no caso do [!UICONTROL Nome de página] ou de outras dimensões no nível de ocorrência, o denominador será, essencialmente, [!UICONTROL Instâncias] ou [!UICONTROL Exibições de página], mas os recarregamentos e valores não definidos (por exemplo, eventos de link) serão contados como uma única interação (uma sequência).

* As ocorrências de [!UICONTROL Retorno] e [!UICONTROL Saída] também são removidas do denominador porque o tempo gasto não pode ser determinado.

## Perguntas frequentes sobre tempo gasto {#section_51C2735BACAB42CCBA1DD3CBF238E2F7}

<table id="table_D8BA825412B6420390CA78D77A5E57C2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pergunta </th> 
   <th colname="col2" class="entry"> Resposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Todas as métricas de tempo gasto podem ser aplicadas a qualquer dimensão? </p> </td> 
   <td colname="col2"> <p>Essas métricas de tempo gasto podem ser aplicadas a qualquer dimensão: </p> 
    <ul id="ul_FC9513D0184B4A74BA1F4CCEA8BC1940"> 
     <li id="li_669156CC549040E08AB4977AF4B8AECB">Total de segundos gastos </li> 
     <li id="li_3CCD7E7D127448689228E98A5EE854CB">Tempo gasto por visita (segundos) </li> 
     <li id="li_1F61C157EC414C7F8702BC3F365AA2D7">Tempo gasto por visitante (segundos) </li> 
     <li id="li_A3EF959A9BAB4872915F1A5C1A86D48E">Tempo médio gasto no site (segundos) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qual dimensão de tempo gasto é mais adequada para detalhar com outras dimensões? </p> </td> 
   <td colname="col2"> <p>A dimensão «Tempo gasto na página - granular» é uma dimensão em nível de ocorrência. Detalhar por outra dimensão fornecerá os segundos que uma ocorrência durou, em que a dimensão detalhada também estava presente. </p> <p>No exemplo abaixo, o termo de pesquisa “classificados” está associado a tempos de ocorrência de 54 segundos, 59 segundos etc., talvez para indicar que os visitantes estão gastando tempo lendo o conteúdo retornado para o termo de pesquisa. </p> <p><img placement="break" align="center"  src="assets/time-spent1.png" id="image_99FB62DCADDA4F8887B14333E65FF8FA" width="500px" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qual métrica é apropriada para a dimensão de «Tempo gasto na página - granular»? </p> </td> 
   <td colname="col2"> <p>Qualquer métrica. A dimensão mostra o tempo gasto na ocorrência exata em que o evento ocorreu. Um tempo gasto maior significa que um visitante permaneceu mais tempo na página (ocorrência) em que o evento ocorreu. </p> <p><img placement="break" align="center"  src="assets/time-spent2.png" id="image_A741C1BA52254124B5C28D030FE20EFF" width="500px" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Qual a diferença entre o <span class="wintitle">Tempo médio gasto no site</span> e o <span class="wintitle">Tempo gasto por visita </span>? </td> 
   <td colname="col2"> <p>A diferença é o denominador na métrica: </p> 
    <ul id="ul_E9D7B4D3EDCC4691B2C724E0FE5480D2"> 
     <li id="li_CA34D84A3164473A8737D258425CA468"> <span class="wintitle"> Tempo médio gasto no site</span> usa as sequências que incluem um item de dimensão. </li> 
     <li id="li_2F2639480BE24927919732D00364EECA"> <span class="wintitle"> Tempo gasto por visita</span> usa a contagem de visitas </li> 
    </ul> <p>Como resultado, essas métricas também podem fornecer resultados semelhantes em nível de visita, mas serão diferentes em nível de ocorrência. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemplos de cálculos {#section_3D63D6A601F34E42AD5366435CB610D5}

Suponha que o seguinte conjunto de chamadas de servidor seja para um único visitante em uma única visita:

<table id="table_63CBB5097E5A46659877E2CA3C94D81C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ocorrência de visita nº </th> 
   <th colname="col2" class="entry"> 1 </th> 
   <th colname="col3" class="entry"> 2 </th> 
   <th colname="col4" class="entry"> 3 </th> 
   <th colname="col5" class="entry"> 4 </th> 
   <th colname="col6" class="entry"> 5 </th> 
   <th colname="col7" class="entry"> 6 </th> 
   <th colname="col8" class="entry"> 7 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Tempo decorrido da visita (segundos)</b> </td> 
   <td colname="col2"> 0 </td> 
   <td colname="col3"> 30 </td> 
   <td colname="col4"> 80 </td> 
   <td colname="col5"> 180 </td> 
   <td colname="col6"> 190 </td> 
   <td colname="col7"> 230 </td> 
   <td colname="col8"> 290 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segundos gastos</b> </td> 
   <td colname="col2"> 30 </td> 
   <td colname="col3"> 50 </td> 
   <td colname="col4"> 100 </td> 
   <td colname="col5"> 10 </td> 
   <td colname="col6"> 40 </td> 
   <td colname="col7"> 60 </td> 
   <td colname="col8"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Tipo de ocorrência</b> </td> 
   <td colname="col2"> Página </td> 
   <td colname="col3"> Link </td> 
   <td colname="col4"> Página </td> 
   <td colname="col5"> Página </td> 
   <td colname="col6"> Página </td> 
   <td colname="col7"> Página </td> 
   <td colname="col8"> Página </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nome da página</b> </td> 
   <td colname="col2"> Início </td> 
   <td colname="col3"> - </td> 
   <td colname="col4"> Produto </td> 
   <td colname="col5"> Início </td> 
   <td colname="col6"> Início <p>(recarga) </p> </td> 
   <td colname="col7"> Carrinho </td> 
   <td colname="col8"> Confirmação de pedido </td> 
  </tr> 
 </tbody> 
</table>

### Exemplo de eVar

<table id="table_6D0CF0C53DC145D3A53C06EC3012BCC0">  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ocorrência de visita nº </th> 
   <th colname="col2" class="entry"> 1 </th> 
   <th colname="col3" class="entry"> 2 </th> 
   <th colname="col4" class="entry"> 3 </th> 
   <th colname="col5" class="entry"> 4 </th> 
   <th colname="col6" class="entry"> 5 </th> 
   <th colname="col7" class="entry"> 6 </th> 
   <th colname="col8" class="entry"> 7 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>eVar1</b> </td> 
   <td colname="col2"> Vermelho <p>(definido) </p> </td> 
   <td colname="col3"> Vermelho <p>(persistente) </p> </td> 
   <td colname="col4"> (expirado) </td> 
   <td colname="col5"> Azul <p>(definido) </p> </td> 
   <td colname="col6"> Azul <p>(definido) </p> </td> 
   <td colname="col7"> Azul <p>(persistente) </p> </td> 
   <td colname="col8"> Vermelho <p>(definido) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segundos gastos da eVar</b> </td> 
   <td colname="col2"> 30 </td> 
   <td colname="col3"> 50 </td> 
   <td colname="col4"> - </td> 
   <td colname="col5"> 10 </td> 
   <td colname="col6"> 40 </td> 
   <td colname="col7"> 60 </td> 
   <td colname="col8"> - </td> 
  </tr> 
 </tbody> 
</table>

### Exemplo de prop

<table id="table_1CB4D24A6CAA479C8E59A7C77FFB8226">  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ocorrência de visita nº </th> 
   <th colname="col2" class="entry"> 1 </th> 
   <th colname="col3" class="entry"> 2 </th> 
   <th colname="col4" class="entry"> 3 </th> 
   <th colname="col5" class="entry"> 4 </th> 
   <th colname="col6" class="entry"> 5 </th> 
   <th colname="col7" class="entry"> 6 </th> 
   <th colname="col8" class="entry"> 7 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>prop1</b> </td> 
   <td colname="col2"> Um <p>(definido) </p> </td> 
   <td colname="col3"> Um <p>Expansão para a frente </p> </td> 
   <td colname="col4"> (não definido) </td> 
   <td colname="col5"> B <p>definido) </p> </td> 
   <td colname="col6"> B <p>(definido) </p> </td> 
   <td colname="col7"> Um <p>(definido) </p> </td> 
   <td colname="col8"> C <p>(definido) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>segundos gastos da prop1</b> </td> 
   <td colname="col2"> 30 </td> 
   <td colname="col3"> 50 </td> 
   <td colname="col4"> - </td> 
   <td colname="col5"> 10 </td> 
   <td colname="col6"> 40 </td> 
   <td colname="col7"> 60 </td> 
   <td colname="col8"> - </td> 
  </tr> 
 </tbody> 
</table>

Com base na tabela acima, as métricas de Tempo gasto são calculadas da seguinte maneira:

| prop1 | Total de segundos gastos | Tempo Gasto por Visita | Tempo gasto por visitante | Contagem de sequências | Tempo médio gasto no site |
|---|---|---|---|---|---|
| Um | 30+50+60=140 | 140/1=140 | 140/1=140 | 2 | 140/2=70 |
| B | 10+40=50 | 50/1=50 | 50/1=50 | 1 | 50/1=50 |
| C | 0 | 0 | 0 | 0 | 0 |
| Tempo não atribuído | 100 | - | - | - | - |

| eVar1 | Total de segundos gastos | Tempo Gasto por Visita | Tempo gasto por visitante | Contagem de sequências | Tempo médio gasto no site |
|---|---|---|---|---|---|
| Vermelho | 30+50=80 | 80/1=80 | 80/1=80 | 1 | 80/1=80 |
| Azul | 10+40+60=110 | 110/1=110 | 110/1=110 | 1 | 110/1=110 |
| Tempo não atribuído | 100 | - | - | - | - |

Para dimensões de Tempo gasto, as seguintes linhas serão exibidas nos relatórios associados:

* Tempo gasto por visita (granular): 290
* Tempo gasto na página (granular): 10, 30, 40, 50, 60, 100

Algumas observações adicionais em apoio ao exemplo:

* Todos os cálculos de Tempo gasto se baseiam no tempo decorrido da visita, que começa em zero na primeira ocorrência da visita.
* “Segundos gastos” é a diferença entre o registro de data e hora da ocorrência atual e o registro de data e hora da próxima ocorrência. Como resultado, a última ocorrência da visita (e rejeições) não tem tempo gasto.
* Uma “sequência” é um conjunto consecutivo de ocorrências em que uma determinada variável contém o mesmo valor (seja por definição, expansão para a frente ou persistente). Por exemplo, prop1 “A” tem duas sequencias: ocorrências 1 e 2 e ocorrência 6. Os valores na última ocorrência da visita não iniciam uma nova sequência porque a última ocorrência não tinha tempo gasto. Tempo médio gasto no site usa as sequências no denominador.

   * Para calcular apenas o Tempo gasto, os props são “expandidos para a frente” a partir das ocorrências de página para ocorrências de link subsequentes, conforme mostrado acima para prop1 na ocorrência 2. Isso permite que o valor definido para prop1 na ocorrência 1 (“A”) acumule o tempo gasto na ocorrência 2.
   * eVars acumulam o Tempo gasto em qualquer ocorrência em que a eVar estiver definida ou persistida. A persistência de eVar é definida pelas configurações de eVar no Analytics Admin.
