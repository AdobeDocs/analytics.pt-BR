---
description: Relaciona as métricas padrão no Adobe Analytics.
title: Referência rápida das métricas
topic: Metrics
uuid: 34160c96-7cb3-4e2f-9956-9ffa9d9a359e
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Referência rápida das métricas

Relaciona as métricas padrão no Adobe Analytics.

>[!NOTE]
>
>Qualquer métrica (evento) não listada abaixo é uma [métrica personalizada](/help/components/c-variables/c-metrics/metrics-custom.md) (evento personalizado).

>[!IMPORTANT]
>
>A Analysis Workspace não diferencia mais entre métricas de Tráfego e Conversão. Portanto, o tipo de métrica é relevante somente para ferramentas como Reports &amp; Analytics, Serviços da Web 1.4 e Report Builder.)

| Nome da métrica | Descrição | Tipo |
|--- |--- |---|
| Profundidade média da página | Exibe em média em que ponto da visita cada valor foi disparado. Esta métrica é importante para determinar em que ponto de uma visita o público-alvo alcança uma página ou valor de prop determinado. Profundidade média da página está disponível em qualquer variável com definição de caminho ativada. | Tráfego |
| Tempo médio gasto na página | Representa o tempo médio gasto em uma página durante uma visita. | Tráfego |
| Tempo médio gasto no site | Representa o tempo médio gasto em um site durante uma visita. | Tráfego |
| Taxa de rejeição | Mostra a porcentagem de visitas que contém uma única ocorrência. A taxa de rejeição usa a métrica de rejeições e é calculada como: Rejeições divididas pelas Entradas. | Conversão |
| Devoluções | Uma visita que consiste em uma chamada única de servidor. Por exemplo, uma visita de página única é uma rejeição se o visitante não interagir com a página de forma a enviar dados para a Adobe como, por exemplo, clicar em um link ou iniciar um vídeo. Se mais de uma ocorrência for recebida em uma visita, uma Rejeição não é contabilizada. | Conversão |
| Click-throughs da campanha | Os Click-throughs representam o número de vezes que um código de rastreamento de uma campanha específica foi passado ao relatório. Quando um visitante clica em um link afiliado que foi marcado com um desses códigos de rastreamento, o visitante é levado a sua página de aterrissagem e o código de rastreamento é capturado na s.campaign. Os dados são enviados para o relatório e um click-through é registrado. | Conversão |
| Adições ao carrinho | O número de vezes que um item foi adicionado ao carrinho de compras. Este valor vem do evento scAdd. | Conversão |
| Abertura do Carrinho | O número de vezes em que um cliente abriu um carrinho de compras adicionando o primeiro item. Ocorre na primeira vez em que um item é adicionado ao carrinho de compras. Este valor vem do evento scOpen. | Conversão |
| Remoções do carrinho | O número de vezes em que um item foi removido do carrinho de compras. Este valor vem do evento scRemove. | Conversão |
| Carrinhos | O número de vezes em que um novo carrinho de compras foi aberto ou inicializado. | Conversão |
| Exibições do carrinho | O número de vezes em que o conteúdo do carrinho de compras foi visualizado pelo cliente. | Conversão |
| Finalizações | Um evento que ocorre quando clientes chegam ao estágio de finalização de uma compra. O estágio de finalização normalmente ocorre pouco antes da compra ser finalizada e geralmente envolve a digitação de informações pessoais por parte do cliente (como informações de transporte e faturamento). Você tem controle sobre quais eventos do site são qualificados como finalizações. Este valor vem do evento scCheckout. | Conversão |
| Click-throughs | Os Click-throughs representam o número de vezes que um código de rastreamento de uma campanha específica foi passado ao relatório. Quando um visitante clica em um link afiliado que foi marcado com um desses códigos de rastreamento, o visitante é levado a sua página de aterrissagem e o código de rastreamento é capturado na s.campaign. Os dados são enviados para o relatório e um click-through é registrado. | Conversão |
| Cliente (Novo, Regresso, Fidelizado) | Categorias do relatório de Fidelidade do cliente:  Cliente novo: cliente com 0 compras.  Cliente recorrente: cliente com 1 compra.  Cliente fidelizado: cliente com mais de 1 compra. | Tráfego |
| Visitas de Retorno Diário | Exibe o número de visitantes ao site mais de uma vez em um dia específico. Um dia é definido como o último período de 24 horas. | Tráfego |
| Entradas | As entradas representam o número de vezes em que determinado valor é capturado como o primeiro em uma visita. Entradas pode ocorrer somente uma vez por visita. Contudo, não é necessariamente a primeira ocorrência se a variável não estiver definida. | Tráfego |
| Saídas | O número de vezes que um determinado valor é capturado como o último em uma visita. Saídas podem ocorrer somente uma vez por visita. | Tráfego |
| Instâncias | O número de vezes que um valor foi definido para uma variável. As instâncias são contabilizadas por todos os tipos de ocorrência, mas não são contabilizadas quando um valor é gravado para uma variável ou uma ocorrência subsequente por motivos de persistência. | Conversão |
| Exibições para dispositivos móveis | O número de vezes que uma página é visualizada ou que uma dimensão é definida quando acessada através de um dispositivo móvel. Somente Ad Hoc Analysis. Em vez de usar a métrica de visualizações móveis, recomendamos aplicar o segmento &quot;Visitas de dispositivos móveis&quot;. | Conversão |
| Novas participações | Novas Participações é uma métrica de relatório do canal de marketing que contabiliza os novos visitantes que chegam através de um canal. Essa métrica também conta os visitantes que não visitaram o seu site nos últimos 30 dias. Uma Nova participação é uma eVar configurada no início de cada visita (alocação original). Canais de primeiro toque também podem ser Novas participações, dependendo das configurações de expiração da participação do visitante. | Conversão |
| Ocorrências | O número de vezes em que um valor específico é capturado, além do número de exibições de página em que o valor dado persistiu. Em outras palavras, Ocorrências são a soma das exibições de página e dos eventos da página. Ocorrências disponíveis somente em Ad Hoc Analysis. | Não disponível em Reports &amp; Analytics, Serviços da Web 1.4 ou Report Builder |
| Pedidos | O número de pedidos feitos no site durante o intervalo selecionado. É possível analisar períodos individuais usando outras métricas para mostrar os itens (como produtos ou campanhas) que contribuíram para a maioria das ordens durante esse intervalo de tempo. | Conversão |
| Profundidade da página | O número médio de cliques necessários para os usuários chegarem a uma página específica do site. | Tráfego |
| Eventos de página | Os eventos de página consistem em dados de solicitação de imagem de solicitações de imagem não padrão. As fontes de solicitações de imagem não padrão são links de downloads, links de saída e rastreamento de link personalizado. | Tráfego |
| Exibições de página | Uma Visualização de Página é contada para cada chamada de servidor que é enviada. Esta métrica representa instâncias totais de visualização de página. Chamadas TrackLink não são contadas como exibições de página e não incrementam a métrica Exibições de página. | Conversão |
| Exibições de caminho | A métrica de Exibições de caminho é baseada nos dados de definição de caminho, que são rastreados para todos os usuários que aceitam cookies persistentes.  O termo Exibição de caminho é usado para indicar o número de vezes que uma página foi visualizada, dadas as restrições do(s) caminho(s) exibido(s). Esta métrica relata o número de exibições de página para uma determinada página que ocorreu dentro de um caminho selecionado. Essa métrica está disponível no relatório de Caminhos. Exibições de caminhos mostram quantas vezes uma sequência específica de páginas foi visualizada. | Tráfego |
| Exibições do produto | Instância da Exibição de produto que está sendo definida. Ocorre quando a página de detalhes do produto é visualizada. Este valor vem do evento prodView. | Conversão |
| Recargas | Contado quando o mesmo nome de página é carregado duas vezes seguidas. Geralmente, isso indica que a página foi atualizada. Observe que visitar a página duas vezes no mesmo momento não conta como um recarregamento, a não ser que as duas visitas ocorram uma seguida da outra. | Tráfego |
| Visitas de Retorno | Mostra o número de visitas em que o número de visitas for maior que 1. As Visitas de retorno incluem visitantes sem cookies. | Conversão |
| Receita | A receita é capturada no evento de compra e é definida como valor total da moeda para a soma do pedido de cada produto. Este valor provém do evento de compra. | Conversão |
| Pesquisas | Pesquisas não é uma métrica padrão, sempre é uma métrica personalizada.  É a métrica padrão recomendada para mecanismos de pesquisa e palavras-chave. Essa métrica representa instâncias de um click-through, e mostra a página associada a um mecanismo ou palavra-chave específico. Dados de métrica de pesquisas podem ser relatados retroativamente para o início do conjunto de dados. | Conversão |
| Único Acesso | O Acesso único é definido pelo número de visitas ao site que continham um único valor de Nome de Página. Se um usuário chega ao site e clica em um link rastreado, dispara um evento (como uma exibição de vídeo) ou recarrega uma página, a visita ainda é considerada uma visita de Acesso único. Enquanto o valor para a variável pageName não muda, qualquer número de solicitações pode ser enviado e a visita ainda é considerada um Acesso Único. | Tráfego |
| Tempo gasto | Métricas que relatam o tempo que cada visitante passou em uma página, em um site ou durante cada visita. | Tráfego |
| Total | As métricas totais relatam o valor de todos os itens de linha de relatório de um período de relatório. Se o filtro estiver selecionado, o total pode representar o total filtrado no lugar do total do conjunto de relatórios. Se nenhum filtro estiver selecionado, o total representa o total do conjunto de relatórios. | A versão Total de uma métrica segue o tipo da métrica base. Por exemplo, `totalpageviews` seria Tráfego porque `pageviews` é Tráfego. |
| Cliente único | (Por hora, Diariamente, Semanalmente, Mensalmente, Trimestralmente, Anualmente)  Um cliente único é contado uma vez neste intervalo de tempo, mas não pode ser contado novamente, independentemente de quantas vezes o visitante retorna para realizar uma compra. Um visitante único é contado uma vez pela primeira visita em um período especificado e não é contado novamente até que o período expire. Depois que o período expira, o visitante único é contado novamente. Clientes únicos são sempre contados como visitantes únicos pois devem visitar o site para realizar a compra. | Conversão |
| Visitantes únicos | Mostra o número total de visitantes únicos para o período dos relatórios (pode ser configurado para diariamente, semanalmente, mensalmente, trimestralmente, anualmente). | Conversão |
| Unidades | Todas as unidades pedidas para o intervalo selecionado. Como é possível adquirir várias unidades por pedido, a métrica Unidades é vital, pois exibe a movimentação geral de inventário. | Conversão |
| Visitantes | O número de visitantes únicos do site por uma hora, dia, semana, mês, trimestre ou ano selecionado. | Conversão |
| Visitas | A sequência de exibições de página em uma sessão. A métrica de visitas normalmente é usada em relatórios que exibem o número de sessões de usuário no intervalo selecionado.  A métrica de visita é sempre associada com um período de tempo, para que você saiba quando contar uma nova visita caso o mesmo visitante retorne ao site. | Conversão |

