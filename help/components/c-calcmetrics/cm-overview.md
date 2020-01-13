---
description: Métricas calculadas e calculadas avançadas (ou derivadas) são métricas personalizadas que podem ser criadas a partir de métricas existentes.
keywords: Calculated Metrics;Derived Metrics;Advanced Calculated Metrics
title: Métricas calculadas e calculadas avançadas (derivadas)
uuid: 2553c115-b15a-4109-8de2-733dbc1eeb9e
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Métricas calculadas e calculadas avançadas (derivadas)

Métricas calculadas e calculadas avançadas (ou derivadas) são métricas personalizadas que podem ser criadas a partir de métricas existentes.

>[!IMPORTANT]
>
>Em julho de 2018, o Adobe introduziu o [Attribution IQ](https://marketing.adobe.com/resources/help/pt_BR/analytics/analysis-workspace/attribution.html), que reimaginou a maneira que modelos de alocação em métricas calculadas são avaliados. Como parte dessa alteração, as métricas calculadas que usam um modelo de alocação não padrão foram migradas para novos modelos de atribuição melhorados:
>
>* Os modelos de alocação "Último contato do canal de marketing" e "Primeiro contato do canal de marketing" foram migrados para os novos modelos de atribuição "Último contato" e "Primeiro contato", respectivamente (Observação: os "Canais de marketing" não serão descontinuados - apenas os dois modelos de alocação que aparecem nas métricas calculadas foram).
>* Além disso, corrigimos a maneira como a alocação linear é calculada. Para clientes que usam métricas calculadas com modelos de alocação "linear", os relatórios podem ser levemente alterados para refletir o novo modelo de atribuição corrigido. Essa alteração nas métricas calculadas é refletida nos recursos [!UICONTROL Analysis Workspace], [!UICONTROL Reports &amp; Analytics], API de relatório, Report Builder e Ad Hoc Analysis. Para obter mais informações, consulte [Como a alocação linear funcionará a partir de 19 de julho de 2018](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md#section_EDBB2E14A6C248C5A79C0913C02D7CA1).


Nossas ferramentas para métricas calculadas oferecem uma maneira muito mais flexível para criar, gerenciar e preparar métricas. Elas permitem que os profissionais de marketing, gerentes de produtos e analistas façam perguntas sobre os dados sem precisarem alterar a implementação do [!DNL Analytics]. As métricas personalizadas disponíveis em cada pacote do [!DNL Analytics] são:

* Adobe [!DNL Analytics] Foundation: calculadas
* [Adobe Analytics Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html): calculadas + calculadas avançadas
* [Adobe Analytics Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html): Calculadas + Calculadas avançadas
* [Adobe Analytics Ultimate](https://www.adobe.com/br/data-analytics-cloud/analytics/ultimate.html): Calculadas + Calculadas avançadas

Veja uma comparação entre os recursos de Métricas calculadas e Métricas calculadas avançadas:

| Opções do criador | Métricas calculadas | Métricas calculadas avançadas (derivadas) |
|---|---|---|
| [Tipos de formatos (decimal, hora, percentual, moeda)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) | Sim | Sim |
| [Alterações de atribuição (padrão, linear, participação etc.)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Sim | Sim |
| [Tipos de métrica (padrão, total)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Sim | Sim |
| Operadores básicos (adição, subtração, multiplicação, divisão) | Sim | Sim |
| [Aplicar segmentos](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) | Não | Sim |
| [Funções básicas (contagem, valor absoluto, meio etc.)](/help/components/c-calcmetrics/cm-reference/cm-functions.md) | Não | Sim |
| [Funções avançadas (regressão, if/then, t-score etc.)](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) | Não | Sim |

## Capacidades  {#section_A0A5C275B68A4D628950BBB0B1EE631F}

É possível

* Crie métricas entre a [!UICONTROL Analysis Workspace], [!UICONTROL Reports &amp; Analytics], [!UICONTROL Ad Hoc Analysis], [!UICONTROL Report Builder], [!UICONTROL Detecção de anomalias] e [!UICONTROL Análise de contribuição].
* Crie métricas segmentadas derivadas do tempo de execução do relatório, sem precisar [alterar a implementação](https://youtu.be/CuQTm9RaUpY). Essas métricas podem ser exibidas historicamente, pois se baseiam em segmentos.
* Compartilhe métricas em conjuntos de relatórios. Isso significa que todas as métricas recém-criadas se aplicam a todos os conjuntos de relatórios da mesma empresa de logon.
* (Somente métricas calculadas avançadas) Segmente as métricas. Por exemplo, é possível criar uma métrica para “Novos visitantes”, com uma contagem de pessoas para as quais esta é a primeira sessão.
* (Somente métricas calculadas avançadas) Incorpore funções estatísticas para ajudar a descrever melhor seus dados. Por exemplo, é possível contar o número de itens em um relatório ou adicionar o número de desvios padrão para cada item.
* Utilize as métricas criadas na [!UICONTROL Ad Hoc Analysis] em outras ferramentas do [!DNL Analytics], e vice-versa.

   >[!NOTE]
   >
   >Você pode continuar a criar métricas na Ad Hoc Analysis. Agora, a interface do usuário do criador de métricas calculadas é similar ao novo criador de métricas.

## Limitações {#section_CB878B02451541D68A68B508D4DBD19A}

Alguns recursos do [!DNL Analytics] permitem usar eventos, mas não permitem usar métricas calculadas:

* [!UICONTROL Funis] no [!UICONTROL Reports &amp; Analytics]
* [!UICONTROL Fallout] na [!UICONTROL Analysis Workspace]
* [!UICONTROL Análise de coorte] na Analysis Workspace
* [!UICONTROL Data Warehouse]
* [!UICONTROL Segmentos]
* [!UICONTROL Relatórios em Tempo real]
* [!UICONTROL Relatórios de Dados atuais]
* [!DNL Analytics] for [!DNL Target]

## Ferramentas {#section_D65E9C067E9C45E1A50DD30F50561BB2}

Esta é uma pequena visão geral das ferramentas de [!UICONTROL Métricas calculadas]:

<table id="table_520AFE97DB514958ABE23FD3C9CE0ABD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ferramenta </th> 
   <th colname="col2" class="entry"> Capacidades </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md"  > Criador de métricas calculada</a> </td> 
   <td colname="col2"> 
    <ul id="ul_E6F02AB9DF204C2F9A0AC92A31594B3E"> 
     <li id="li_A4A6E716374243A190C539A3F4A41C0C">Crie métricas calculadas e calculadas avançadas usando modelos de alocação avançados. </li> 
     <li id="li_C8C97BA4E227463E98077ABA5818FFC6">Adicionar segmentos em linha às fórmulas de métricas. </li> 
     <li id="li_8503D9E06A3C46569B5CDB4B90F72446">Comparar segmentos em um mesmo relatório. É possível, por exemplo, comparar visitantes locais com visitantes internacionais. </li> 
     <li id="li_4B528FDE1F96400DBA0D3276408FF919">Usar funções estatísticas. </li> 
     <li id="li_C1162B1EA6784B8189A8A87E2B0DA79A">Fornecer descrições de métricas detalhadas (mostrar o que ela faz, quando usá-la, quando NÃO usá-la). </li> 
     <li id="li_DEA13F5E8BF94AF1B311C467FE6E2A74">Copiar definições em novas métricas. </li> 
     <li id="li_8C21F55015D44910904202D2BF74221C">Fornecer uma visualização da métrica em linha. </li> 
     <li id="li_3704F66C321C477F9D4F52E068C231BD">Definir a polaridade da métrica, que indica se ela é boa ou ruim caso um determinado evento personalizado (métrica) apresente uma tendência para cima. </li> 
     <li id="li_9D45319FA965476FB1C90DE8AA72BBD7">Adicionar tags às métricas. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md"  > Gerenciador de métricas calculadas</a> </td> 
   <td colname="col2"> 
    <ul id="ul_E4D20D5DD3904CC6A85785B5BD4C1B1E"> 
     <li id="li_E0B216BA1478406EB6212263DF71D85B">Compartilhar métricas com outras pessoas. </li> 
     <li id="li_96EB16FAF3454211AAEF78EA5B08927F">Aprovar e controlar métricas. </li> 
     <li id="li_3ADBD2428EAC4B0AA61222D87C3AF2B7">Organizar (marcar com tags) suas métricas de forma que as pessoas possam encontrá-las. </li> 
     <li id="li_726F3C3390744E49BA63606FE196880E">Excluir métricas. </li> 
     <li id="li_F306BA4FA8AF4A6E987BA62634659A2F">Renomear as métricas. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Painel Seletor de métricas </td> 
   <td colname="col2"> <p>Substitui o menu pop-up <span class="uicontrol">Mostrar métricas</span> no<span class="uicontrol"> Reports &amp; Analytics</span>. </p> <p>Permite pesquisar e adicionar/aplicar métricas ao relatório. Também é possível alterar a ordem de  <a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-finding.md"  > classificação</a> (as opções incluem: alfabética, recomendado, usados com frequência, usados recentemente.) Além disso, é possível filtrar os Conjuntos de relatórios para mostrar apenas as métricas criadas em um conjunto de relatórios específico. </p> <p>Para acessar o Seletor de métricas, clique no ícone Métricas <img placement="inline"  src="assets/metrics_icon.png" width="30px" id="image_2C6F20B4E634486B95BACD4CA47EF991" /> à esquerda de um relatório. O Seletor de métricas tem a seguinte aparência: </p> <p><img src="assets/metrics_rail.png" width="200px" id="image_379523E9AFEC4CF08D20C42C740AA358" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/README.md"  > API para métricas calculadas</a> </td> 
   <td colname="col2"> <p>Parte do conjunto de APIs do Adobe Analytics 2.0. </p> </td> 
  </tr> 
 </tbody> 
</table>

