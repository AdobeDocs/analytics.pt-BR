---
title: eVars de merchandising e métodos de descoberta de produtos
description: Um aprofundamento dos conceitos por trás das eVars de comercialização e como elas processam e alocam dados.
source-git-commit: 6f98366a58c7c249c474d9f4474faa1676cdf1ea
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 1%

---

# eVars de merchandising e métodos de descoberta de produtos

Este documento explica os conceitos por trás das eVars de comercialização, que processam e alocam dados de forma diferente das eVars padrão. Ele também explica como as eVars de merchandising estão relacionadas aos métodos de descoberta de produtos.

Embora a maioria dos sites de varejo tenha muitas maneiras de encontrar produtos, o Adobe considera que os seguintes são os métodos fundamentais para encontrar produtos que cada cliente de varejo deve rastrear no Adobe Analytics:

* Palavras-chave de pesquisa interna
* Códigos de rastreamento de campanha interna
* Categorias de merchandising/navegação
* Links de venda cruzada

Para os fins deste documento, vamos mapear algumas eVars para as soluções da seguinte maneira:

* eVar2: Palavras-chave de pesquisa interna
* eVar3: Códigos de rastreamento de campanha interna
* eVar4: Categorias de merchandising/navegação
* eVar5: Links de venda cruzada

Podemos usar um eVar adicional para medir o desempenho de todos os métodos de busca de produtos em relação uns aos outros. Além dos métodos de descoberta descritos acima, o eVar inclui outros métodos de descoberta em sua comparação, como links para páginas de detalhes do produto de sites externos.

* eVar1: Métodos para encontrar produtos

Em vez de configurar qualquer uma dessas variáveis para serem eVars padrão, configure-as para serem eVars de merchandising. Usar eVars de merchandising permite alocar qualquer atividade bem-sucedida nos valores capturados pelas eVars em um nível *por produto* em vez de um nível *por visita/por pedido*. Este documento esclarece a diferença entre a alocação por produto e por pedido em todo o processo.

Para demonstrar como definir essas variáveis, aqui está um exemplo em que um visitante decide usar as &quot;sandálias&quot; internas de pesquisa de palavra-chave para localizar um produto no site. Na página de resultados da pesquisa por palavra-chave, você deve capturar dados em pelo menos duas eVars:

* `eVar2` é igual à palavra-chave que foi usada na pesquisa (&quot;sandals&quot;)
* `eVar1` é igual ao método de descoberta de produto usado (&quot;pesquisa interna de palavra-chave&quot;).

Quando você define essas duas variáveis iguais a esses valores específicos, você sabe que o visitante está usando o termo de pesquisa interno de palavra-chave &quot;sandals&quot; para localizar um produto. Ao mesmo tempo, você sabe que o visitante não está usando os outros métodos de busca de produtos para localizar produtos (por exemplo, o visitante não está navegando pelas categorias de produtos exatamente ao mesmo tempo em que está realizando uma pesquisa de palavra-chave). Para garantir que a alocação adequada por produto ocorra, esses métodos não utilizados não devem receber crédito pela localização de um produto encontrado por meio de uma pesquisa interna por palavra-chave. Portanto, você deve inserir lógica no código (como AppMeasurement, AEP Web SDK e assim por diante) que define automaticamente as eVars associadas a esses outros métodos de descoberta como um valor de &quot;método que não seja de conclusão&quot;.

Por exemplo, quando um usuário pesquisa produtos usando a palavra-chave &quot;sandals&quot;, a lógica do código do Analytics deve definir as variáveis iguais às seguintes na página de resultados da pesquisa interna por palavra-chave:

* eVar2=&quot;sandals&quot;: a palavra-chave &quot;sandals&quot; foi usada na pesquisa interna da palavra-chave
* eVar1=&quot;pesquisa interna de palavra-chave&quot;: o método de descoberta &quot;pesquisa interna de palavra-chave&quot; foi usado
* eVar3=&quot;campanha não interna&quot;: uma campanha interna não foi usada para acessar a página de resultados da pesquisa
* eVar4=&quot;não navegado&quot;: uma categoria de navegação não foi acessada na página de resultados da pesquisa
* eVar5=&quot;venda não cruzada&quot;: um link de venda cruzada não foi clicado na página Resultados da pesquisa

## Configurações de eVars de merchandising

Antes de continuar com o exemplo de &quot;sandálias&quot;, veja as diferentes configurações que você pode usar com suas eVars de merchandising.  A seguinte captura de tela é do Gerenciador de conjunto de relatórios. Acesse-o acessando Analytics > Admin > Conjuntos de relatórios > Editar configurações > Conversão > Variáveis de conversão > Adicionar novo > Ativar merchandising.

![](assets/merch-evars1.png)

As seções abaixo da tabela contêm mais detalhes sobre essas configurações.

| Configuração | Descrição |
|--- | --- |
| Nome | O Nome ou a dimensão de relatório à qual a variável deve ser associada. Se `eVar1` for destinado a capturar os Métodos de descoberta de produto, o campo Nome para `eVar1` deverá ser definido como &quot;Métodos de descoberta de produto&quot;. |
| Merchandising | O tipo de sintaxe que será usada para capturar os valores de eVar de comercialização |
| Alocação | Ajuda a determinar o valor do eVar de merchandising que deve receber crédito quando um evento bem-sucedido ocorrer. |
| Expirar após | Determina quando os vínculos de eVar de produto e merchandising existentes não devem mais estar em vigor. |
| Tipo | O tipo de dados que está sendo coletado no eVar de comercialização |
| Evento compulsório de merchandising | Os eventos que determinam quando um produto deve ser vinculado a um valor de eVar de comercialização |
| Redefinir | Um acionador que redefinirá todos os dados de back-end do eVar nesse ponto |
| Ativar o merchandising | Um sinalizador que precisa ser definido como &quot;Ativado&quot; para transformar o eVar de um eVar padrão em um eVar de comercialização |

### Merchandising

Essa opção não está disponível para eVars comuns. A configuração [!UICONTROL Merchandising] permite selecionar [!UICONTROL Sintaxe de variável de conversão] ou [!UICONTROL Sintaxe de produto] como o método para capturar o valor do eVar de merchandising.

**[!UICONTROL A]** sintaxe da variável de conversão significa que você definiu o valor do eVar em sua própria variável. Por exemplo, com a Sintaxe de variável de conversão, o valor `eVar1` de &quot;pesquisa interna de palavra-chave&quot; é definido da seguinte maneira no código da página (ou no código AppMeasurement, código AEP Web SDK e assim por diante):

`s.eVar1="internal keyword search";`

Com **[!UICONTROL Sintaxe de produto]**, no entanto, o eVar é definido somente na variável de produtos do Adobe Analytics. A variável de produtos do Analytics é dividida em seis partes diferentes por produto:

`s.products="[category];[productID];[quantity];[revenue];[events];[eVars]"`

*  A categoria é um recurso obsoleto e não é mais recomendada como uma opção viável para rastrear o desempenho da categoria do produto.  Sua mera existência demonstra por que, na maioria das implementações da variável products , um único ponto e vírgula precede a parte productID do valor da variável.
*  Quantidade e   receita são úteis quando uma compra de produto está sendo rastreada.
*  Os eventos são úteis para registrar valores de evento de moeda ou incremental personalizados que não devem ser contados como receita (como frete, descontos etc.)

As eVars de merchandising configuradas para usar a Sintaxe de produto são definidas na parte final da variável products. Por exemplo, suponha que um visitante tenha usado uma pesquisa interna de palavra-chave para encontrar a ID de produto &quot;12345&quot;. A maneira baseada em sintaxe de produto de configurar o eVar1 neste exemplo seria semelhante a:

`s.products=";12345;;;;eVar1=internal keyword search";`

Observe que ainda temos espaços reservados delimitados por ponto e vírgula para a quantidade, receita e partes do evento da variável products.  Sem esses espaços reservados, a configuração `eVar1` da pesquisa interna de palavra-chave seria completamente ignorada.

### Alocação

O termo &quot;Alocação&quot; para eVars de comercialização é um erro, especialmente para eVars de comercialização que usam Sintaxe de variável de conversão. Todas as eVars que usam sintaxe padrão podem ter sua própria configuração de alocação individual, mas eVars de comercialização com Sintaxe de variável de conversão usam apenas uma configuração de alocação &quot;Mais recente (último)&quot;, independentemente do que as configurações de alocação no Gerenciador de conjunto de relatórios mostram.

Para entender o que essa configuração faz, é necessário entender a diferença entre a alocação de eVar e a vinculação de eVar de comercialização.  Para eVars de merchandising, &quot;Vínculo de eVar de merchandising&quot; pode ser considerado um nome mais adequado para essa configuração de &quot;Alocação&quot;.
Sempre que qualquer eVar com sintaxe padrão é coletado de uma solicitação de imagem, os servidores de processamento da Adobe Analytics inserem dados em outra coluna de banco de dados, chamada de coluna post_evar, ao lado da coluna de eVar regular.  Como as eVars devem ser persistentes (ou seja, expiram em algum ponto além da ocorrência atual na maioria dos casos), os servidores definirão essa coluna post_evar em cada solicitação de imagem subsequente e a definirão como o último valor transmitido para o eVar correspondente. Para eVars padrão (ou seja, não Merchandising), quando um evento bem-sucedido ocorre, o Adobe Analytics usa a coluna post_evar em vez da coluna de eVar regular para determinar o valor do eVar que deve receber crédito pelo evento.
Para eVars padrão (ou seja, não Merchandising), a configuração Alocação determina se o primeiro ou o último valor do eVar coletado durante um determinado período será inserido na coluna post_evar. Se a configuração Alocação de um eVar padrão for igual ao &quot;Valor original (primeiro)&quot;, o primeiro valor de eVar coletado do visitante será inserido na coluna post_evar para todas as solicitações de imagem subsequentes.  Isso continuará para todas as solicitações futuras enviadas do navegador do visitante até que o eVar expire de acordo com a configuração &quot;Expirar após&quot;.\
Se a configuração Alocação de um eVar padrão for igual a &quot;Mais recente (último)&quot;, o valor de eVar mais recente coletado do visitante será preenchido na coluna post_evar para todas as solicitações de imagem subsequentes. A alocação &quot;Mais recente (último)&quot; implica que o valor de post_evar será alterado sempre que o eVar correspondente for definido como um novo valor em qualquer solicitação de imagem.  A alocação &quot;Valor original (primeiro)&quot; implica que a coluna post_evar não será alterada entre ocorrências, mesmo que seu eVar correspondente possa ser definido com um valor diferente em uma solicitação de imagem futura.
Como mencionado anteriormente, todas as eVars de merchandising com Sintaxe de variável de conversão têm somente a alocação &quot;Mais recente (último)&quot; (de acordo com a definição de eVar padrão).  Portanto, preciso explicar o que a configuração &quot;Alocação&quot; realmente significa para eVars de merchandising.  Como sugerido anteriormente, essa configuração não determina quais valores são inseridos na coluna post_evar, pois um visitante continua a usar o site.  Em vez disso, a configuração Alocação de eVars de comercialização determina qual valor de eVar se vincula a um produto e como esses produtos são alocados


