---
description: Relaciona as métricas padrão no Adobe Analytics.
seo-description: Relaciona as métricas padrão no Adobe Analytics.
seo-title: Métricas referência rápida
solution: Analytics
title: Referência rápida das métricas
topic: Métricas
uuid: 34160 c 96-7 cb 3-4 e 2 f -9956-9 ffa 9 d 9 a 359 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Referência rápida das métricas

Relaciona as métricas padrão no Adobe Analytics.

>[!NOTE]
>
>Any metric (event) not listed below is a [custom metric](../../../components/c-variables/c-metrics/metrics-custom.md#concept_F44638FC95A44B06AEBA3A6F9D008D27) (event).

<table id="table_CF4480B640BD4C81B4B32121FED5C96A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome da métrica </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Profundidade média da página </td> 
   <td colname="col2"> Exibe em média em que ponto da visita cada valor foi disparado. Esta métrica é importante para determinar em que ponto de uma visita o público-alvo alcança uma página ou valor de prop determinado. Profundidade média da página está disponível em qualquer variável com definição de caminho ativada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tempo médio gasto na página </td> 
   <td colname="col2"> Representa o tempo médio gasto em uma página durante uma visita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tempo médio gasto no site </td> 
   <td colname="col2"> Representa o tempo médio gasto em um site durante uma visita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Taxa de rejeição </td> 
   <td colname="col2"> Mostra a porcentagem de visitas que contém uma única ocorrência. A taxa de rejeição usa a métrica de rejeições e é calculada como: Rejeições divididas pelas Entradas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Devoluções </td> 
   <td colname="col2"> Uma visita que consiste em uma chamada única de servidor. Por exemplo, uma visita de página única é uma rejeição se o visitante não interagir com a página de forma a enviar dados para a Adobe como, por exemplo, clicar em um link ou iniciar um vídeo. Se mais uma ocorrência for recebida em uma visita, uma Rejeição não é contabilizada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Click-throughs da campanha </td> 
   <td colname="col2"> Os Click-throughs representam o número de vezes que um código de rastreamento de uma campanha específica foi passado ao relatório. Quando um visitante clica em um link afiliado que foi marcado com um desses códigos de rastreamento, o visitante é levado a sua página de aterrissagem e o código de rastreamento é capturado na s.campaign. Os dados são enviados para o relatório e um click-through é registrado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Adições ao carrinho </td> 
   <td colname="col2"> O número de vezes que um item foi adicionado ao carrinho de compras. Este valor vem do evento scAdd. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Abertura do Carrinho </td> 
   <td colname="col2"> O número de vezes em que um cliente abriu um carrinho de compras adicionando o primeiro item. Ocorre na primeira vez em que um item é adicionado ao carrinho de compras. Este valor vem do evento scOpen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Remoções do carrinho </td> 
   <td colname="col2"> O número de vezes em que um item foi removido do carrinho de compras. Este valor vem do evento scRemove. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Carrinhos </td> 
   <td colname="col2"> O número de vezes em que um novo carrinho de compras foi aberto ou inicializado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Exibições do carrinho </td> 
   <td colname="col2"> O número de vezes em que o conteúdo do carrinho de compras foi visualizado pelo cliente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Finalizações </td> 
   <td colname="col2"> Um evento que ocorre quando clientes chegam ao estágio de finalização de uma compra. O estágio de finalização normalmente ocorre pouco antes da compra ser finalizada e geralmente envolve a digitação de informações pessoais por parte do cliente (como informações de transporte e faturamento). Você tem controle sobre quais eventos do site são qualificados como finalizações. Este valor vem do evento scCheckout. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Click-throughs </td> 
   <td colname="col2">Os Click-throughs representam o número de vezes que um código de rastreamento de uma campanha específica foi passado ao relatório. When a visitor clicks on an affiliate link that has been tagged with one of these tracking codes, the visitor is taken to your landing page and the tracking code is captured in <span class="varname"> s.campaign</span>. Os dados são enviados para o relatório e um click-through é registrado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cliente (Novo, Regresso, Fidelizado) </td> 
   <td colname="col2">Categorias do relatório de Fidelidade do cliente: <p>Cliente novo: cliente com 0 compras. </p> <p>Cliente recorrente: cliente com 1 compra. </p> <p>Cliente fidelizado: cliente com mais de 1 compra. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de retorno diário </td> 
   <td colname="col2"> Exibe o número de visitantes ao site mais de uma vez em um dia específico. Um dia é definido como o último período de 24 horas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entradas </td> 
   <td colname="col2"> As entradas representam o número de vezes em que determinado valor é capturado como o primeiro em uma visita. Entradas pode ocorrer somente uma vez por visita. Contudo, não é necessariamente a primeira ocorrência se a variável não estiver definida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Saídas </td> 
   <td colname="col2"> O número de vezes que um determinado valor é capturado como o último em uma visita. Saídas podem ocorrer somente uma vez por visita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Instâncias </td> 
   <td colname="col2"> O número de vezes que um valor foi definido para uma variável. As instâncias são contabilizadas por todos os tipos de ocorrência, mas não são contabilizadas quando um valor é gravado para uma variável ou uma ocorrência subsequente por motivos de persistência. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Duração </td> 
   <td colname="col2"> A quantidade total de determinada métrica de sucesso para um único usuário. Por exemplo, o número total de visitas acumuladas de um usuário. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Exibições para dispositivos móveis </td> 
   <td colname="col2"> O número de vezes que uma página é visualizada ou que uma dimensão é definida quando acessada através de um dispositivo móvel. Somente Ad Hoc Analysis. Em vez de usar a métrica de visualizações móveis, recomendamos aplicar o segmento "Visitas de dispositivos móveis". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Novas participações </td> 
   <td colname="col2"> Novas Participações é uma métrica de relatório do canal de marketing que contabiliza os novos visitantes que chegam através de um canal. Essa métrica também conta os visitantes que não visitaram o seu site nos últimos 30 dias. Uma Nova participação é uma eVar configurada no início de cada visita (alocação original). Canais de primeiro toque também podem ser Novas participações, dependendo das configurações de expiração da participação do visitante. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ocorrências </td> 
   <td colname="col2"> O número de vezes em que um valor específico é capturado, além do número de exibições de página em que o valor dado persistiu. Em outras palavras, Ocorrências são a soma das exibições de página e dos eventos da página. Ocorrências disponíveis somente em Ad Hoc Analysis. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pedidos </td> 
   <td colname="col2"> O número de pedidos feitos no site durante o intervalo selecionado. É possível analisar períodos individuais usando outras métricas para mostrar os itens (como produtos ou campanhas) que contribuíram para a maioria das ordens durante esse intervalo de tempo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profundidade da página </td> 
   <td colname="col2"> O número médio de cliques necessários para os usuários chegarem a uma página específica do site. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eventos de página </td> 
   <td colname="col2"> Os eventos de página consistem em dados de solicitação de imagem de solicitações de imagem não padrão. As fontes de solicitações de imagem não padrão são links de downloads, links de saída e rastreamento de link personalizado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Exibições de página </td> 
   <td colname="col2"> Uma Visualização de Página é contada para cada chamada de servidor que é enviada. Esta métrica representa instâncias totais de visualização de página. Chamadas TrackLink não são contadas como exibições de página e não incrementam a métrica Exibições de página. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Exibições de caminho </td> 
   <td colname="col2"> <p>A métrica de Exibições de caminho é baseada nos dados de definição de caminho, que são rastreados para todos os usuários que aceitam cookies persistentes. </p> <p>O termo Exibição de caminho é usado para indicar o número de vezes que uma página foi visualizada, dadas as restrições do(s) caminho(s) exibido(s). Esta métrica relata o número de exibições de página para uma determinada página que ocorreu dentro de um caminho selecionado. Essa métrica está disponível no relatório de Caminhos. Exibições de caminhos mostram quantas vezes uma sequência específica de páginas foi visualizada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Exibições do produto </td> 
   <td colname="col2"> Instância da Exibição de produto que está sendo definida. Ocorre quando a página de detalhes do produto é visualizada. Este valor vem do evento prodView. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recargas </td> 
   <td colname="col2"> Contado quando o mesmo nome de página é carregado duas vezes seguidas. Geralmente, isso indica que a página foi atualizada. Observe que visitar a página duas vezes no mesmo momento não conta como um recarregamento, a não ser que as duas visitas ocorram uma seguida da outra. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas de retorno </td> 
   <td colname="col2"> Mostra o número de visitas em que o número de visitas for maior que 1. As Visitas de retorno incluem visitantes sem cookies. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Receita </td> 
   <td colname="col2"> A receita é capturada no evento de compra e é definida como valor total da moeda para a soma do pedido de cada produto. Este valor provém do evento de compra. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pesquisas </td> 
   <td colname="col2"> <p>Pesquisas não é uma métrica padrão, sempre é uma métrica personalizada. </p> <p>É a métrica padrão recomendada para mecanismos de pesquisa e palavras-chave. Essa métrica representa instâncias de um click-through, e mostra a página associada a um mecanismo ou palavra-chave específico. Dados de métrica de pesquisas podem ser relatados retroativamente para o início do conjunto de dados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Acesso único </td> 
   <td colname="col2"> O Acesso único é definido pelo número de visitas ao site que continham um único valor de Nome de Página. Se um usuário chega ao site e clica em um link rastreado, dispara um evento (como uma exibição de vídeo) ou recarrega uma página, a visita ainda é considerada uma visita de Acesso único. Enquanto o valor para a variável pageName não muda, qualquer número de solicitações pode ser enviado e a visita ainda é considerada um Acesso Único. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tempo gasto </td> 
   <td colname="col2"> Métricas que relatam o tempo que cada visitante passou em uma página, em um site ou durante cada visita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total </td> 
   <td colname="col2"> As métricas totais relatam o valor de todos os itens de linha de relatório de um período de relatório. Se o filtro estiver selecionado, o total pode representar o total filtrado no lugar do total do conjunto de relatórios. Se nenhum filtro estiver selecionado, o total representa o total do conjunto de relatórios. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cliente único </td> 
   <td colname="col2"> <p>(Por hora, Diariamente, Semanalmente, Mensalmente, Trimestralmente, Anualmente) </p> <p>Um cliente único é contado uma vez neste intervalo de tempo, mas não pode ser contado novamente, independentemente de quantas vezes o visitante retorna para realizar uma compra. Um visitante único é contado uma vez pela primeira visita em um período especificado e não é contado novamente até que o período expire. Depois que o período expira, o visitante único é contado novamente. Clientes únicos são sempre contados como visitantes únicos pois devem visitar o site para realizar a compra. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes únicos </td> 
   <td colname="col2"> Mostra o número total de visitantes únicos para o período dos relatórios (pode ser configurado para diariamente, semanalmente, mensalmente, trimestralmente, anualmente). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Unidades </td> 
   <td colname="col2"> Todas as unidades pedidas para o intervalo selecionado. Como é possível adquirir várias unidades por pedido, a métrica Unidades é vital, pois exibe a movimentação geral de inventário. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitantes </td> 
   <td colname="col2"> O número de visitantes únicos do site por uma hora, dia, semana, mês, trimestre ou ano selecionado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitas </td> 
   <td colname="col2"> <p>A sequência de exibições de página em uma sessão. A métrica de visitas normalmente é usada em relatórios que exibem o número de sessões de usuário no intervalo selecionado. </p> <p>A métrica de visita é sempre associada com um período de tempo, para que você saiba quando contar uma nova visita caso o mesmo visitante retorne ao site. </p> </td> 
  </tr> 
 </tbody> 
</table>

