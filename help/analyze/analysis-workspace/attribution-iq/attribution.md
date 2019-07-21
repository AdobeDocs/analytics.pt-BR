---
description: 'null'
seo-description: 'null'
seo-title: Visão geral IQ da atribuição
title: Visão geral IQ da atribuição
uuid: bb 345642-4 f 45-4 fb 8-82 d 0-803248 dd 52 ea
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Visão geral IQ da atribuição

>[!IMPORTANT]
>
>O IQ da atribuição está disponível para todos os clientes nas skus Ultimate, Prime, Select e Foundation do Adobe Analytics.

## Valor comercial do Attribution IQ {#section_E82B97114E1641A8AE911F57AEB3240A}

A “Jornada do cliente” não é linear e só é previsível parcialmente. É mais orgânica, flexível e em sua maior parte, imprevisível. Cada cliente prossegue em seu próprio ritmo, podendo retornar, esperar um momento até avançar, reiniciar etc. Isso dificulta a identificação dos esforços de marketing ao longo da jornada do cliente. Além disso, impede as tentativas de vincular vários canais de dados para responder a perguntas comerciais e resulta em insights de cliente incompletos.

O Attribution IQ do Adobe Analytics permite que equipes de inteligência modernas compreendam como a participação significativa é aplicada ao longo da jornada do cliente, identificando de maneira inteligente pontos de inflexão que causam clientes a direcionar resultados, e consequentemente otimizando iniciativas de marketing.

![](assets/attribution_iq_problem.png)

O Adobe Analytics aprimora a atribuição ao permitir:

* Definir atribuição além de mídias com anúncios: qualquer dimensão, métrica, canal ou evento pode ser aplicado a modelos (ex: pesquisa interna), além de campanhas de marketing.
* Utilizar comparação ilimitada de modelos de atribuição: compare dinamicamente quantos modelos desejar.
* Evitar alterações de implementação: com processamento de tempo de relatório e sessões contextuais, o contexto da jornada do cliente pode ser incorporado e aplicado no tempo de execução.
* Construir a sessão que melhor corresponde ao seu cenário de atribuição.
* Detalhar atribuições por segmentos: compare facilmente o desempenho de seus canais de marketing entre segmentos importantes (ex: Clientes Novos vs. Repetidos, Produto X vs. Produto Y, Nível de fidelidade ou CLV).
* Inspecionar canais cruzados e análise de multi toque: usando diagramas e histogramas de Venn, e resultados de atribuição de tendência.
* Analisar visualmente as principais sequências de marketing: explore visualmente caminhos que levaram à conversão usando as visualizações de fluxo de múltiplos nós e de fallout.
* Criar métricas calculadas: use a quantidade de métodos de alocação de atribuição que desejar.

## O que o Attribution IQ faz? {#section_63B421E9E75B4CCEBA96726CAA37D73E}

O Attribution IQ na Analysis Workspace permite que você adicione vários tipos novos de modelos de atribuição a Tabelas de forma livre, Visualizações e Métricas calculadas. Todos os modelos de atribuição têm dois componentes:

* Um **modelo de atribuição** (ou seja, Primeiro contato, Último contato, Linear etc.). O modelo descreve a distribuição de conversões para as ocorrências em um grupo.
* Uma **janela de lookback de atribuição** (ou seja, visita ou visitante). A janela de lookback descreve quais agrupamentos de ocorrências são considerados para cada modelo.

O seguinte exemplo de jornada do cliente representa os pontos de contato de marketing de um único visitante que abrangem três visitas, três conversões e quatro canais de marketing (pesquisa, exibição, social e email):

![](assets/attribution_example.png)

## Atribuição baseada em instância {#section_A81DBC3B19014CE3894131F1CF72736F}

A atribuição na Analysis Workspace utiliza a “instância” de qualquer dimension, o que significa que modelos de atribuição são aplicados aos valores passados para o Analytics (regras de pós-processamento, VISTA, e Regras de processamento de canais de marketing). Na prática, isso significa que não há diferença entre uma propriedade ou uma eVar (ou qualquer outra dimensão) em termos de modelo de atribuição. Propriedades podem ser definidas para persistirem usando qualquer janela de lookback ou modelo abaixo, e configurações de alocação e expiração para eVars não são usadas (conforme especificado nas configurações de Admin) quando os modelos ou as janelas de lookback de atribuição são aplicadas.

## Janela de lookback de atribuição {#section_A2782BB64171431EB370CDCD4AD8030D}

A janela de lookback de atribuição é um grupo de ocorrências ao qual um modelo de atribuição será aplicado. Há duas configurações de janela de lookback na Analysis Workspace: visita e visitante.

**Janela de lookback de visita**

A janela de lookback de visita é qualquer sequência de atividades separadas por 30 minutos de inatividade por padrão. Entretanto, [Sessões sensíveis ao contexto](https://marketing.adobe.com/resources/help/en_US/reference/vrs-mobile-visit-processing.html) também são suportadas por meio do [Tempo de processamento de relatórios](https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html) se você desejar alterar a configuração padrão. Ao usar uma janela de lookback de atribuição de visita dentro de um Conjunto de relatórios virtual usando uma sessão personalizada, a janela de lookback de atribuição usará a definição personalizada da visita como a base do cálculo. No exemplo acima, cada visita seria considerada um lookback de atribuição independente.

**Janela de lookback de visitante**

A janela de lookback de visitante considera a totalidade de ocorrências de um visitante dentro da janela de relatório do seu painel da Workspace, junto ao total de meses que compõem a janela de relatório. Por exemplo, se o intervalo de datas a janela de relatório fosse 15 de setembro a 30 de setembro, o intervalo de datas de lookback do visitante seria 1 de setembro a 30 de setembro. Para obter mais informações sobre a janela de lookback do visitante, consulte [Dados exibidos fora da janela de relatório](https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html).

**Exemplo de janela de lookback de atribuição**

Para ilustrar o efeito das janelas de lookback de atribuição, aplicaremos um modelo Linear (que atribui o mesmo crédito a todos os pontos de contato) ao nosso exemplo acima:

Ao usar a **janela de lookback de atribuição de visita**, cada visita tem sua conversão distribuída de maneira independente:

* Os/$ 10 da primeira visita seriam divididos igualmente entre Pesquisar, Exibir, Social e Email, cada um recebendo/$ 2.50.
* Na segunda visita, a Pesquisa e o Email receberiam metade da conversão/$ 5, portanto, e-mail e pesquisa receberiam cada outro/$ 2.50.
* Por fim, na visita final, o email receberia todo o crédito pela conversão/$ 2.

Na **janela de lookback de visitante**, todas as conversões são consideradas juntas, entretanto, o cálculo é um pouco mais complexo devido ao fato de haver várias conversões.

* A primeira conversão/$ 10 seria dividida igualmente entre Pesquisar, Exibir, Social e Email.
* A segunda conversão/$ 5 seria então dividida entre os canais presentes nessa visita e os canais anteriores da visita anterior: Search = (2/6) */$ 5 =/$ 1.67, Display = (1/6) */$ 5 =/$ 0.83, Social = (1/6) */$ 5 =/$ 0.83, Email = (2/6) */$ 5 =/$ 1.67.
* Finalmente, a última conversão seria dividida em todos os canais do visitante: Search = (2/7) */$ 2 =/$ 0.57, Display = (1/7) */$ 2 =/$ 0.29, Social = (1/7) */$ 2 =/$ 0.29, Email = (3/7) */$ 2 =/$ 0.86.

Veja um resumo dos resultados em uma tabela:

| Canal | Receita (Linear/Visita) | Receita (Linear/Visitante) |
|---|---|---|
| Pesquisar | /$5,00 | /$4,74 |
| Exibição | /$2,50 | /$3,62 |
| Social | /$2,50 | /$3,62 |
| Email | /$7,00 | /$5,02 |
| Total | /$17,00 | /$17,00 |

Essa diferença na janela de lookback de atribuição funciona de maneira semelhante com todos os modelos de atribuição descritos abaixo.

## Modelos de atribuição {#section_4B9E7F83AE0B451A992397E55C3F5871}

A Analysis Workspace dá suporte a dez modelos de atribuição diferentes: Primeiro contato, Último contato, Mesmo contato, Linear, Forma de U, Forma de J, J invertido, Declínio de tempo, Participação e Personalizado. Abaixo estão exibidos detalhe de cada um, acompanhados de modelos:

<table id="table_A3EB34CD52314F0393FF0D12E5F9779D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ícone da interface do usuário </th> 
   <th colname="col2" class="entry"> Modelo de atribuição </th> 
   <th colname="col3" class="entry"> Definição </th> 
   <th colname="col4" class="entry"> Quando usar </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/last_touch.PNG" id="image_7D574182B1564109B0F1C3DD4FD9E8E9" /> </p> </td> 
   <td colname="col2"> <p>Último contato </p> </td> 
   <td colname="col3"> <p>O modelo de Último contato atribui 100% do crédito ao ponto de contato que ocorre imediatamente antes da conversão. Do caso acima, o canal de Email receberia crédito para os $17 em um lookback de visita ou de visitante, porque Email ocorreu antes das três conversões. </p> </td> 
   <td colname="col4"> <p>Este é o modelo de atribuição mais básico e comum e é frequentemente usado para converesões com um ciclo de consideração curto. </p> <p>Último contato é usado por equipes responsáveis por gerenciar marketing de pesquisa ou analisar palavras-chave de pesquisa interna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/first_touch.png" id="image_D8CD48CB39D64A0386CBA38397BB69B0" /> </p> </td> 
   <td colname="col2"> <p>Primeiro contato </p> </td> 
   <td colname="col3"> <p>O modelo de Último contato atribui 100% do crédito ao ponto de contato que ocorre imediatamente na janela de lookback de atribuição. </p> <p>No exemplo acima usando o lookback de visita, $10 + $5 = $15 seriam atribuídos ao canal de Pesquisa, e $2 ao canal de Email. Com um lookback de visitante, os $17 seriam atribuídos ao canal de Pesquisa porque foi o primeiro a ocorrer entre todas as ocorrências na janela de relatório. </p> </td> 
   <td colname="col4"> <p>Este é outro modelo de atribuição comum que é útil para analisar canais de marketing para impulsionar a consciência de marca ou a aquisição de cliente. </p> <p>Primeiro contato é usado frequentemente por equipes de marketing de Exibição ou de Redes sociais, mas também é últil para assistir na eficiência de recomendações locais de produtos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/same_touch.png" id="image_7E093A65BA4048F0B46E1110D9569C84" /> </p> </td> 
   <td colname="col2"> <p>Mesmo contato </p> </td> 
   <td colname="col3"> <p>O modelo de Mesmo contato atribui 100% do crédito à exata ocorrência na qual a conversão foi ocorrida. </p> <p>Em nosso exemplo acima, cada conversão ocorreu em uma ocorrência subsequente do ponto de contato de marketing anterior, portanto os $17 seriam atribuídos ao item de linha “Nenhum” no relatório. </p> </td> 
   <td colname="col4"> <p>Este modelo é útil ao avaliar o conteúdo ou experiência do usuário que foi apresentada imediatamente no momento da conversão. Equipes de produto ou de design geralmente usam esse modelo para estimar a eficácia de uma página na qual a conversão ocorre. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/linear.png" id="image_FB96E57837EE47B5B6AE0066CC6DCF45" /> </p> </td> 
   <td colname="col2"> <p>Linear </p> </td> 
   <td colname="col3"> <p>O modelo Linear é um modelo multi toque que atribui o mesmo crédito a cada ocorrência que levou a uma conversão. </p> <p>Em cenários onde vários pedidos são feitos no mesmo lookback de visita ou de visitante, o crédito é distribuído igualmente entre todos os canais ocorridos antes da conversão. </p> </td> 
   <td colname="col4"> <p>Este modelo é útil para conversões com ciclos de consideração mais longos ou experiências do usuário que requerem participações do cliente mais frequentes ou consistentes. </p> <p>A atribuição linear é frequentemente usada por equipes responsáveis por medir a eficácia de notificações de aplicativos móveis ou com produtos com base em assinatura. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/u_shaped.png" id="image_625BB199056D453E8DA8FA283A990DDD" /> </p> </td> 
   <td colname="col2"> <p>Forma de U </p> </td> 
   <td colname="col3"> <p>O modelo de Forma de U atribui 40% do crédito para a primeira interação, 40% para a última interação e compartilha os 20% restantes com as interações intermediárias. </p> <p>Em lookbacks de atribuição com somente um ponto de contato, 100% do crédito é atribuído ao único ponto de contato; caso haja somente dois pontos de contato, 50% de crédito é atribuído a cada. </p> </td> 
   <td colname="col4"> <p>Este modelo é útil para quem prioriza a primeira ou última interação em uma conversão, mas também deseja identificar as interações assistentes. </p> <p>A atribuição de Forma de U é frequentemente usada por equipes com uma abordagem mais equilibrada, mas que desejam atribuir mais crédito a canais que introduziram ou encerraram uma conversão. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/j_shaped.png" id="image_D062FD7277A947BC9802F8BDFC139427" /> </p> </td> 
   <td colname="col2"> <p>Forma de J </p> </td> 
   <td colname="col3"> <p>O modelo de Forma de J atribui 60% do crédito para a última interação, 20% para a primeira interação e compartilha os 20% restantes com as interações intermediárias. </p> <p>Em lookbacks de atribuição com somente um ponto de contato, 100% do crédito é atribuído ao único ponto de contato; caso haja somente dois pontos de contato, 75% de crédito é atribuído ao último e 25% ao primeiro. </p> </td> 
   <td colname="col4"> <p>Similar ao Forma de U, esse modelo é útil para quem prioriza a primeira ou última interação em uma conversão, mas deseja enfatizar a interação que encerrou a conversão. </p> <p>A atribuição de Forma de J é frequentemente usada por equipes com uma abordagem mais equilibrada, e que desejam atribuir mais crédito a canais que encerraram uma conversão </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/inverse_j.png" id="image_20FFD4C9C9714901B3F54C049D129BC6" /> </p> </td> 
   <td colname="col2"> <p>J inverso </p> </td> 
   <td colname="col3"> <p>O modelo de J inverso atribui 60% do crédito para a primeira interação, 20% para a última interação e compartilha os 20% restantes com as interações intermediárias. </p> <p>Em lookbacks de atribuição com somente um ponto de contato, 100% do crédito é atribuído ao único ponto de contato; caso haja somente dois pontos de contato, 75% de crédito é atribuído ao primeiro e 25% ao último. </p> </td> 
   <td colname="col4"> <p>Similar ao Forma de U, esse modelo é útil para quem prioriza a primeira ou última interação em uma conversão, mas deseja enfatizar a interação que iniciou a conversão. </p> <p>A atribuição de J inverso é frequentemente usada por equipes com uma abordagem mais equilibrada, e que desejam atribuir mais crédito a canais que iniciaram uma conversão. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/custom.png" id="image_D46A787AC72248C7B28C402F5515B099" /> </p> </td> 
   <td colname="col2"> <p>Personalizado </p> </td> 
   <td colname="col3"> <p>O modelo personalizado é um modelo com base em posição que permite especificar os valores que você deseja atribuir à primeira interação (início), à última (encerramento) e às interações intermediárias (reprodução). </p> <p>Os valores especificados são regularizados para 100% mesmo se os números inseridos, quando somados, não resultarem em 100. Em lookbacks de atribuição com somente um ponto de contato, 100% do crédito é atribuído ao único ponto de contato; em casos com somente dois pontos de contato, o parâmetro “player” (reprodução) é ignorado, e a primeira e a última interação são medidas pelos valores de parâmetro de modelo “starter” (início) e “closer” (encerramento), regularizados para 100%. </p> </td> 
   <td colname="col4"> <p>Se sua organização não está confortável com os padrões providenciados pelo Adobe Analytics, um modelo personalizado permite que você especifique os valores que fazem mais sentido para a sua organização. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/time_decay.png" id="image_7976721B60454944BF516FCF8484D3A2" /> </p> </td> 
   <td colname="col2"> <p>Declínio de tempo </p> </td> 
   <td colname="col3"> <p>O modelo de Declínio de tempo segue um declínio exponencial com um parâmetro personalizado de vida útil parcial (o padrão é sete dias). </p> <p>O valor de cada canal depende da quantidade de tempo que passou entre o ponto de contato e a conversão, e é determinado pela fórmula 2^(-t/vidaútilparcial), onde t é o tempo entre um ponto de contato e uma conversão. Para lookbacks com um único ponto de contato, 100% do crédito é atribuído a ele. Para lookbacks com dois pontos de contato, o crédito é proporcional ao tempo da conversão. </p> </td> 
   <td colname="col4"> <p>Este modelo é útil para equipes que executam promoções ao longo de uma quantidade predeterminada de dias que desejam enfatizar canais ocorridos recentemente. </p> <p>A atribuição de Declínio de tempo é frequentemente usada por equipes responsáveis por executar publicidade em vídeos ou equipes responsáveis por agendar o marketing de acordo com um determinado evento com uma data predeterminada (como uma conferência ou um evento esportivo). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/participation.png" id="image_19DD3CA5C0F24F05835D8522C6708DE4" /> </p> </td> 
   <td colname="col2"> <p>Participação </p> </td> 
   <td colname="col3"> <p>A Participação atribui 100% do crédito a todos os pontos de contato ou canais exclusivos em uma janela de lookback de atribuição. Com a Participação, o número total de conversões será elevado em seu relatório, em comparação a outros modelos de atribuição. Observe que a participação deduplica canais que ocorrem várias vezes em uma única janela de lookback de atribuição antes de atribuir crédito. </p> <p>No nosso exemplo acima, e considerando uma janela de lookback de visitante, Pesquisa, Exibição, Social e Email receberiam $17 cada. Usando o mesmo exemplo com uma janela de lookback de visita, Pesquisa receberia $15, Exibição receberia $10, Social receberia $10 e Email receberia $17. </p> </td> 
   <td colname="col4"> <p>Este modelo é excelente para análise e descoberta para compreender com que frequência seus usuários finais ou clientes são expostos a um canal em particular ou interação. </p> <p>Equipes de mídia usam esse modelo para calcular a velocidade do conteúdo, e organizações de vendas usam esse modelo para saber mais sobre quais partes de seus aplicativos ou sites estão no caminho crítico de conversão. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Canais de marketing e regras de processamento de canais de marketing {#section_FCBF08A9D7C94B67B7AD76E8633E7916}

Os canais de Primeiro contato e de Úiltimo contato, bem como o Detalhe do canal de primeiro contato e o Detalhe do canal de último contato, podem ser usados com os novos modelos de atribuição. Para evitar confusão entre sua equipe no futuro, recomendamos usar duas novas dimensões em vez disso: **Canais de marketing** e **Detalhe de canais de marketing**. A maneira como agem é precisamente similar mas não apresentam a distinção confusa “Primeiro contato” e “Último contato” no nome. Se nenhum modelo de atribuição for aplicado, Canais de marketing e Detalhe de canais de marketing terão os mesmos resultatos que Canal de último contato e Detalhe de canal de último contato, respectivamente.

Ao aplicar modelos de atribuição ao Canal de primeiro contato ou ao Canal de último contato, quaisquer configurações de atribuição serão sobrescritas pelo modelo de atribuição selecionado. Portanto, apesar do nome da dimensão ser “Canal de primeiro contato”, se você selecionar o modelo Linear (por exemplo), os resultados refletirão a atribuição linear, e não o “Primeiro contato”.

Além disso, como variáveis de Canais de marketing dependem da visita tradicional (conforme definido pelas Regras de processamento de canais de marketing, aplicadas durante o processo de coleta de dados), elas são inelegíveis para uso com Sessões sensíveis ao contexto.

## Detalhamentos de atribuição por classificação {#section_F9DE21758C4643879BE05EEAE9A34E5A}

Modelos de atribuição podem ser aplicados a qualquer valor e sua classificação. Em casos onde um valor classificado é detalhado por sua respectiva chave, o Analytics incluirá somente as chaves associadas com esse determinado valor classificado. Por exemplo, em um modelo de atribuição linear aplicado a uma determinada eVar com os valores “maçã”, “banana” e “cenoura” classificados aos valores “Frutas” e “Vegetais”, onde o valor “Vegetais” é detalhado pela eVar de base, somente “cenoura” apareceria no detalhamento. De maneira semelhante, detalhar “Frutas” pela eVar de base mostraria somente “maçã” e “banana” nos resultados do detalhamento, mesmo se o crédito de atribuição fosse distribuído entre os valores de todas as três eVars de base.

Esse comportamento também aplica-se a relatórios onde as dimensões de Canais de marketing são detalhadas pelas dimensões de Detalhe de canais de marketing.

## Atribuição para detalhamentos {#section_B2E87C768B6B4DBFA8EB7DB5E2DF881E}

A Analysis Workspace permite detalhar qualquer valor por qualquer dimensão e especificar as mesmas configurações ou configurações diferentes de atribuição no detalhamento. Por exemplo, uma dimensão de Canal pode ter uma atribuição linear aplicada a ela, mas detalhar Canal por Campanha permite especificar um modelo de atribuição diferente no nível da campanha.

Isso é útil para equipes que possuem um modelo de atribuição no nível de Canal (para dividir igualmente entre canais), mas têm equipes individuais que desejam usar um modelo de atribuição separado em suas campanhas individuais e precisam que os totais das campanhas correspondam ao que foi alocado no nível de Canal.

## “Nenhuma” em atribuição {#section_BC71DA030E45487AA3C3F6ED247A3C4A}

O item de linha “nenhuma” representa todas as conversões que ocorreram onde não havia um valor de dimensão presente. Tradicionalmente, o item de linha “nenhuma” existe somente em relatórios de eVar ou outras dimensões com persistência. Quando modelos de atribuição são aplicados, um item de linha “nenhuma” pode aparecer onde não existia antes. Isso ocorre ao aplicar modelos de atribuição a propriedades que introduzem um item de linha “nenhuma” que não estava presente anteriormente.

## Atribuição para variáveis com valores múltiplos

Algumas dimensões no Analytics podem conter vários valores em uma única ocorrência como listVars, a variável do produto, propriedades de lista ou eVars de merchandising. A Analysis Workspace permite aplicar o Attribution IQ a qualquer um desses tipos de variáveis no nível de ocorrência. Uso de uma atribuição de Forma de U (40/20/40) como um exemplo de visita única:

| Número da ocorrência | Variável com valores múltiplos | Evento de conversão | Percentual de crédito para a ocorrência (forma de U) |
|--- |--- |---|---|
| 1 | A,B,C | - | 40% |
| 2 | D | - | 20% |
| 3 | E,F | 1 | 40% |

Neste caso, A, B e C foram definidas ao mesmo tempo na ocorrência 1, D foi definida individualmente na ocorrência 2 e E e F foram definidas na ocorrência 3.

O Attribution IQ distribui todo o crédito percentual da ocorrência a quaisquer valores presentes na ocorrência. Em nosso exemplo anterior, A, B e C receberão 40% ou .4 conversões, D receberá 20% ou .2 conversões e E e F cada receberá 40% das conversões ou .4. Um relatório usando a atribuição de Forma de U nas ocorrências acima produziria o seguinte relatório:

| Variável com valores múltiplos | Conversões (em formato U/Visita) |
|--- |---|
| A | .4 |
| B | .4 |
| C | .4 |
| D | .2 |
| E | .4 |
| F | .4 |
| Total | 1 |

>[!NOTE]
>Devido à alocação em nível de ocorrência dos modelos de atribuição, a soma de cada item de linha de seu relatório pode não ser igual ao total, devido a cada valor que recebe o crédito percentual total que pertence à ocorrência em que foi contido.