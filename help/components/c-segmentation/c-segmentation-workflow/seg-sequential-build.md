---
description: Segmentos sequenciais são criados por meio do operador THEN, em vez de AND ou OR. THEN implica que um critério de segmento ocorre, seguido de outro. Por padrão, um segmento sequencial identifica todos os dados correspondentes, mostrados no filtro "Incluir todos". Segmentos sequenciais podem ser filtrados ainda mais para um subconjunto de ocorrências correspondentes que usam as opções “Apenas antes da sequência” e "Apenas após a sequência".
seo-description: Segmentos sequenciais são criados por meio do operador THEN, em vez de AND ou OR. THEN implica que um critério de segmento ocorre, seguido de outro. Por padrão, um segmento sequencial identifica todos os dados correspondentes, mostrados no filtro "Incluir todos". Segmentos sequenciais podem ser filtrados ainda mais para um subconjunto de ocorrências correspondentes que usam as opções “Apenas antes da sequência” e "Apenas após a sequência".
seo-title: Construir segmentos sequenciais
solution: Analytics
title: Construir segmentos sequenciais
topic: Segmentos
uuid: 7 fb 9 f 1 c 7-a 738-416 a-aaa 2-d 77 e 40 fa 7 e 61
translation-type: tm+mt
source-git-commit: b21f741216af8edc631cc271618f638d46a16a96

---


# Construir segmentos sequenciais

Segmentos sequenciais são criados por meio do operador THEN, em vez de AND ou OR. THEN implica que um critério de segmento ocorre, seguido de outro. Por padrão, um segmento sequencial identifica todos os dados correspondentes, mostrados no filtro &quot;Incluir todos&quot;. Segmentos sequenciais podem ser filtrados ainda mais para um subconjunto de ocorrências correspondentes que usam as opções “Apenas antes da sequência” e &quot;Apenas após a sequência&quot;.

![](assets/before-after-sequence.png)

Além disso, é possível restringir os segmentos sequenciais a uma duração de tempo, granularidade e contagens específicas entre pontos de verificação ao usar o [Operadores Depois e Dentro](../../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_07708877D06742998C6237DD9FD194EA).

## Incluir todos {#section_75ADDD5D41F04800A09E592BB2940B35}

Ao criar o segmento usando a definição “Incluir todos”, o segmento identifica caminhos que correspondem ao padrão como um todo. Veja abaixo um exemplo de um segmento de sequência básico procurando por uma ocorrência (Página A) seguido por outro (Página B) acessado pelo mesmo visitante. O segmento está definido como Incluir todos.

![](assets/sequence-filter.png)

| Se resultado… | Sequência |
|--- |--- |
| Corresponde | A then B<br>A then (in a different visit) B<br>A then D then B |
| Não corresponde | B depois A |

## Apenas antes da sequência ou apenas após a sequência {#section_736E255C8CFF43C2A2CAAA6D312ED574}

As opções **[!UICONTROL Apenas antes da sequência]** e **Apenas após a sequência]filtram o segmento em um subconjunto de dados antes e depois da sequência especificada.[!UICONTROL **

* **Apenas antes da sequência**: inclui todas as ocorrências antes de uma sequência + a primeira ocorrência da própria sequência (consulte o exemplo 1, 3). Se uma sequência aparece várias vezes em um caminho, “Apenas antes da sequência” inclui a primeira ocorrência da última ocorrência da sequência e todas as ocorrências anteriores (consulte o exemplo 2).
* **Apenas após a sequência**: inclui todas as ocorrências após uma sequência + a última ocorrência da própria sequência (consulte o exemplo 1, 3). Se uma sequência aparece várias vezes em um caminho, “Apenas após” inclui a última ocorrência da primeira ocorrência da sequência e todas as ocorrências posteriores (consulte o exemplo 2).

Por exemplo,  uma sequência de B -&gt; D. Os três filtros identificariam as ocorrências como se segue:considere 

**Exemplo 1: B então D aparece uma vez**

| Exemplo | Uma | B | C | D | E | F |
|---|---|---|---|---|---|---|
| Incluir todos | Uma | B | C | D | E | F |
| Somente antes da sequência | Uma | B |  |  |  |  |
| Somente após sequência |  |  |  | D | E | F |

**Exemplo 2: B então D aparece várias vezes**

| Exemplo | Uma | B | C | D | B | C | D | E |
|---|---|---|---|---|---|---|---|---|
| Incluir todos | Uma | B | C | D | B | C | D | E |
| Somente antes da sequência | Uma | B | C | D | B |  |  |  |
| Somente após sequência |  |  |  | D | B | C | D | E |

Também vamos modelar este conceito com a dimensão Profundidade da ocorrência.

**Exemplo 3: profundidade da ocorrência 3 então 5**

![](assets/hit-depth.png)

## Restrições de dimensão {#section_EAFD755F8E674F32BCE9B642F7F909DB}

Em uma cláusula “dentro”, entre instruções ENTÃO, é possível adicionar, por exemplo, “dentro de uma instância de palavra-chave de pesquisa”, “dentro de uma instância eVar 47”. Isso restringe o segmento a uma instância de uma dimensão.

Definir uma cláusula “dentro da dimensão” entre regras permite que o segmento restrinja dados a sequências que satisfazem a essa cláusula. Observe o exemplo abaixo, onde a restrição está definida como “Dentro de uma página”:

![](assets/sequence-filter4.png)

| Se resultado… | Sequência |
|--- |--- |
| Corresponde | A depois B |
| Não corresponde | A then C then B (because B was not within 1 page of A)<br>**Note:**  If the dimension restriction is taken out, &quot;A then B&quot; and &quot;A then C then B&quot; would both match. |

## Sequência de exibição de página simples

Identifique visitantes que visualizaram uma página e, depois, outra página. Os dados no nível da ocorrência filtram essa sequência independentemente das sessões de visita anteriores, passadas ou temporárias, ou do tempo ou visualizações de página ocorridos.

**Exemplo**: O Visitante visualizou a página A, depois visualizou a página B na mesma visita ou em outra.

**Casos de uso**

Os seguintes exemplos mostram como o segmento pode ser usado.

1. Os visitantes de um site de esportes visualizam a página de aterrissagem de futebol e, em seguida, visualizam a página de aterrissagem do basquete na ordem sequencial, mas não necessariamente na mesma visita. Isso solicita uma campanha a mostrar conteúdo de basquete para interessados em futebol durante a temporada de futebol.
1. Revendedor de carros identifica uma relação entre aqueles que chegam na página de fidelidade do cliente e, em seguida, vão para a página de vídeo a qualquer momento durante a visita ou outra visita.

**Criar este segmento**

Você aninha duas regras de página em um contêiner de nível superior de [!UICONTROL Visitante] e faz a sequência de ocorrência da página com o operador [!UICONTROL ENTÃO].

![](assets/segment_sequential_1.png)

## Sequência do visitante em visitas

Identifique os visitantes que desistiram de uma campanha, mas voltaram para a sequência de exibições de página em outra sessão.

**Exemplo**: O visitante visualizou a página A em uma visita e visualizou a página B em outra visita.

**Casos de uso**

Os seguintes exemplos sobre como esse tipo de segmento pode ser usado:

* Os visitantes à página Esportes de um site de notícias revisita a página de Esportes em outra sessão.
* Um revendedor de roupas nota uma relação entre visitantes que chegam em uma página de aterrissagem em uma sessão, em seguida, vão diretamente para a página de checkout em outra sessão.

**Criar este segmento**

Esse exemplo aninha dois contêineres de **[!UICONTROL Visita]** no contêiner de **[!UICONTROL Visitantes]de nível superior e faz a sequência com o operador** ENTÃO[!UICONTROL .]

![](assets/visitor_seq_across_visits.png)

## Sequência de nível misto

Identifique visitantes que visualizam duas páginas em determinado número de visitas, mas visualize uma terceira página em uma visita separada.

**Exemplo**: Os visitantes visitam a página A e a página B em uma ou mais visitas, seguido por uma visita à página C em uma visita separada.

**Casos de uso**

Os seguintes exemplos sobre como esse tipo de segmento pode ser usado:

* Primeiro, os visitantes visitam um site de notícias e, em seguida, visualizam a página de esportes na mesma visita. Ou, em outra visita, o visitante visita a página de previsão do tempo.
* O revendedor define os visitantes que entram na Página principal e, em seguida, vão até a página da Minha conta. Em outra visita, eles visitam a página de Visualizar carrinho.

**Criar este segmento**

1. Solte duas Dimensões de página dos painéis à esquerda do contêiner de nível superior [!UICONTROL Visitante].
1. Adicione o operador ENTÃO entre elas.
1. Click **[!UICONTROL Options]** &gt; **[!UICONTROL Add container]** and add a [!UICONTROL Visit] container underneath the [!UICONTROL Visitor] level and sequenced using the [!UICONTROL THEN] operator.

![](assets/mixed_level_checkpoints.png)

## Contêineres agregados

Adicionar vários contêineres no nível de [!UICONTROL Ocorrência] em um contêiner de [!UICONTROL Visitante] permite empregar os operadores adequados entre o mesmo tipo de contêineres, bem como usar regras e dimensões como Número de visitas e Página para definir a exibição de página e fornecer uma dimensão de sequência no contêiner de [!UICONTROL Ocorrência]. Aplicar lógica no nível da Ocorrência permite restringir e combinar as combinações como um mesmo nível de ocorrências no contêiner de [!UICONTROL Visitante] para elaborar diversos tipos de segmento.

**Exemplo**: os visitantes visitaram a página A após a primeira ocorrência na sequência de exibições de página (página D no exemplo) e depois visitaram a página B ou C sem considerar o número de sessões da visita.

**Casos de uso**

Os seguintes exemplos sobre como esse tipo de segmento pode ser usado:

* Identifique visitantes que vão para a página de aterrissagem principal em uma visita, em seguida, visualizam a página de roupas Masculinas em outra visita, então visualizam a página de aterrissagem Feminina ou de Crianças em uma visita diferente.
* Um e-zine capta os visitantes que vão para a Página inicial em uma visita, a página de Esportes em outra visita e a página de Opinião em outra.

**Criar este segmento**

1. Selecione o contêiner de [!UICONTROL Visitante] como contêiner de nível superior.
1. Adicione dois contêineres no nível da [!UICONTROL Ocorrência], uma dimensão com uma dimensão numérica adequada unida no mesmo nível de [!UICONTROL Ocorrência] pelo operador [!UICONTROL E] e [!UICONTROL OU].
1. No contêiner de [!UICONTROL Visita], adicione outro contêiner de [!UICONTROL Ocorrência] e aninhe dois outros contêineres de [!UICONTROL Ocorrência] unidos com um operador [!UICONTROL OR] ou [!UICONTROL AND].

   Coloque esses contêineres de [!UICONTROL Ocorrência] aninhados em sequência com o operador [!UICONTROL ENTÃO].

![](assets/aggregate_checkpoints2.png)

## &quot; Aninhamento &quot;nos segmentos sequenciais

Ao colocar pontos de verificação em ambos os níveis de [!UICONTROL Visita] e [!UICONTROL Ocorrência], é possível restringir o segmento para que atenda aos requisitos em uma visita específica, bem como em uma ocorrência específica.

**Exemplo**: O visitante visitou a página A e depois a página B na mesma visita. Em uma nova visita, o visitante foi para a página C.

**Criar este segmento**

1. Sob o contêiner de nível superior [!UICONTROL Visita], arraste duas dimensões de página.
1. Multi-select both rules, click **[!UICONTROL Options]** &gt; **[!UICONTROL Add container from selection]** and change it to a [!UICONTROL Visit] container.
1. Una-os com o operador [!UICONTROL ENTÃO].
1. Crie um contêiner de Ocorrência como um par do contêiner [!UICONTROL Visita] e arraste uma dimensão de página.
1. Una a sequência aninhada no contêiner de [!UICONTROL Visita] com o contêiner de [!UICONTROL Ocorrência] usando outro operador [!UICONTROL ENTÃO].

![](assets/nesting_sequential_seg.png)

## Excluir ocorrências

As regras do segmento incluem todos os dados, a menos que você exclua especificamente os dados de [!UICONTROL Visitante], [!UICONTROL Visita] ou [!UICONTROL Ocorrência] usando a regra [!UICONTROL Excluir]. Isso permite recusar dados comuns e criar segmentos com um foco maior. Ou permite criar segmentos excluindo grupos encontrados para identificar o conjunto de dados restante, como ao criar uma regra que inclui visitantes bem sucedidos que fizeram pedidos e depois os excluíram para identificar os &quot;não compradores&quot;. Contudo, na maioria dos casos, é melhor criar regras que excluam valores abrangentes do que tentar usar a regra [!UICONTROL Excluir] para direcionar valores de inclusão específicos.

Por exemplo:

* **Excluir páginas**. Use uma regra de segmento para retirar uma página específica (como *`Home Page`*) de um relatório, criar uma regra de Ocorrência em que a página seja igual à &quot;Página inicial&quot; e, então, excluí-la. Essa regra inclui automaticamente todos os valores, salvo a Página inicial.
* **Excluir os domínios de referência**. Use uma regra que inclua somente os domínios de referência do Google.com e exclua todos os outros.
* **Identificar não compradores**. Identifique quando os pedidos são maiores que zero e, então, exclua o [!UICONTROL Visitante].

O operador [!UICONTROL Excluir] pode ser empregado para identificar uma sequência em que visitas ou ocorrências específicas não sejam realizadas pelo visitante. [!UICONTROL Excluir pontos de verificação] também pode ser incluído em um [Grupo lógico](../../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_23CE0E6071E14E51B494CD21A9799112).

## Excluir entre pontos de verificação

Assegure lógica aos visitantes do segmento em que um ponto de verificação não tenha ocorrido explicitamente entre dois outros pontos de verificação.

**Exemplo**: Os visitantes que visitaram a página A e depois visitaram a página C, mas não visitaram a página B.

**Casos de uso**

Os seguintes exemplos sobre como esse tipo de segmento pode ser usado:

* Visitantes de uma página de Estilo de vida e, em seguida, da seção de Cinema sem chegar a página de Artes.
* Um revendedor automático nota a relação entre aqueles que visitam a página de aterrissagem principal e, em seguida, vão para a campanha Sem interesse sem ir para a página de Veículos.

**Criar este segmento**

Crie um segmento como você faria para um  segmento sequencial simples, de nível variado ou aninhado e em seguida defina o operador [!UICONTROL EXCLUIR] para o elemento do contêiner. O exemplo abaixo é um segmento agregado em que os três contêineres de [!UICONTROL Ocorrência] são arrastados para o canvas, o operador [!UICONTROL THEN] é designado para unir a lógica do contêiner e, em seguida, exclui o contêiner de exibição de página do meio para incluir somente os visitantes que foram da página A para a página C na sequência.

![](assets/exclude_between_checkpoints.png)

## Excluir no início da sequência

Se o ponto de verificação excluído estiver no início de um segmento sequencial, isso assegura que uma exibição de página excluída não ocorreu antes da primeira ocorrência não excluída.

**Exemplo**: O visitante visitou a página A e não a página B.

**Casos de uso**

Estes são exemplos de casos de uso de como esse tipo de segmento pode ser usado:

* Visitantes que visitarem a página A e não visitaram a página B.
* Um restaurante deseja visualizar usuários inveterados que evitam a página de aterrissagem e vão diretamente para a página de Saída de pedido.

**Criar este segmento**

Crie dois contêineres de Ocorrência separados em um contêiner de Visitante de nível superior. Em seguida, defina o operador [!UICONTROL EXCLUIR] para o primeiro contêiner.

![](assets/exclude_beginning_sequence.png)

## Excluir no final da sequência

Se o ponto de verificação excluído estiver no final de uma sequência, isso garante que o ponto de verificação não ocorreu a partir do último ponto de verificação não excluído até o final da sequência do visitante.

**Exemplo**: Os visitantes visitam a página A e não visitaram a página B nas visitas atuais ou subsequentes.

**Casos de uso**

Os seguintes exemplos sobre como esse tipo de segmento pode ser usado:

* Visitantes que visitarem a página A e não visitaram a página B.
* Um restaurante deseja visualizar usuários inveterados que evitam a página de aterrissagem e vão diretamente para a página de Saída de pedido.

**Criar este segmento**

Build a simple sequence segment by dragging two [!UICONTROL Hit] containers to the canvas and connecting them using the [!UICONTROL THEN] operator. Em seguida, atribua o operador [!UICONTROL EXCLUIR] ao segundo próximo de [!UICONTROL Ocorrência] na sequência.

![](assets/exclude_end_sequence.png)

## Contêineres do Grupo lógico

Na segmentação sequencial, é necessário que os contêineres sejam ordenados rigorosamente dentro da [hierarquia do contêiner](../../../components/c-segmentation/seg-overview.md#concept_A38E7000056547399E346559D85E2551). O contêiner do [!UICONTROL Grupo lógico] foi designado para ser usado quando os contêineres de nível superior são necessários em segmentos sequenciais para filtrar ainda mais os visitantes e fornecer restrições complexas, aninhadas e no nível do visitante para refinar o segmento.

| Hierarquia do contêiner padrão |
|---|
| ![](assets/nesting_container.png) |
| No contêiner [!UICONTROL Visitante], os contêineres [!UICONTROL Visita] e [!UICONTROL Ocorrência] são aninhados em sequência para extrair os segmentos com base nas ocorrências, no número de visitas e no visitante. |

>[!NOTE]
>
>A [!UICONTROL Logic Group] can only be defined in a sequential segment, meaning that the [!UICONTROL THEN] operator is used within the expression.

Um contêiner do [!UICONTROL Grupo lógico] trata vários pontos de verificação como um grupo sem ordem. Por exemplo, não é possível aninhar um contêiner de [!UICONTROL Visitante] em um contêiner de [!UICONTROL Visitante]. Mas, em vez disso, você pode aninhar um contêiner do [!UICONTROL Grupo lógico] em um contêiner de [!UICONTROL Visitante] com pontos de verificação de nível de [!UICONTROL Visita] e [!UICONTROL Ocorrência].

| Hierarquia não padrão do contêiner lógico |
|---|
| ![](assets/logic_group_hierarchy.png) |
| A hierarquia do contêiner padrão também é necessária fora do contêiner do [!UICONTROL Grupo lógico]. Mas dentro do contêiner do [!UICONTROL Grupo lógico], os pontos de verificação não requerem uma ordem estabelecida nem uma hierarquia. Esses pontos de verificação precisam simplesmente ser cumpridos pelo visitante em qualquer ordem. |

## Build a Logic Group segment {#section_A5DDC96E72194668AA91BBD89E575D2E}

Assim como outros contêineres, os contêineres do [!UICONTROL Grupo lógico] podem ser construídos de  várias maneiras no [!UICONTROL Construtor de segmentos]. Veja a seguir uma forma preferida de aninhar contêineres do [!UICONTROL Grupo lógico]:

1. Arraste dimensões, eventos ou segmentos dos painéis à esquerda.
1. Altere o contêiner superior para um contêiner de [!UICONTROL Visitante].
1. Altere o operador [!UICONTROL E] ou [!UICONTROL OU] inserido por padrão no operador ENTÃO.
1. Select the [!UICONTROL Hit] containers (the Dimension, Event, or Item) and click **[!UICONTROL Options]** &gt; **[!UICONTROL Add container from selection]**.
1. Clique no ícone do contêiner e selecione **[!UICONTROL Grupo lógico]**.  ![](assets/logic_group_checkpoints.png)
1. Agora, você pode definir a [!UICONTROL Ocorrência] no contêiner do [!UICONTROL Grupo lógico] independentemente da hierarquia.

## Pontos de verificação do Grupo lógico em qualquer ordem

Usar o [!UICONTROL Grupo lógico] permite satisfazer as condições nesse grupo que está fora da sequência. Isso permite construir segmentos em que há um contêiner de [!UICONTROL Visita] ou de [!UICONTROL Ocorrência] independentemente da hierarquia normal.****

**Exemplo**: Visitantes que visitaram a página A e, em seguida, visitaram a página B e C em qualquer ordem.

**Criar este segmento**

As páginas B e C são aninhadas em um contêiner de [!UICONTROL Grupo lógico] no contêiner de [!UICONTROL Visitante] exterior. O contêiner [!UICONTROL Ocorrência] de A é seguido pelo contêiner de [!UICONTROL Grupo lógico] com B e C identificados por meio do operador [!UICONTROL E]. Como está no [!UICONTROL Grupo lógico], a sequência não é definida e fazer uma ocorrência na página B ou C torna o argumento verdadeiro.

![](assets/logic_group_any_order2.png)

## Primeira correspondência do Grupo lógico

Usar o [!UICONTROL Grupo lógico] permite satisfazer as condições nesse grupo que está fora da sequência. Neste segmento de primeira correspondência não ordenado, as regras do [!UICONTROL Grupo lógico] são identificadas primeiro para serem uma exibição de página da página B ou da página C, depois a visualização necessária da página A.

**Exemplo**: Visitantes que visitaram a página B ou C e, em seguida, visitaram a página A.

**Criar este segmento**

As dimensões das páginas B e C são agrupadas em um contêiner do [!UICONTROL Grupo lógico] com o operador [!UICONTROL OU] selecionado e o contêiner de [!UICONTROL Ocorrência] identificando a exibição da página A como o valor.

![](assets/logic_group_1st_match.png)

## Excluir E do Grupo lógico

Construa segmentos usando o [!UICONTROL Grupo lógico] em que várias exibições de página são agregadas para definir que páginas precisaram ser acessadas, ao passo que outras foram evitadas especificamente. ****

**Exemplo**: O visitante visitou a página A e, em seguida, não visitou explicitamente a página B ou C, mas ocorrência da página D.

**Criar este segmento**

Construa esse segmento arrastando dimensões, eventos e segmentos pré-criados dos painéis à esquerda. Consulte [Construção de um segmento de grupo lógico](../../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_23CE0E6071E14E51B494CD21A9799112).

Depois de aninhar os valores com o [!UICONTROL Grupo lógico], clique no botão **[!UICONTROL Excluir]** no contêiner do [!UICONTROL Grupo lógico].

![](assets/logic_exclude_and.png)

## Excluir OU do Grupo lógico

Construa segmentos usando o [!UICONTROL Grupo lógico] em que várias exibições de página são agregadas para definir que páginas precisaram ser acessadas, ao passo que outras foram evitadas especificamente.

**Exemplo**: Visitantes que visitaram a página A, mas não visitaram a Página B ou C antes da página A.

**Criar este segmento**

As páginas B e C iniciais são identificadas em um contêiner de [!UICONTROL Grupo lógico] que está excluído e, então, seguidas por um acesso à página A pelo visitante.

Construa esse segmento arrastando dimensões, eventos e segmentos pré-criados dos painéis à esquerda.

Depois de aninhar os valores com o [!UICONTROL Grupo lógico], clique no botão **[!UICONTROL Excluir]** no contêiner do [!UICONTROL Grupo lógico].

![](assets/logic_exclude_or.png)

## Criar segmentos de tempo dentro e de tempo após

Use os operadores [!UICONTROL Dentro] e [!UICONTROL Depois] integrados no cabeçalho de cada contêiner para definir o tempo, eventos e contagem.

![](assets/then_within_operators.png)

É possível limitar a correspondência para uma duração de tempo específica por meio dos contêineres [!UICONTROL Dentro] e [!UICONTROL Depois] e especificando uma granularidade e contagem. O operador [!UICONTROL Dentro] é usado para especificar um limite máximo na quantidade de tempo entre dois pontos de verificação. O operador [!UICONTROL Depois] é usado para especificar um limite mínimo na quantidade de tempo entre dois pontos de verificação.

## Operadores Depois e Dentro {#section_CCAF5E44719447CFA7DF8DA4192DA6F8}

A duração é especificada por uma única letra maiúscula representando a granularidade seguida por um número representando a contagem de repetição da granularidade.

**[!UICONTROL Dentro]** inclui o ponto de extremidade (menor do que ou igual a).

**[!UICONTROL Depois]** não inclui o ponto de extremidade (maior do que).

| Operadores | Descrição |
|--- |--- |
| AFTER | O operador Depois é usado para especificar um limite mínimo na quantidade de tempo entre dois pontos de verificação. Ao definir os valores de Depois, o limite de tempo começará quando o segmento for aplicado. Por exemplo, se o operador Depois estiver definido em um contêiner para identificar os visitantes que visitam a página A, mas não retornarem para visitar a página B depois de um dia, esse dia começará quando o visitante sair da página A. Para que o visitante seja incluído no segmento, no mínimo 1440 minutos (um dia) devem transpocorrer após sair da página A para visualizar a página B. |
| WITHIN | O operador Dentro é usado para especificar um limite máximo na quantidade de tempo entre dois pontos de verificação. Por exemplo, se o operador Dentro estiver definido em um contêiner para identificar os visitantes que visitam a página A e depois retornarem a página B dentro de um dia, esse dia começará quando o visitante sair da página A. Para ser incluído no segmento, o visitante terá um tempo máximo de um dia antes de abrir a página B. Para que o visitante seja incluído no segmento, a visita à página B deve ocorrer dentro de um máximo de 1440 minutos (um dia) após sair da página A para visualizar a página B. |
| DEPOIS/DENTRO | Ao usar ambos os operadores Depois e Dentro, é importante compreender que ambos os operadores começarão e terminarão simultaneamente, não em sequência.   For example, if you build a segment with the container set to:<br>`After = 1 Week(s) and Within = 2 Week(s)`<br>Then the conditions to identify visitors in the segment are met only between 1 and 2 weeks. As duas condições são aplicadas a partir da primeira ocorrência da página. |

## Use o operador Depois

* A definição de tempo Depois permite rastrear por ano, mês, dia, hora e minuto para corresponder às visitas.
* A definição de tempo Depois pode ser aplicada somente a um contêiner de [!UICONTROL Ocorrência], visto que essa granularidade fina é definida somente nesse nível.

**Exemplo**: Os visitantes que visitaram a página A depois visitaram a página B depois de 2 semanas. ****

![](assets/time_between_after_operator.png)

**Criar o segmento**: Esse segmento é criado adicionando um contêiner [!UICONTROL de Visitante] com dois contêineres [!UICONTROL de Ocorrência] . Em seguida, você pode definir o operador [!UICONTROL ENTÃO], abrir o menu suspenso do operador [!UICONTROL DEPOIS] e definir o número de semanas.

![](assets/after_operator.png)

**Corresponde**

Ao determinar &quot;Após 2 semanas&quot;, se houver uma ocorrência na página A em 1° de junho de 2019 às 00:01, a próxima ocorrência na página B corresponderá contanto que seja realizada antes de 00:01 de 15 de junho de 2019 (14 dias depois).

| Ocorrência A | Ocorrência B | Correspondência |
|--- |--- |--- |
| Ocorrência **A**: 1 de junho de 2019 00:01 | **Ocorrência B**: 15 de junho de 2019 00:01 | **Corresponde:** Essa restrição de tempo corresponde porque é Após 1 ° de junho de 2019 (duas semanas). |
| Ocorrência **A**: 1 de junho de 2019 00:01 | **** Ocorrência B: Ocorrência de june de junho de 2019: hit de junho de:0:0: 15 de junho de 25 19 00001 | **Não corresponde:** A primeira ocorrência na página B não corresponde porque está em conflito com a restrição que exigia a ocorrência após duas semanas. |

## Use o operador Dentro

* [!UICONTROL Dentro] permite rastrear por ano, mês, dia, hora e minuto para corresponder visitas.
* [!UICONTROL Dentro] pode ser aplicado somente a um contêiner de [!UICONTROL Ocorrência], visto que essa granularidade fina é definida somente nesse nível.

>[!IMPORTANT]
>
>Em uma cláusula “dentro”, entre instruções ENTÃO, é possível adicionar, por exemplo, “dentro de uma instância de palavra-chave de pesquisa”, “dentro de uma instância eVar 47”. Isso restringe o segmento a uma instância de uma dimensão.

**Exemplo**: Os visitantes que visitaram a página A e, em seguida, visitaram a página B em 5 minutos.

![](assets/time_between_within_operator.png)

**Crie o segmento**: Esse segmento é criado adicionando um [!UICONTROL contêiner de Visitante] e arrastando com dois contêineres [!UICONTROL de Ocorrência] . Em seguida, você pode definir o operador [!UICONTROL ENTÃO] e abrir o menu suspenso do operador [!UICONTROL APÓS], além de definir o intervalo: ocorrências, visualizações de página, visitas, minutos, horas, dias, semanas, meses, semestres ou anos.

![](assets/within_operator.png)

**Corresponde**

As correspondências devem ocorrer dentro do limite de tempo. Para a expressão, se um visitante faz a ocorrência da página A às 00:01, uma ocorrência a seguir à página B corresponderá contanto que ocorra em ou antes de 00:06 (cinco minutos depois, incluindo o mesmo minuto). As ocorrências dentro do mesmo minuto também corresponderão.

## Os operadores Dentro e Depois

Use o [!UICONTROL Dentro] e o [!UICONTROL Depois] para fornecer um terminal mínimo e máximo em ambas as extremidades de um segmento.

**Exemplo**: Os visitantes que visitaram a página A depois visitaram a página B após 2 semanas, mas dentro de um mês.

![](assets/time_between_using_both_operators.png)

**Criar o segmento**: Crie o segmento sequenciando dois contêineres [!UICONTROL de Ocorrência] em um [!UICONTROL contêiner de Visitante] . Em seguida, defina os operadores [!UICONTROL Depois] e [!UICONTROL Dentro].

![](assets/within_after_together.png)

**Corresponde**

Todos os visitantes que acessam a página A em 1° de junho de 2019 voltam depois de 15 de junho de 2019 às 00:01, mas *antes* de 1° de julho de 2019 estão incluídos no segmento. Compare com [Tempo entre exclusões](../../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_C5CB0A391B7C4AC8A95B9724A14E28E8).

Os operadores [!UICONTROL Depois] e [!UICONTROL Dentro] podem ser usados em conjunto para definir um segmento sequencial.

![](assets/time_between_within_after.png)

Esse exemplo retrata uma segunda visita para acessar a página B após duas semanas, mas dentro de um mês.
