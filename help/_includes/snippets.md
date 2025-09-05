---
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '2962'
ht-degree: 88%

---
# Trechos

## Report Builder legado {#legacy-arb}

>[!IMPORTANT]
>
>Um novo e simplificado [Report Builder](/help/analyze/report-builder/rb-overview.md) foi lançado em 16 de outubro de 2024. Ele é compatível com Mac, Windows e navegadores da Web.
>&#x200B;>Esta versão herdada do complemento do Report Builder ainda funciona. Você pode [converter suas pastas de trabalho herdadas](/help/analyze/report-builder/convert-workbooks.md) para a nova Report Builder.

## Anúncio do fim da vida útil do Reports & Analytics {#ra-eol}

>[!IMPORTANT]
>
>A partir de **17 de janeiro de 2024**, a Adobe descontinuou o Reports &amp; Analytics, juntamente com os relatórios e recursos que o acompanham. Naquele momento, o Reports &amp; Analytics e todos os seus relatórios e agendamentos pararam de funcionar. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o Reports &amp; Analytics não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do Reports &amp; Analytics está disponível no Analysis Workspace. Para obter informações, consulte [Usar modelos](/help/analyze/analysis-workspace/templates/use-templates.md).
> 
>Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do Reports &amp; Analytics foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. Este aviso explica o processo do fim da vida útil.
>
>Leia mais sobre o [Anúncio do fim da vida útil](https://www.adobe.com/go/analytics_rnaeol_pt) do Reports &amp; Analytics.

## Opções de classificação de componentes {#components-sort-options}

| Opção | Função |
|---------|----------|
| [!UICONTROL **Recomendado**] | Classifica componentes com aqueles recomendados no topo da lista. Os componentes usados com mais frequência e mais recentemente por você ou outras pessoas em sua organização são mostrados em uma posição superior na lista. |
| [!UICONTROL **Ordem alfabética**] | Classifica os componentes em ordem alfabética. |
| [!UICONTROL **Categórico**] | Classifica componentes de acordo com o tipo de componente (dimensão, métrica, segmento, intervalo de datas). |

{style="table-layout:auto"}

## Fase de teste limitado da versão {#release-limited-testing}

>[!AVAILABILITY]
>
>A funcionalidade descrita neste artigo está na fase de teste limitado da versão e pode não estar disponível ainda em seu ambiente. Essa observação será removida quando a funcionalidade estiver em disponibilidade geral. Para obter informações sobre o processo de lançamento do Analytics, consulte [Versões de recursos do Adobe Analytics](/help/release-notes/releases.md).

## Seção Fase de teste limitado da versão {#release-limited-testing-section}

>[!AVAILABILITY]
>
>A funcionalidade descrita nesta seção está na fase de teste limitado da versão e pode não estar disponível ainda em seu ambiente. Essa observação será removida quando a funcionalidade estiver em disponibilidade geral. Para obter informações sobre o processo de lançamento do Analytics, consulte [Versões de recursos do Adobe Analytics](/help/release-notes/releases.md).


## Aviso de isenção de responsabilidade do plug-in {#plug-in}

>[!IMPORTANT]
>
>Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com a Equipe de conta da Adobe de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.


## Disponível somente para clientes existentes {#available-existing-customers}

>[!AVAILABILITY]
>
>A funcionalidade descrita nesta seção só está disponível para clientes existentes que já têm uma licença para a funcionalidade. A funcionalidade não é mais oferecida como um complemento para clientes existentes ou novos.
>



## Modelos de atribuição {#attribution-models-details}

Um modelo de atribuição determina quais itens de dimensão recebem crédito por uma métrica quando há vários valores na sua janela de retrospectiva. Os modelos de atribuição só se aplicam quando a janela de retrospectiva contém vários itens de dimensão. Se apenas um item de dimensão for definido, esse item de dimensão receberá 100% de crédito, independentemente do modelo de atribuição usado.

| Ícone | Modelo de atribuição | Definição |
| :---: | :--- | --- |
| ![Último contato](/help/assets/icons/AttributeLastTouch.svg) | Último contato | Dá 100% de crédito ao ponto de contato que ocorreu mais recentemente antes da conversão. Este modelo de atribuição normalmente é o valor padrão para qualquer métrica na qual um modelo de atribuição não tenha sido especificado de outra forma. As organizações normalmente usam esse modelo quando o tempo de conversão é relativamente curto, como na análise de palavras-chave de pesquisa interna. |
| ![Primeiro contato](/help/assets/icons/AttributeFirstTouch.svg) | Primeiro contato | Dá 100% de crédito ao primeiro ponto de contato visto na janela de retrospectiva de atribuição. As organizações normalmente usam esse modelo para entender a percepção da marca ou a conquista de clientes. |
| ![Linear](/help/assets/icons/AttributeLinear.svg) | Linear | Distribui igualmente o crédito entre todos os pontos de contato que resultam em uma conversão. É útil quando os ciclos de conversão são mais longos ou exigem um engajamento mais frequente do cliente. As organizações normalmente usam esse modelo de atribuição para medir a eficácia de notificações de aplicativos móveis ou com produtos baseados em assinatura. |
| ![Participação](/help/assets/icons/AttributeParticipation.svg) | Participação | Dá 100% de crédito a todos os pontos de contato exclusivos. Como cada ponto de contato recebe 100% de crédito, os dados da métrica geralmente somam mais de 100%. Se um item de dimensão aparecer várias vezes separadas antes de uma conversão, os valores serão desduplicados para 100%. Esse modelo de atribuição é ideal em situações em que você deseja entender a quais pontos de contato os clientes estão mais expostos. As organizações de mídia normalmente usam esse modelo para calcular a velocidade do conteúdo. As organizações de varejo normalmente usam esse modelo para entender quais partes do site são essenciais para a conversão. |
| ![Mesmo contato](/help/assets/icons/AttributeSameTouch.svg) | Mesmo contato | Dá 100% de crédito ao mesmo evento no qual ocorreu a conversão. Se um ponto de contato não ocorrer no mesmo evento que uma conversão, ele será agrupado em “Nenhum”. Este modelo de atribuição às vezes é equiparado à ausência de um modelo de atribuição. É bastante útil em cenários em que você não deseja que valores de outros eventos afetem como uma métrica distribui crédito aos itens de dimensão. As equipes de produto ou design podem usar esse modelo para avaliar a eficácia de uma página na qual ocorre a conversão. |
| ![Em forma de U](/help/assets/icons/AttributeUShaped.svg) | Forma de U | Dá crédito de 40% à primeira interação, de 40% à última interação, e divide os 20% restantes para os pontos de contato entre as duas. Para conversões com um só ponto de contato, o crédito é de 100%. Para conversões com dois pontos de contato, o crédito é de 50% para ambos. Esse modelo de atribuição é melhor utilizado em cenários em que você valoriza mais a primeira e a última interação, mas não deseja descartar completamente as interações adicionais entre elas. |
| ![Curva J](/help/assets/icons/AttributeJCurve.svg) | Curva J | Dá crédito de 60% à última interação, de 20% à primeira interação, e divide os 20% restantes para os pontos de contato entre as duas. Para conversões com um só ponto de contato, o crédito é de 100%. Para conversões com dois pontos de contato, o crédito é de 75% para a última interação e de 25% para a primeira. Semelhante à “Forma de U”, esse modelo de atribuição favorece a primeira e a última interação, mas com foco maior na última interação. |
| ![J invertido](/help/assets/icons/AttributeInverseJ.svg) | J invertido | Dá 60% de crédito ao primeiro ponto de contato, 20% de crédito ao último ponto de contato e divide os 20% restantes para os pontos de contato entre os dois. Para conversões com um só ponto de contato, o crédito é de 100%. Para conversões com dois pontos de contato, o crédito é de 75% para a primeira interação e de 25% para a última. Semelhante à “Forma de J”, esse modelo de atribuição favorece a primeira e a última interação, mas com foco maior na primeira interação. |
| ![Declínio de tempo](/help/assets/icons/AttributeTimeDecay.svg) | Declínio de tempo | Segue um declínio exponencial com um parâmetro personalizado de meia-vida e padrão de 7 dias. O peso de cada canal depende da quantidade de tempo decorrido entre a iniciação do ponto de contato e a conversão final. A fórmula usada para determinar o crédito é `2^(-t/halflife)`, em que `t` é o tempo entre um ponto de contato e uma conversão. Todos os pontos de contato são normalizados para 100%. Ideal para cenários em que você deseja medir a atribuição em relação a um evento específico e significativo. Quanto mais tempo uma conversão demorar para ocorrer após esse evento, menos crédito será dado. |
| ![Personalizado](/help/assets/icons/AttributeCustom.svg) | Personalizado | Permite especificar o peso que você deseja dar ao primeiro ponto de contato, ao último ponto de contato e a pontos de contato intermediários. Os valores especificados são regularizados para 100% mesmo se os números inseridos, quando somados, não resultarem em 100. Para conversões com um só ponto de contato, o crédito é de 100%. Para interações com dois pontos de contato, o parâmetro intermediário é ignorado. O primeiro e o último ponto de contato são normalizados para 100% e o crédito é atribuído em conformidade. Este modelo é ideal para analistas que desejam controle total sobre seu modelo de atribuição e têm necessidades específicas que outros modelos de atribuição não atendem. |
| ![Algorítmico](/help/assets/icons/AttributeAlgorithmic.svg) | Algorítmico | Usa técnicas estatísticas para determinar dinamicamente a alocação ideal de crédito para a métrica selecionada. O algoritmo usado para atribuição é baseado no Harsanyi Dividend da teoria dos jogos cooperativos. O dividendo de Harsanyi é uma generalização da solução de valor de Shapley (batizada de Lloyd Shapley, economista vencedor do Nobel) para distribuir crédito entre os jogadores em um jogo com contribuições desiguais para o resultado.<br>Em alto nível, a atribuição é calculada como uma aliança de jogadores aos quais um excedente deve ser distribuído equitativamente. A distribuição excedente de cada aliança é determinada de acordo com o excedente anteriormente criado por cada subaliança (ou itens de dimensão participantes anteriores) de forma recursiva. Para mais detalhes, veja os documentos originais de John Harsanyi e Lloyd Shapley:<br>Shapley, Lloyd S. (1953). Um valor para jogos em pessoa. *Contribuições para a Teoria dos Jogos, 2(28)*, 307-317.<br>Harsanyi, John C. (1963).  Um modelo de negociação simplificado para o jogo cooperativo entre pessoas. *International Economic Review 4(2)*, 194-220. |

{style="table-layout:auto"}

## Container de atribuição {#attribution-container}

Um container de atribuição define o escopo desejado para a atribuição. As opções disponíveis são:

* **Visita**: verifica as conversões do escopo do contêiner de visitas.
* **Visitante**: verifica as conversões do escopo do contêiner de visitantes.

## Janela de retrospectiva de atribuição {#attribution-lookback-window}

As janelas de retrospectiva representam quanto tempo uma conversão deve retroceder para incluir pontos de contato. Se um item de dimensão for definido fora da janela de retrospectiva, o valor não será incluído em nenhum cálculo de atribuição.

* **14 dias**: retroage até 14 dias a partir do momento em que a conversão ocorreu.
* **30 dias**: retroage até 30 dias a partir do momento em que a conversão ocorreu.
* **60 dias**: retroage até 60 dias a partir do momento em que a conversão ocorreu.
* **90 dias**: retroage até 90 dias a partir do momento em que a conversão ocorreu.
* **Tempo personalizado:** permite definir uma janela de retrospectiva personalizada a partir de quando ocorreu uma conversão. Você pode especificar o número de minutos, horas, dias, semanas, meses ou trimestres. Por exemplo, se uma conversão ocorreu em 20 de fevereiro, uma janela de retrospectiva de cinco dias avaliaria todos os pontos de contato da dimensão de 15 a 20 de fevereiro no modelo de atribuição.

## Exemplo de atribuição {#attribution-example}

Considere o exemplo a seguir:

1. Em 15 de setembro, um visitante chega ao seu site através de um anúncio de pesquisa pago e depois sai.
1. Em 18 de setembro, o visitante chega ao seu site novamente através de um link de mídia social que recebeu de um amigo. Eles adicionam vários itens ao carrinho, mas não compram nada.
1. Em 24 de setembro, sua equipe de marketing envia um email com um cupom para alguns dos itens em seu carrinho. Eles aplicam o cupom, mas visitam vários outros sites para ver se existem outros cupons disponíveis. Eles encontram outro cupom por meio de um anúncio de exibição e, em seguida, fazem uma compra de US$ 50.

Dependendo do modelo de atribuição, o container e os canais recebem créditos diferentes. Veja exemplos na tabela abaixo:

| Modelo | Container | Janela de retrospectiva | Explicação |
|---|---|---|---|
| Primeiro contato | Visita | 30 dias | A atribuição analisa somente a terceira visita. Entre email e exibição, o email foi o primeiro, portanto, o email recebe 100% de crédito pela compra de US$ 50. |
| Primeiro contato | Visitante | 30 dias | A atribuição analisa as três visitas. A pesquisa paga foi a primeira, portanto recebe 100% de crédito pela compra de US$ 50. |
| Linear | Visita | 30 dias | O crédito é dividido entre email e exibição. Ambos os canais recebem um crédito de US$ 25. |
| Linear | Visitante | 30 dias | O crédito é dividido entre pesquisa paga, redes sociais, email e exibição. Cada canal recebe um crédito de US$ 12,50 pela compra. |
| Forma de J | Visitante | 30 dias | O crédito é dividido entre pesquisa paga, redes sociais, email e exibição.<ul><li>O crédito será de 60% para a exibição (US$ 30).</li><li>De 20% para a pesquisa paga (US$ 10).</li><li>Os 20% restantes são divididos entre redes sociais e email (US$ 5 para cada).</li></ul> |
| Declínio de tempo | Visitante | 30 dias | <ul><li>Intervalo de 0 dias entre o ponto de contato de exibição e a conversão. `2^(-0/7) = 1`</li><li>Intervalo de 0 dias entre o ponto de contato de email e a conversão. `2^(-0/7) = 1`</li><li>Intervalo de seis dias entre o ponto de contato de rede social e a conversão. `2^(-6/7) = 0.552`</li><li>Intervalo de nove dias entre o ponto de contato de pesquisa paga e a conversão. `2^(-9/7) = 0.41`</li>A normalização desses valores resulta no seguinte:<ul><li>Exibição: 33,8%, crédito de US$ 16,88</li><li>Email: 33,8%, crédito de US$ 16,88</li><li>Redes sociais: 18,6%, crédito de US$ 9,32</li><li>Pesquisa paga: 13,8%, crédito de US$ 6,92</li></ul></li></ul> |

Os eventos de conversão que normalmente têm números inteiros são divididos se o crédito pertencer a mais de um canal. Por exemplo, se dois canais contribuem para um pedido usando um modelo de atribuição linear, ambos os canais recebem 0,5 desse pedido. Essas métricas parciais são somadas para todas as pessoas e depois arredondadas para o número inteiro mais próximo para fins de geração de relatórios.

## Comparações de visualização de jornadas {#journey-visualization-comparisons}

Várias visualizações no Customer Journey Analytics são projetadas para analisar as jornadas que você fornece aos seus clientes.

Use as informações a seguir para escolher a visualização que melhor atende às suas necessidades.

| Função | Tela da jornada | Fallout | Fluxo |
|---------|----------|---------|---------|
| **Sequência predefinida de páginas** | Sim</br>Combina análise predefinida e exploratória. O caminho eventual é usado ao usar nós predefinidos no caminho (os visitantes são contados desde que eventualmente se movam de um nó predefinido para o outro). Os próximos nós imediatos (não eventuais) também podem ser mostrados. | Sim</br>O caminho pode ser um caminho eventual ou pode ser restrito ao próximo ponto de contato | Não |
| **Sequência exploratória de páginas (análise ad hoc)** | Sim</br>Combina análise predefinida e exploratória. O caminho eventual é usado ao usar nós predefinidos no caminho (os visitantes são contados desde que eventualmente se movam de um nó predefinido para o outro). Os próximos nós imediatos (não eventuais) também podem ser mostrados. | Limitado</br>Permite clicar com o botão direito do mouse e exibir o fallout imediato em uma tabela de forma livre. | Sim</br>Somente análise exploratória. Sempre em uma instância de dimensão entre nós. Isso significa que cada nó mostra o próximo ponto de contato imediato (não eventual) ao longo do caminho. |
| **Mostra onde as pessoas saíram (desistiram) e continuaram (permaneceram)** | Sim</br>Mostra para jornadas predefinidas e exploratórias | Sim</br>Mostra jornadas predefinidas | Sim</br>Mostra jornadas exploratórias |
| **Jornadas lineares** | Sim | Sim | Não |
| **Jornadas não lineares com vários pontos de entrada e caminhos** | Sim | Não | Sim |
| **Métrica principal** | Qualquer métrica, incluindo métricas calculadas | Somente sessões ou pessoas | Somente ocorrências (visualizações de caminho) |
| **Métrica secundária** | Sim<p>Qualquer métrica, incluindo métricas calculadas</p> | Não | Não |
| **Suporte a componentes em nós ou pontos de contato** | Métricas, itens de dimensão, filtros e intervalos de datas. | Métricas, itens de dimensão, filtros e intervalos de datas. | Somente itens de dimensão (exceto para os pontos de contato inicial e final) |
| **Comparar filtros** | Não | Sim<p>Fazer comparações lado a lado de dois filtros diferentes no mesmo relatório.</p> | Não |
| **Interação de componentes de arrastar e soltar** | Sim | Sim | Não |
| **Jornadas do Adobe Journey Optimizer** | Sim</br>Abrir jornadas do Journey Optimizer para análise e personalização mais profundas | Não | Não |

{style="table-layout:auto"}



## Seção de filtro de tag {#tagfiltersection}

| Tags | Descrição |
|---|---|
| ![Tags](/help/assets/filter-tag.png){width="300"} | A seção **[!UICONTROL Tags]** permite filtrar por tags. <ul><li>Você pode ![Pesquisar](/help/assets/icons/Search.svg) *Pesquisar tags* para procurar tags que você pode usar para filtrar.</li><li>É possível selecionar mais de uma tag. As tags disponíveis dependem das seleções feitas em outras seções no painel de filtro.</li><li>Os números indicam:<ul><li>**(1)**: o número de tags selecionadas (se uma ou mais tags forem selecionadas).</li><li>**2︎⃣**: o número de tags disponíveis para os itens resultantes do filtro atual.</li><li>7︎⃣: o número de itens associados à tag específica.</li></ul></li></ul> |


## Seção de filtro do conjunto de relatórios {#reportsuitefiltersection}

| Conjunto de relatórios | Descrição |
|---|---|
| ![Republicar conjunto](/help/assets/filter-reportsuite.png){width="300"} | A seção **[!UICONTROL Conjunto de relatórios]** permite filtrar por conjuntos de relatórios. <ul><li>Você pode ![Pesquisar](/help/assets/icons/Search.svg) *Pesquisar conjuntos de relatórios* para procurar conjuntos de relatórios que você possa usar para filtrar.</li><li>É possível selecionar mais de um conjunto de relatórios. Os conjuntos de relatórios disponíveis dependem das seleções feitas em outras seções no painel de filtro.</li><li>Os números indicam:<ul><li>**(2)**: o número de conjuntos de relatórios selecionados (se um ou mais conjuntos de relatórios estiverem selecionados).</li><li>**3︎⃣**: o número de conjuntos de relatórios disponíveis para os itens resultantes do filtro atual.</li><li>4︎⃣: o número de itens associados ao conjunto de relatórios específico.</li></ul></li></ul> |

## Seção de filtro de status habilitado {#enabledstatusfiltersection}

| Status habilitado | Descrição |
|---|---|
| ![Status habilitado](/help/assets/filter-enabledstatus.png){width="300"} | A seção **[!UICONTROL Status habilitado]** permite filtrar pelo status habilitado. <ul><li>Você pode selecionar mais de um status.</li><li>Os números indicam:<ul><li>**(2)**: o número de status selecionados (se um ou mais status forem selecionados).</li><li>**2︎⃣**: o número de status disponíveis para os itens resultantes do filtro atual.</li><li>1︎⃣: o número de itens associados ao status específico.</li></ul></li></ul> |

## Seção de filtro de tipo {#typefiltersection}

| Tipo | Descrição |
|---|---|
| ![Tipo](/help/assets/filter-type.png){width="300"} | A seção **[!UICONTROL Tipo]** permite filtrar por tipo. <ul><li>Você pode selecionar mais de um tipo.</li><li>Os números indicam:<ul><li>**(2)**: o número de tipos selecionados (se um ou mais tipos forem selecionados).</li><li>**1︎⃣**: o número de tipos disponíveis para os itens resultantes do filtro atual.</li><li>3︎⃣: o número de itens associados ao tipo específico.</li></ul></li></ul> |

## Seção de filtro Proprietário {#ownerfiltersection}

| Proprietário | Descrição |
|---|---|
| ![Proprietários](/help/assets/filter-owners.png){width="300"} | A seção **[!UICONTROL Proprietário]** permite filtrar por proprietários. <ul><li>Use o recurso ![Pesquisar](/help/assets/icons/Search.svg) *Pesquisar proprietários* para encontrar proprietários que você possa usar para filtrar.</li><li>É possível selecionar mais de um proprietário. Os proprietários disponíveis dependem das seleções feitas em outras seções no painel de filtro.</li><li>Os números indicam:<ul><li>**(2)**: o número de proprietários selecionados (se um ou mais proprietários forem selecionados).</li><li>**3︎⃣**: o número de proprietários disponíveis para os itens resultantes do filtro atual.</li><li>4︎⃣: o número de itens associados ao proprietário específico.</li></ul></li></ul> |

## Seção de outros filtros {#otherfiltersfiltersection}

| Outros filtros | Descrição |
|---|---|
| ![Outros filtros](/help/assets/filter-other.png){width="300"} | A seção **[!UICONTROL Outros filtros]** permite filtrar por outros filtros predefinidos.<ul><li>Você pode selecionar uma ou mais das seguintes opções:<ul><li> **[!UICONTROL Exibir tudo]**</li><li>**[!UICONTROL Compartilhado comigo]**</li><li>**[!UICONTROL Meu]**</li><li>**[!UICONTROL Aprovado]**</li><li>**[!UICONTROL Favoritos]**</li></ul> O que você pode selecionar depende da sua função e das suas permissões.</li><li>É possível selecionar vários outros filtros. Os outros filtros disponíveis dependem das seleções feitas em outras seções no painel de filtros.</li><li>Os números indicam:<ul><li>**(1)**: o número de outros filtros selecionados (se um ou mais outros filtros forem selecionados).</li><li>**5︎⃣**: o número de outros filtros disponíveis para os itens resultantes do filtro atual.</li><li>4︎⃣: o número de itens associados ao outro filtro específico.</li></ul></li></ul> |

## Seção de filtro de intervalo de datas  {#daterangefiltersection}

| Intervalo de datas aplicado | Descrição |
|---|---|
| ![Intervalo de datas](/help/assets/filter-daterange.png){width="300"} | A seção Intervalo de datas aplicado permite filtrar um intervalo de datas aplicado aos itens.<ol><li>Selecione um intervalo de datas.</li><li>No pop-up do calendário, defina um intervalo de datas ou selecione uma das predefinições disponíveis.<br>Como alternativa, também é possível especificar um intervalo de datas diretamente na seção Intervalo de datas do painel Filtro.</li></ol><ul><li>Os números indicam:<ul><li>**(1)**: o número de intervalos de datas modificados a partir das predefinições padrão.</li><li>**5︎⃣**: o número de intervalos de datas disponíveis para os itens resultantes do filtro atual.</li></ul> |


## Descontinuação do importador de classificação {#classification-importer-deprecation}

>[!WARNING]
>
>O importador de classificação está obsoleto e não estará mais acessível após **31 de agosto de 2026**. Alterne para a experiência de [Conjuntos de classificação](/help/components/classifications/sets/overview.md) para garantir a funcionalidade contínua.
>



## Descontinuação do Construtor de regras de classificação {#classification-rulebuilder-deprecation}

>[!WARNING]
>
>O construtor de regras de classificação está obsoleto e não estará mais acessível após **31 de agosto de 2026**. Alterne para a experiência de [Conjuntos de classificação](/help/components/classifications/sets/overview.md) para garantir a funcionalidade contínua.
>

