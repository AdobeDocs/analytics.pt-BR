---
description: Segmentos sequenciais são criados por meio do operador THEN, em vez de AND ou OR. THEN implica que um critério de segmento ocorre, seguido de outro. Por padrão, um segmento sequencial identifica todos os dados correspondentes, mostrados no filtro "Incluir todos". Segmentos sequenciais podem ser filtrados ainda mais para um subconjunto de ocorrências correspondentes que usam as opções "Somente antes da sequência" e "Somente após da sequência".
title: Construir segmentos sequenciais
feature: Segmentation
exl-id: 2ac4e6db-3111-45e5-bedf-7d9b7b1ae352
source-git-commit: 0fd1f7a9dd876eef02dd6dbf9e40426b0acdbc17
workflow-type: tm+mt
source-wordcount: '3934'
ht-degree: 95%

---

# Construir segmentos sequenciais

Segmentos sequenciais são criados por meio do operador THEN, em vez de AND ou OR. THEN implica que um critério de segmento ocorre, seguido de outro. Por padrão, um segmento sequencial identifica todos os dados correspondentes, mostrados no filtro &quot;Incluir todos&quot;. Segmentos sequenciais podem ser filtrados ainda mais para um subconjunto de ocorrências correspondentes que usam as opções &quot;Somente antes da sequência&quot; e &quot;Somente após da sequência&quot;.

![](assets/before-after-sequence.png)

Além disso, é possível restringir os segmentos sequenciais a uma duração de tempo, granularidade e contagens específicas entre pontos de verificação ao usar os [operadores After e Within](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).

Veja um vídeo sobre segmentação sequencial:

>[!VIDEO](https://video.tv.adobe.com/v/25405/?quality=12)

## Incluir todos {#section_75ADDD5D41F04800A09E592BB2940B35}

Ao criar o segmento usando a definição &quot;Incluir todos&quot;, o segmento identifica caminhos que correspondem ao padrão como um todo. Veja abaixo um exemplo de um segmento de sequência básico procurando por uma ocorrência (Página A) seguido por outro (Página B) acessado pelo mesmo visitante. O segmento está definido como Incluir todos.

![](/help/admin/admin/assets/filter.png)
![70a875e2-0ef9-4459-8648-77c60081d64d](https://git.corp.adobe.com/storage/user/5902/files/d55be11f-4c4c-4198-bba5-ecad27ebcabf)

| Se o resultado for... | Sequência |
|--- |--- |
| Corresponde | A então B<br>A então (em uma visita diferente) B<br>A então D então B |
| Não corresponde | B depois A |

## Somente antes da sequência ou somente após da sequência {#section_736E255C8CFF43C2A2CAAA6D312ED574}

As opções **[!UICONTROL Somente antes da sequência]** e **[!UICONTROL Somente após da sequência]** filtram o segmento em um subconjunto de dados antes e depois da sequência especificada.

* **Somente antes da sequência**: inclui todas as ocorrências antes de uma sequência + a primeira ocorrência da própria sequência (consulte o exemplo 1, 3). Se uma sequência aparece várias vezes em um caminho, &quot;Somente antes da sequência&quot; inclui a primeira ocorrência da última ocorrência da sequência e todas as ocorrências anteriores (consulte o exemplo 2).
* **Somente após da sequência**: inclui todas as ocorrências após uma sequência + a última ocorrência da própria sequência (consulte o exemplo 1, 3). Se uma sequência aparece várias vezes em um caminho, &quot;Apenas após&quot; inclui a última ocorrência da primeira ocorrência da sequência e todas as ocorrências posteriores (consulte o exemplo 2).

Por exemplo, uma sequência de B -> D. Os três filtros identificariam as ocorrências como se segue:

**Exemplo 1: B então D aparece uma vez**

| Exemplo | A | B | C | D | E | F |
|---|---|---|---|---|---|---|
| Incluir todos | A | B | C | D | E | F |
| Somente antes da sequência | A | B |  |  |  |  |
| Somente após sequência |  |  |  | D | E | F |

**Exemplo 2: B então D aparece várias vezes**

| Exemplo | A | B | C | D | B | C | D | E |
|---|---|---|---|---|---|---|---|---|
| Incluir todos | A | B | C | D | B | C | D | E |
| Somente antes da sequência | A | B | C | D | B |  |  |  |
| Somente após sequência |  |  |  | D | B | C | D | E |

Também vamos modelar este conceito com a dimensão Profundidade da ocorrência.

**Exemplo 3: profundidade da ocorrência 3 então 5**

![](assets/hit-depth.png)

## Restrições de dimensão {#section_EAFD755F8E674F32BCE9B642F7F909DB}

Em uma cláusula &quot;dentro&quot;, entre instruções THEN, é possível adicionar, por exemplo, &quot;dentro de uma instância de palavra-chave de pesquisa&quot;, &quot;dentro de uma instância eVar 47&quot;. Isso restringe o segmento a uma instância de uma dimensão.

Definir uma cláusula &quot;Within da dimensão&quot; entre regras permite que o segmento restrinja dados a sequências que satisfazem a essa cláusula. Observe o exemplo abaixo, onde a restrição está definida como “Within de uma página”:

![](assets/sequence-filter4.png)

| Se o resultado for... | Sequência |
|--- |--- |
| Corresponde | A depois B |
| Não corresponde | A então C então B (porque B não estava dentro de uma página de A)<br>**Observação:** se a restrição de dimensão for removida, &quot;A então B&quot; e &quot;A então C então B&quot; corresponderão. |

## Sequência de visualização de páginas simples

Identifique visitantes que visualizaram uma página e, depois, outra página. Os dados no nível da ocorrência filtram essa sequência independentemente das sessões de visita anteriores, passadas ou temporárias, ou do tempo ou visualizações de página ocorridos.

**Exemplo**: o Visitante visualizou a página A, em seguida, visualizou a página B na mesma visita ou em outra.

**Casos de uso**

Os seguintes exemplos mostram como o segmento pode ser usado.

1. Os visitantes de um site de esportes visualizam a página de aterrissagem de futebol e, em seguida, visualizam a página de aterrissagem do basquete na ordem sequencial, mas não necessariamente na mesma visita. Isso solicita uma campanha a mostrar conteúdo de basquete para interessados em futebol durante a temporada de futebol.
1. Revendedor de carros identifica uma relação entre aqueles que chegam na página de fidelidade do cliente e, em seguida, vão para a página de vídeo a qualquer momento durante a visita ou outra visita.

**Criar este segmento**

Você aninha duas regras de página em um contêiner de nível superior de [!UICONTROL Visitante] e faz a sequência de ocorrência da página com o operador [!UICONTROL THEN].

![](assets/segment_sequential_1.png)

## Sequência do visitante em visitas

Identifique os visitantes que desistiram de uma campanha, mas voltaram para a sequência de exibições de página em outra sessão.

**Exemplo**: o Visitante visualizou a página A em uma visita, depois visualizou a página B em outra visita.

**Casos de uso**

Os seguintes exemplos sobre como esse tipo de segmento pode ser usado:

* Os visitantes à página Esportes de um site de notícias revisita a página de Esportes em outra sessão.
* Um revendedor de roupas nota uma relação entre visitantes que chegam em uma página de aterrissagem em uma sessão, em seguida, vão diretamente para a página de checkout em outra sessão.

**Criar este segmento**

Esse exemplo aninha dois contêineres de **[!UICONTROL Visita]** no contêiner de **[!UICONTROL Visitantes]** de nível superior e faz a sequência com o operador [!UICONTROL THEN].

![](assets/visitor_seq_across_visits.png)

## Sequência de nível misto

Identifique visitantes que visualizam duas páginas em determinado número de visitas, mas visualize uma terceira página em uma visita separada.

**Exemplo**: os visitantes visitem a página A e depois a página B em uma ou mais visitas, seguido de uma visita à página C em uma visita separada.

**Casos de uso**

Os seguintes exemplos sobre como esse tipo de segmento pode ser usado:

* Primeiro, os visitantes visitam um site de notícias e, em seguida, visualizam a página de esportes na mesma visita. Ou, em outra visita, o visitante visita a página de previsão do tempo.
* O revendedor define os visitantes que entram na Página principal e, em seguida, vão até a página da Minha conta. Em outra visita, eles visitam a página de Visualizar carrinho.

**Criar este segmento**

1. Solte duas Dimensões de página dos painéis à esquerda do contêiner de nível superior [!UICONTROL Visitante].
1. Adicione o operador THEN entre elas.
1. Clique em **[!UICONTROL Opções]** > **[!UICONTROL Adicionar contêiner]** e adicione o contêiner [!UICONTROL Visita] sob o nível do [!UICONTROL Visitante] e sequenciado com o operador [!UICONTROL THEN].

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
1. Adicione dois contêineres no nível da [!UICONTROL Ocorrência], uma dimensão com uma dimensão numérica adequada unida no mesmo nível de [!UICONTROL Ocorrência] pelo operador [!UICONTROL AND] e [!UICONTROL OR].
1. No contêiner de [!UICONTROL Visita], adicione outro contêiner de [!UICONTROL Ocorrência] e aninhe dois outros contêineres de [!UICONTROL Ocorrência] unidos com um operador [!UICONTROL OR] ou [!UICONTROL AND].

   Coloque esses contêineres de [!UICONTROL Ocorrência] aninhados em sequência com o operador [!UICONTROL THEN].

![](assets/aggregate_checkpoints2.png)

## &quot;Aninhamento&quot; em segmentos sequenciais

Ao colocar pontos de verificação em ambos os níveis de [!UICONTROL Visita] e [!UICONTROL Ocorrência], é possível restringir o segmento para que atenda aos requisitos em uma visita específica, bem como em uma ocorrência específica.

**Exemplo**: o visitante visitou a página A e a página B na mesma visita. Em uma nova visita, o visitante foi para a página C.

**Criar este segmento**

1. Sob o contêiner de nível superior [!UICONTROL Visita], arraste duas dimensões de página.
1. Faça a seleção múltipla de ambas as regras, clique em **[!UICONTROL Opções]** > **[!UICONTROL Adicionar contêiner da seleção]** e altere para um contêiner de [!UICONTROL Visita].
1. Una-os com o operador [!UICONTROL THEN].
1. Crie um contêiner de Ocorrência como um par do contêiner [!UICONTROL Visita] e arraste uma dimensão de página.
1. Una a sequência aninhada no contêiner de [!UICONTROL Visita] com o contêiner de [!UICONTROL Ocorrência] usando outro operador [!UICONTROL THEN].

![](assets/nesting_sequential_seg.png)

## Excluir ocorrências

As regras do segmento incluem todos os dados, a menos que você exclua especificamente os dados de [!UICONTROL Visitante], [!UICONTROL Visita] ou [!UICONTROL Ocorrência] usando a regra [!UICONTROL Excluir]. Isso permite recusar dados comuns e criar segmentos com um foco maior. Ou permite criar segmentos excluindo grupos encontrados para identificar o conjunto de dados restante, como ao criar uma regra que inclui visitantes bem sucedidos que fizeram pedidos e depois os excluíram para identificar os &quot;não compradores&quot;. Contudo, na maioria dos casos, é melhor criar regras que excluam valores abrangentes do que tentar usar a regra [!UICONTROL Excluir] para direcionar valores de inclusão específicos.

Por exemplo:

* **Excluir páginas**. Use uma regra de segmento para retirar uma página específica (como *`Home Page`*) de um relatório, criar uma regra de Ocorrência em que a página seja igual à &quot;Página inicial&quot; e, então, excluí-la. Essa regra inclui automaticamente todos os valores, salvo a Página inicial.
* **Excluir os domínios de referência**. Use uma regra que inclua somente os domínios de referência do Google.com e exclua todos os outros.
* **Identificar não compradores**. Identifique quando os pedidos são maiores que zero e, então, exclua o [!UICONTROL Visitante].

O operador [!UICONTROL Exclude] pode ser empregado para identificar uma sequência em que visitas ou ocorrências específicas não sejam realizadas pelo visitante. [!UICONTROL Excluir pontos de verificação] também pode ser incluído em um [Grupo lógico](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).

### Excluir entre pontos de verificação

Assegure lógica aos visitantes do segmento em que um ponto de verificação não tenha ocorrido explicitamente entre dois outros pontos de verificação.

**Exemplo**: os visitantes que visitaram a página A e, em seguida, visitaram a página C, mas não visitaram a página B.

**Casos de uso**

Os seguintes exemplos sobre como esse tipo de segmento pode ser usado:

* Visitantes de uma página de Estilo de vida e, em seguida, da seção de Cinema sem chegar a página de Artes.
* Um revendedor automático nota a relação entre aqueles que visitam a página de aterrissagem principal e, em seguida, vão para a campanha Sem interesse sem ir para a página de Veículos.

**Criar este segmento**

Crie um segmento como você faria para um segmento sequencial simples, de nível variado ou aninhado e defina o operador [!UICONTROL EXCLUIR] para o elemento de contêiner. O exemplo abaixo é um segmento agregado em que os três contêineres de [!UICONTROL Ocorrência] são arrastados para o canvas, o operador [!UICONTROL THEN] é designado para unir a lógica do contêiner e, em seguida, exclui o contêiner de exibição de página do meio para incluir somente os visitantes que foram da página A para a página C na sequência.

![](assets/exclude_between_checkpoints.png)

### Excluir no início da sequência

Se o ponto de verificação excluído estiver no início de um segmento sequencial, isso assegura que uma exibição de página excluída não ocorreu antes da primeira ocorrência não excluída.

Por exemplo, um restaurante deseja ver usuários que tendem a evitar a página de aterrissagem principal e ir diretamente para a página de pedidos. Você pode visualizar esses dados excluindo ocorrências da página de aterrissagem e incluindo ocorrências da página Solicitar saída em um segmento sequencial.

**Criar este segmento**

Crie dois contêineres de Ocorrência separados em um contêiner de Visitante de nível superior. Em seguida, defina o operador [!UICONTROL EXCLUDE] para o primeiro contêiner.

![](assets/exclude_beginning_sequence.png)

### Excluir no final da sequência

Se o ponto de verificação excluído estiver no final de uma sequência, isso garante que o ponto de verificação não ocorreu a partir do último ponto de verificação não excluído até o final da sequência do visitante.

Por exemplo, uma loja de roupas quer ver todos os visitantes que visualizaram uma página de produto, mas que nunca acessaram o carrinho de compras depois. Esse exemplo pode ser simplificado para um visitante que acessa a página A e nunca prossegue para a página B nas visitas atuais ou subsequentes.

**Criar este segmento**

Criar sequência simples arrastando dois contêineres de [!UICONTROL Ocorrência] para a tela e os unindo por meio do operador [!UICONTROL THEN]. Em seguida, atribua o operador [!UICONTROL EXCLUDE] ao segundo próximo de [!UICONTROL Ocorrência] na sequência.

![](assets/exclude_end_sequence.png)

## Contêineres de Grupo lógico

Os contêineres do Grupo lógico são necessários para agrupar as condições em um único ponto de verificação de segmento sequencial. O contêiner especial do Grupo lógico está disponível somente na segmentação sequencial, para garantir que suas condições sejam atendidas após qualquer ponto de verificação sequencial anterior e antes de qualquer ponto de verificação sequencial posterior. As condições no próprio ponto de verificação do Grupo lógico podem ser cumpridas em qualquer ordem. Por outro lado, os contêineres não sequenciais (ocorrência, visita, visitante) não exigem que suas condições sejam atendidas na sequência geral, produzindo resultados não intuitivos, se usados com um operador THEN.
O contêiner do [!UICONTROL Grupo lógico] foi projetado para tratar *vários pontos de verificação como um grupo*, *sem qualquer ordem* entre os pontos de verificação agrupados. Em outras palavras, a ordem dos pontos de verificação nesse grupo não é importante. Por exemplo, não é possível aninhar um contêiner de [!UICONTROL Visitante] em um contêiner de [!UICONTROL Visitante]. Mas, em vez disso, você pode aninhar um contêiner do [!UICONTROL Grupo lógico] em um contêiner de [!UICONTROL Visitante] com pontos de verificação de nível de [!UICONTROL Visita] e [!UICONTROL Ocorrência].

>[!NOTE]
>
>Um [!UICONTROL Grupo lógico] só pode ser definido em um segmento sequencial, o que significa que o operador [!UICONTROL THEN] é usado na expressão.

| Hierarquia do contêiner | Ilustração | Definição |
|---|---|---|
| Hierarquia do contêiner padrão | ![](assets/nesting_container.png) | No contêiner [!UICONTROL Visitante], os contêineres [!UICONTROL Visita] e [!UICONTROL Ocorrência] são aninhados em sequência para extrair os segmentos com base nas ocorrências, no número de visitas e no visitante. |
| Hierarquia do contêiner lógico | ![](assets/logic_group_hierarchy.png) | A hierarquia do contêiner padrão também é necessária fora do contêiner do [!UICONTROL Grupo lógico]. Mas dentro do contêiner do [!UICONTROL Grupo lógico], os pontos de verificação não requerem uma ordem estabelecida nem uma hierarquia. Esses pontos de verificação precisam simplesmente ser cumpridos pelo visitante em qualquer ordem. |

Os grupos lógicos podem parecer intimidantes - veja algumas práticas recomendadas sobre como usá-los:

**Grupo lógico ou contêiner de Ocorrência/Visita?**
Se você quiser agrupar pontos de verificação sequenciais, seu &quot;contêiner&quot; será do Grupo lógico. No entanto, se esses pontos de verificação sequenciais precisarem ocorrer no escopo de uma única ocorrência ou visita, um contêiner de &quot;ocorrência&quot; ou &quot;visita&quot; será necessário. (É claro que a &quot;ocorrência&quot; não faz sentido para um grupo de pontos de verificação sequenciais, quando uma ocorrência não pode creditar mais de um ponto de verificação).

**Os Grupos lógicos simplificam a criação de segmentos sequenciais?**
Sim, eles podem. Vamos supor que você esteja tentando identificar este segmento de visitantes: **Visitantes que visualizaram a página A e, em seguida, visualizaram cada uma das páginas de B, C e D**

Você pode criar esse segmento sem um contêiner do Grupo lógico, mas ele é complexo e trabalhoso. Você deve especificar cada sequência de páginas que o visitante poderia visualizar:
* `Visitor Container [Page A THEN Page B THEN Page C THEN Page D] or`
* `Visitor Container [Page A THEN Page B THEN Page D THEN Page C] or`
* `Visitor Container [Page A THEN Page C THEN Page B THEN Page D] or`
* `Visitor Container [Page A THEN Page C THEN Page D THEN Page B] or`
* `Visitor Container [Page A THEN Page D THEN Page B THEN Page C] or`
* `Visitor Container [Page A THEN Page D THEN Page C THEN Page B]`

Um contêiner do Grupo lógico simplifica consideravelmente a criação desse segmento, como mostrado aqui:

![](assets/logic-grp-example.png)


### Criar um segmento do Grupo lógico {#section_A5DDC96E72194668AA91BBD89E575D2E}

Como outros contêineres, os contêineres do [!UICONTROL Grupo lógico] podem ser criados de várias formas no [!UICONTROL Construtor de segmentos]. Veja a seguir uma forma preferida de aninhar contêineres do [!UICONTROL Grupo lógico]:

1. Arraste dimensões, eventos ou segmentos dos painéis à esquerda.
1. Altere o contêiner superior para um contêiner de [!UICONTROL Visitante].
1. Altere o operador [!UICONTROL AND] ou [!UICONTROL OR] inserido por padrão no operador THEN.
1. Selecione os contêineres [!UICONTROL Ocorrência] (a Dimensão, o Evento ou Item) e clique em **[!UICONTROL Opções]** > **[!UICONTROL Adicionar contêiner da seleção]**.
1. Clique no ícone do contêiner e selecione **[!UICONTROL Grupo lógico]**.  ![](assets/logic_group_checkpoints.png)
1. Agora, você pode definir a [!UICONTROL Ocorrência] no contêiner do [!UICONTROL Grupo lógico] independentemente da hierarquia.

### Pontos de verificação do grupo lógico em qualquer ordem

Usar o [!UICONTROL Grupo lógico] permite satisfazer as condições nesse grupo que está fora da sequência. Isso permite construir segmentos em que há um contêiner de [!UICONTROL Visita] ou de [!UICONTROL Ocorrência] independentemente da hierarquia normal.

**Exemplo**: os visitantes que visitaram a página A visitaram depois as páginas B e C em qualquer ordem.

**Criar este segmento**

As páginas B e C são aninhadas em um contêiner de [!UICONTROL Grupo lógico] no contêiner de [!UICONTROL Visitante] exterior. O contêiner [!UICONTROL Ocorrência] de A é seguido pelo contêiner de [!UICONTROL Grupo lógico] com B e C identificados por meio do operador [!UICONTROL AND]. Como está no [!UICONTROL Grupo lógico], a sequência não é definida e fazer uma ocorrência nas páginas B e C torna o argumento verdadeiro.

![](assets/logic_group_any_order2.png)

**Outro exemplo**: visitantes que visitaram a página B ou C, então a página A:

![](assets/logic_group_any_order3.png)

O segmento deve corresponder pelo menos a um dos pontos de verificação do grupo lógico (B ou C). Além disso, as condições do grupo lógico podem ser cumpridas na mesma ocorrência ou em várias ocorrências.

### Primeira correspondência do grupo lógico

Usar o [!UICONTROL Grupo lógico] permite satisfazer as condições nesse grupo que está fora da sequência. Neste segmento de primeira correspondência não ordenado, as regras do [!UICONTROL Grupo lógico] são identificadas primeiro para serem uma exibição de página da página B ou da página C, depois a visualização necessária da página A.

**Exemplo**: os visitantes que visitaram a página B ou a página C, visitaram a página A.

**Criar este segmento**

As dimensões das páginas B e C são agrupadas em um contêiner do [!UICONTROL Grupo lógico] com o operador [!UICONTROL OR] selecionado e o contêiner de [!UICONTROL Ocorrência] identificando a exibição da página A como o valor.

![](assets/logic_group_1st_match.png)

### Excluir AND do Grupo lógico

Construa segmentos usando o [!UICONTROL Grupo lógico] em que várias exibições de página são agregadas para definir que páginas precisaram ser acessadas, ao passo que outras foram evitadas especificamente. ****

**Exemplo**: o visitante visitou a página A e não visitou explicitamente a página B ou C, mas acessou a página D.

**Criar este segmento**

Construa esse segmento arrastando dimensões, eventos e segmentos pré-criados dos painéis à esquerda. Consulte [Construção de um segmento de grupo lógico](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).

Depois de aninhar os valores com o [!UICONTROL Grupo lógico], clique no botão **[!UICONTROL Excluir]** no contêiner do [!UICONTROL Grupo lógico].

![](assets/logic_exclude_and.png)

### Excluir OR do grupo lógico

Construa segmentos usando o [!UICONTROL Grupo lógico] em que várias exibições de página são agregadas para definir que páginas precisaram ser acessadas, ao passo que outras foram evitadas especificamente.

**Exemplo**: os visitantes que visitaram a página A, mas não visitaram a página B ou C antes da página A.

**Criar este segmento**

As páginas B e C iniciais são identificadas em um contêiner de [!UICONTROL Grupo lógico] que está excluído e, então, seguidas por um acesso à página A pelo visitante.

Construa esse segmento arrastando dimensões, eventos e segmentos pré-criados dos painéis à esquerda.

Depois de aninhar os valores com o [!UICONTROL Grupo lógico], clique no botão **[!UICONTROL Excluir]** no contêiner do [!UICONTROL Grupo lógico].

![](assets/logic_exclude_or.png)

## Criar segmentos de tempo em e tempo após

Use os operadores [!UICONTROL Within] e [!UICONTROL After] integrados no cabeçalho de cada contêiner para definir o tempo, eventos e contagem.

![](assets/then_within_operators.png)

É possível limitar a correspondência para uma duração de tempo específica por meio dos contêineres [!UICONTROL Within] e [!UICONTROL After] e especificando uma granularidade e contagem. O operador [!UICONTROL Within] é usado para especificar um limite máximo na quantidade de tempo entre dois pontos de verificação. O operador [!UICONTROL After] é usado para especificar um limite mínimo na quantidade de tempo entre dois pontos de verificação.

>[!NOTE]
>
>Há diferenças na avaliação entre elementos com nomes semelhantes, como **Dia(s)** ou **Dia**. Para definições baseadas em tempo de Dentro e Depois, utilize as opções listadas primeiro na janela pop-up:
>
>![imagem](https://git.corp.adobe.com/storage/user/5902/files/70a875e2-0ef9-4459-8648-77c60081d64d)
>
>Para definições baseadas em dimensão de Dentro e Depois, utilize as opções no submenu *Outros Dimension*:
>
>![imagem](https://git.corp.adobe.com/storage/user/5902/files/b808eeb0-5e3f-499b-8096-c7eb0d51c57a)

### Operadores After e Within {#section_CCAF5E44719447CFA7DF8DA4192DA6F8}

A duração é especificada por uma única letra maiúscula representando a granularidade seguida por um número representando a contagem de repetição da granularidade.

**[!UICONTROL Within]** inclui o ponto de extremidade (menor do que ou igual a).

**[!UICONTROL After]** não inclui o ponto de extremidade (maior do que).

| Operadores | Descrição |
|--- |--- |
| AFTER | O operador After é usado para especificar um limite mínimo na quantidade de tempo entre dois pontos de verificação. Ao definir os valores de After, o limite de tempo começará quando o segmento for aplicado. Por exemplo, se o operador After estiver definido em um contêiner para identificar visitantes que visitaram a página A, mas não retornam para visitar a página B depois de um dia, esse dia começará quando o visitante sair da página A. Para que o visitante seja incluído no segmento, no mínimo, 1440 minutos (um dia) devem se passar após sair da página A para visualizar a página B. |
| WITHIN | O operador Within é usado para especificar um limite máximo na quantidade de tempo entre dois pontos de verificação. Por exemplo, se o operador Within estiver definido em um contêiner para identificar visitantes que visitaram a página A e retornam para visitar a página B dentro de um dia, esse dia começará quando o visitante sair da página A. Para ser incluído no segmento, o visitante terá um tempo máximo de um dia antes de abrir a página B. Para que o visitante seja incluído no segmento, a visita à página B deve ocorrer dentro de no máximo 1440 minutos (um dia) após sair da página A para visualizar a página B. |
| AFTER/WITHIN | Ao usar ambos os operadores After e Within, é importante compreender que ambos os operadores começarão e terminarão simultaneamente, não em sequência.   Por exemplo, se você construir um segmento com o contêiner definido como:<br>`After = 1 Week(s) and Within = 2 Week(s)`<br>, as condições para identificar os visitantes no segmentos serão atendidas somente entre 1 e 2 semanas. As duas condições são aplicadas a partir da primeira ocorrência da página. |

### Usar o operador After

* A definição de tempo Depois permite rastrear por ano, mês, dia, hora e minuto para corresponder às visitas.
* A definição de tempo Depois pode ser aplicada somente a um contêiner de [!UICONTROL Ocorrência], visto que essa granularidade fina é definida somente nesse nível.

**Exemplo**: os visitantes que visitaram a página A e, depois, a página B somente após 2 semanas.****

![](assets/time_between_after_operator.png)

**Crir o segmento**: esse segmento é criado ao adicionar um contêiner de [!UICONTROL Visitante] com dois contêineres de [!UICONTROL Ocorrência]. Em seguida, você pode definir o operador [!UICONTROL THEN], abrir o menu suspenso do operador [!UICONTROL AFTER] e definir o número de semanas.

![](assets/after_operator.png)

**Corresponde**

Ao determinar &quot;Após 2 semanas&quot;, se houver uma ocorrência na página A em 1° de junho de 2019 às 00:01, a próxima ocorrência na página B corresponderá contanto que seja realizada antes de 00:01 de 15 de junho de 2019 (14 dias depois).

| Ocorrência A | Ocorrência B | Correspondência |
|--- |--- |--- |
| Ocorrência **A**: 1 de junho de 2019 00:01 | **Ocorrência B**: 15 de junho de 2019 00:01 | **Corresponde**: essa restrição de tempo corresponde porque ocorre Depois de 1° de junho de 2019 (duas semanas). |
| Ocorrência **A**: 1 de junho de 2019 00:01 | Ocorrência **B**: 8 de junho de 2019 00:01 Ocorrência B: 15 de junho de 2019 00:01 | **Não corresponde**: a primeira correspondência na página B não corresponde porque está em conflito coma primeira restrição que exigia a ocorrência após duas semanas. |

### Usar o operador Within

* [!UICONTROL Within] permite rastrear por ano, mês, dia, hora e minuto para corresponder visitas.
* [!UICONTROL Within] pode ser aplicado somente a um contêiner de [!UICONTROL Ocorrência], visto que essa granularidade fina é definida somente nesse nível.

>[!TIP]
>
>Em uma cláusula &quot;dentro&quot;, entre instruções THEN, é possível adicionar, por exemplo, &quot;dentro de uma instância de palavra-chave de pesquisa&quot;, &quot;dentro de uma instância eVar 47&quot;. Isso restringe o segmento a uma instância de uma dimensão.

**Exemplo**: os visitantes que visitaram a página A e, em seguida, visitaram a página B dentro de 5 minutos.

![](assets/time_between_within_operator.png)

**Criar o segmento**: esse segmento é criado ao adicionar um contêiner de [!UICONTROL Visitante] e arrastar com dois contêineres de [!UICONTROL Ocorrência]. Em seguida, você pode definir o operador [!UICONTROL THEN] e abrir o menu suspenso do operador [!UICONTROL AFTER], além de definir o intervalo: ocorrências, visualizações de página, visitas, minutos, horas, dias, semanas, meses, semestres ou anos.

![](assets/within_operator.png)

**Corresponde**

As correspondências devem ocorrer dentro do limite de tempo. Para a expressão, se um visitante faz uma ocorrência na página A às 00:01, a próxima ocorrência à página B corresponderá se acontecer em ou antes de 00:06 (cinco minutos depois, incluindo o mesmo minuto). As ocorrências dentro do mesmo minuto também corresponderão.

### Os operadores Within e After

Use o [!UICONTROL Within] e o [!UICONTROL After] para fornecer um terminal mínimo e máximo em ambas as extremidades de um segmento.

**Exemplo**: os visitantes que visitaram a página A e, em seguida, a página B após 2 semanas, mas dentro de 1 mês.

![](assets/time_between_using_both_operators.png)

**Criar o segmento**: crie o segmento fazendo a sequência de dois contêineres de [!UICONTROL Ocorrência] em um contêiner de [!UICONTROL Visitante]. Em seguida, defina os operadores [!UICONTROL After] e [!UICONTROL Within].

![](assets/within_after_together.png)

**Corresponde**

Todos os visitantes que acessam a página A em 1° de junho de 2019 voltam depois de 15 de junho de 2019 às 00:01, mas *antes* de 1° de julho de 2019 estão incluídos no segmento. Compare com [Tempo entre exclusões](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).

Os operadores [!UICONTROL After] e [!UICONTROL Within] podem ser usados em conjunto para definir um segmento sequencial.

![](assets/time_between_within_after.png)

Esse exemplo retrata uma segunda visita para acessar a página B após duas semanas, mas dentro de um mês.
