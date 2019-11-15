---
description: 'null'
title: Visão geral do painel Atribuição
uuid: bb345642-4f45-4fb8-82d0-803248dd52ea
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Visão geral do painel Atribuição

>[!IMPORTANT] O painel Atribuição está disponível para todos os clientes nos SKUs do Adobe Analytics Ultimate, Prime, Select e Foundation.

O painel de atribuição é um recurso de QI [de](../../attribution-iq.md) atribuição que permite adicionar muitos novos tipos de modelos de atribuição a tabelas de forma livre, visualizações e métricas calculadas. Todos os modelos de atribuição têm dois componentes:

* **** Modelo de atribuição: O modelo descreve a distribuição de conversões para as ocorrências em um grupo. Por exemplo, primeiro ou último toque.
* **** Janela de pesquisa de atribuição: A janela de pesquisa descreve quais agrupamentos de ocorrências são considerados para cada modelo. Por exemplo, visita ou visitante.

## Modelos de atribuição

| Ícone da interface | Modelo de atribuição | Definição | Quando usar |
| --- | --- | --- | --- |
| ![Último contato](assets/last_touch1.png) | Último contato | Dá 100% de crédito ao ponto de toque que ocorreu mais recentemente antes da conversão. | O modelo de atribuição mais básico e comum. É frequentemente utilizado para conversões com um ciclo de curto prazo. Último contato é usado por equipes responsáveis por gerenciar marketing de pesquisa ou analisar palavras-chave de pesquisa interna. |
| ![Primeiro contato](assets/first_touch.png) | Primeiro contato | Dá 100% de crédito ao ponto de toque visto pela primeira vez na janela de pesquisa de atribuição. | Outro modelo de atribuição comum útil para analisar canais de marketing destinados a promover o reconhecimento da marca ou a aquisição do cliente. Ele é usado com frequência pelas equipes de exibição ou marketing social, mas também é excelente para avaliar a eficácia da recomendação de produtos no site. |
| ![Mesmo contato](assets/same_touch.png) | Mesmo contato | Dá 100% de crédito à ocorrência em que a conversão ocorreu. Se um ponto de toque não ocorrer na mesma ocorrência que uma conversão, ele será agrupado em "Nenhum". | Um modelo útil ao avaliar o conteúdo ou a experiência do usuário que foi apresentado imediatamente no momento da conversão. Geralmente, as equipes de produto ou design usam esse modelo para avaliar a eficácia de uma página onde a conversão acontece. |
| ![Linear](assets/linear.png) | Linear | Dá crédito igual a cada ponto de toque visto, o que resulta em uma conversão. | Útil para conversões com ciclos de consideração mais longos ou experiências de usuário que precisam de envolvimento mais frequente do cliente. Geralmente é usado por equipes que avaliam a eficácia da notificação do aplicativo móvel ou com produtos baseados em assinatura. |
| ![Forma de U](assets/u_shaped.png) | Forma de U | Dá crédito a 40% à primeira interação, 40% à última interação, e divide os 20% restantes em qualquer ponto de toque no meio. Para conversões com um único ponto de toque, é dado crédito de 100%. Para conversões com dois pontos de toque, 50% de crédito é dado a ambos. | Um grande modelo para aqueles que valorizam as interações que introduziram ou fecharam uma conversão, mas ainda querem reconhecer as interações de assistência. A atribuição U-Shaped é normalmente usada por equipes que adotam uma abordagem mais equilibrada, mas que desejam conceder mais crédito aos canais que encontraram ou fecharam uma conversão. |
| ![Forma de J](assets/j_shaped.png) | Forma de J | Dá crédito de 60% à última interação, 20% à primeira interação, e divide os 20% restantes em qualquer ponto de contato entre eles. Para conversões com um único ponto de toque, é dado crédito de 100%. Para conversões com dois pontos de contato, 75% de crédito é dado à última interação, e 25% de crédito é dado à primeira. | Esse modelo é excelente para aqueles que priorizam localizadores e fechadores, mas querem se concentrar em interações de fechamento. A atribuição J-Shaped é frequentemente usada por equipes que adotam uma abordagem mais equilibrada e querem dar mais crédito aos canais que fecharam uma conversão. |
| ![Forma J Inversa](assets/inverse_j.png) | J inverso | Dá 60% de crédito ao primeiro ponto de toque, 20% de crédito ao último ponto de toque e divide os 20% restantes em qualquer ponto de toque no meio. Para conversões com um único ponto de toque, é dado crédito de 100%. Para conversões com dois pontos de contato, 75% de crédito é dado à primeira interação, e 25% de crédito é dado à última. | Esse modelo é ideal para aqueles que priorizam localizadores e fechadores, mas querem se concentrar em encontrar interações. A atribuição Inverse J é usada por equipes que adotam uma abordagem mais equilibrada e querem dar mais crédito aos canais que iniciaram uma conversão. |
| ![Personalizado](assets/custom.png) | Personalizado | Permite que você especifique os pesos que deseja atribuir aos pontos de primeiro toque, aos pontos de último toque e a todos os pontos de toque no meio. Os valores especificados são normalizados para 100% mesmo se os números personalizados inseridos não adicionarem a 100. Para conversões com um único ponto de toque, é dado crédito de 100%. Para interações com dois pontos de toque, o parâmetro intermediário é ignorado. Os pontos de primeiro e último toque são normalizados para 100% e o crédito é atribuído de acordo. | Esse modelo é perfeito para quem quer controle total sobre seu modelo de atribuição e tem necessidades específicas que outros modelos de atribuição não atendem. |
| ![Declínio de tempo](assets/time_decay.png) | Decadência de tempo | Segue e decai exponencial com um parâmetro personalizado de meia-vida, onde o padrão é 7 dias. O peso de cada canal depende da quantidade de tempo decorrido entre a iniciação do ponto de toque e a conversão final. A fórmula usada para determinar o crédito é `2`<sup>`(-t/halflife)`</sup>, onde `t` é o tempo entre um ponto de contato e uma conversão. Todos os pontos de toque são normalizados para 100%. | Excelente para equipes que fazem regularmente publicidade em vídeo ou marketing contra eventos com data predeterminada. Quanto mais tempo uma conversão ocorrer após um evento de marketing, menos crédito será dado. |
| ![Participação](assets/participation.png) | Participação | Dá 100% de crédito a todos os pontos de toque exclusivos. O número total de conversões é inflado em comparação com outros modelos de atribuição. A participação remove a duplicação de canais que são vistos várias vezes. | Excelente para entender quem frequentemente os clientes são expostos a uma determinada interação. As organizações de mídia frequentemente usam esse modelo para calcular a velocidade do conteúdo. As organizações de varejo geralmente usam esse modelo para entender quais partes do site são essenciais para a conversão. |

## Janelas de pesquisa

Uma janela de pesquisa é a quantidade de tempo que uma conversão deve retornar para incluir pontos de contato. Os modelos de atribuição que dão mais crédito às primeiras interações veem diferenças maiores ao visualizar diferentes janelas de pesquisa.

* **** Janela Pesquisar: Procura até o início de uma visita em que uma conversão aconteceu. As janelas de pesquisa de visitas são estreitas, pois não parecem além da visita. As janelas de pesquisa de visita respeitam a definição de visita modificada em conjuntos de relatórios virtuais.
* **** Janela de pesquisa do visitante: Verifica todas as visitas até o primeiro dia do mês do intervalo de datas atual. As janelas de pesquisa do visitante são amplas, pois podem abranger muitas visitas. Por exemplo, se o intervalo de datas do relatório for de 15 de setembro a 30 de setembro, o intervalo de datas de retrospectiva do visitante incluirá 1 de setembro a 30 de setembro.

## Exemplo

Considere o exemplo a seguir:

1. Em 15 de setembro, um visitante chega ao seu site por meio de um anúncio de pesquisa pago e depois sai.
2. Em 18 de setembro, o visitante chega ao seu site novamente através de um link de mídia social que recebeu de um amigo. Eles adicionam vários itens ao carrinho, mas não compram nada.
3. Em 24 de setembro, sua equipe de marketing envia um email com um cupom para alguns dos itens em seu carrinho. Eles aplicam o cupom, mas visitam vários outros sites para ver se existem outros cupons disponíveis. Eles encontram outro por meio de um anúncio de exibição e, em seguida, fazem uma compra de US$ 50.

Dependendo da janela de pesquisa e do modelo de atribuição, os canais recebem crédito diferente. Estes são alguns exemplos notáveis:

* Usando o **primeiro toque** e uma janela **de pesquisa de** visita, a atribuição procura somente a terceira visita. Entre email e exibição, o email foi o primeiro, então o email recebe 100% de crédito pela compra de US$ 50.
* Usando o **primeiro toque** e uma janela **de pesquisa de** visitante, a atribuição analisa todas as três visitas. A pesquisa paga foi a primeira, então ela recebe 100% de crédito pela compra de $50.
* Usando uma janela **de pesquisa** linear **e de** visita, o crédito é dividido entre email e exibição. Ambos os canais recebem um crédito de 25 dólares.
* Usando uma janela **de pesquisa** linear **e de** visitante, o crédito é dividido entre pesquisa paga, social, email e exibição. Cada canal recebe um crédito de R$ 12,50 por esta compra.
* Usando a janela **de pesquisa em** J e **** visitante, o crédito é dividido entre pesquisa paga, social, email e exibição.
   * 60% de crédito é dado para exibição, por $30.
   * O crédito de 20% é dado à pesquisa paga, por $10.
   * Os 20% restantes são divididos entre social e email, dando 5 dólares a cada um.
* Usando a **Intervalo de tempo** e uma janela **de pesquisa de** visitante, o crédito é dividido entre pesquisa paga, social, email e exibição. Usando a semivida padrão de 7 dias:
   * Intervalo de 0 dias entre o ponto de toque de exibição e a conversão. `2`<sup>`(-0/7)`</sup> `= 1`
   * Intervalo de 0 dias entre o ponto de contato do email e a conversão. `2`<sup>`(-0/7)`</sup> `= 1`
   * Intervalo de 6 dias entre o ponto de contato social e a conversão. `2`<sup>`(-6/7)`</sup> `= 0.552`
   * Intervalo de 9 dias entre o ponto de contato de pesquisa paga e a conversão. `2`<sup>`(-9/7)`</sup> `= 0.41`
   * A normalização desses valores resulta no seguinte:
      * Exibir: 33,8%, ganhando $16,88
      * Email: 33,8% obtendo US$ 16,88
      * Social: 18,6%, ganhando US$ 9,32
      * Pesquisa paga: 13,8%, ganhando $6,92

> [!TIP] Outros eventos de conversão, como pedidos ou eventos personalizados, também são divididos se o crédito pertencer a mais de um canal. Por exemplo, se dois canais contribuem para um evento personalizado usando um modelo de atribuição Linear, ambos os canais obtêm 0,5 do evento personalizado. Essas frações de evento são somadas em todas as visitas, em seguida, arredondadas para o número inteiro mais próximo para o relatório.

## Usar atribuição com canais de marketing

Quando os canais de marketing foram introduzidos pela primeira vez, eles vieram com apenas as dimensões de primeiro e último toque. Com esses modelos de atribuição adicionais, dimensões explícitas de primeiro/último toque não são mais necessárias. A Adobe fornece dimensões genéricas **de Canal** de marketing para que possam ser usadas com o modelo de atribuição escolhido. Essas dimensões genéricas dos Canais de marketing se comportam de forma idêntica às dimensões do Canal de último toque, mas são rotuladas de forma diferente para evitar confusão ao usar canais de marketing com um modelo de atribuição diferente.

Como as dimensões do canal de marketing dependem de uma definição de visita tradicional (conforme definido por suas regras de processamento), a definição de visita não pode ser alterada usando conjuntos de relatórios virtuais.

## Uso de atribuição com variáveis de vários valores

Algumas dimensões no Analytics podem conter vários valores em uma única ocorrência. Exemplos comuns incluem list vars e a variável products.

Quando a atribuição é aplicada a ocorrências de vários valores, todos os valores na mesma ocorrência recebem o mesmo crédito. Como muitos valores podem receber esse crédito, o total do relatório pode ser diferente se você somar cada item de linha individual. O total do relatório é desduplicado, enquanto cada valor de dimensão individual recebe o crédito adequado.

## Usar atribuição com segmentação

A atribuição sempre é executada antes da segmentação e a segmentação é executada antes da aplicação dos filtros do relatório. Esse conceito também se aplica a conjuntos de relatórios virtuais que usam segmentos.

Por exemplo, se você criar um VRS com um segmento "Exibir ocorrências" aplicado, poderá ver outros canais em uma tabela usando alguns modelos de atribuição.

![Conjunto de relatórios virtual somente exibição](assets/vrs-aiq-example.png)
