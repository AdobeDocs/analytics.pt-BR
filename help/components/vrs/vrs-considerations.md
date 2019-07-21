---
description: Os conjuntos de relatórios virtuais podem ser usados para substituir tags de múltiplos conjuntos. Por exemplo, em vez de enviar dados para dois conjuntos de relatórios diferentes, você pode enviar dados para um ou usá-los para limitar a quantidade de dados que os usuários podem acessar. Entretanto, o acesso aos dados é apenas um dos benefícios dos conjuntos de relatórios separados. Considere cuidadosamente os seguintes casos de uso antes de fazer alterações de implementação nos conjuntos de relatórios virtuais.
keywords: Conjunto de relatórios virtuais
seo-description: Os conjuntos de relatórios virtuais podem ser usados para substituir tags de múltiplos conjuntos. Por exemplo, em vez de enviar dados para dois conjuntos de relatórios diferentes, você pode enviar dados para um ou usá-los para limitar a quantidade de dados que os usuários podem acessar. Entretanto, o acesso aos dados é apenas um dos benefícios dos conjuntos de relatórios separados. Considere cuidadosamente os seguintes casos de uso antes de fazer alterações de implementação nos conjuntos de relatórios virtuais.
seo-title: Considerações de marcação de vrss e global/multiconjunto
solution: Analytics
title: Considerações de marcação de vrss e global/multiconjunto
topic: Reports and Analytics
uuid: f 17 d 3659-a 5 b 1-4807-a 01 d-a 1 b 422009 a 64
translation-type: tm+mt
source-git-commit: 800d4ed34a816bd331b339295dc3acd2a03a2cd5

---


# Considerações de marcação de vrss e global/multiconjunto

Os Conjuntos de relatórios virtuais (VRS) permitem exibir dados de um conjunto de relatórios que está coletando dados de suas propriedades digitais, mas com um segmento aplicado permanentemente.

Como eles funcionam como conjuntos de relatórios e podem ser atribuídos a grupos de usuários da mesma forma que os conjuntos de relatórios, osVRS podem, em alguns casos, ser usados para substituir a marcação de multiconjunto e remover [chamadas de servidor secundário](/help/admin/c-server-call-usage/overage-overview.md). (A marcação de vários relatórios é definida como a capacidade de enviar dados para vários conjuntos de relatórios usando uma única solicitação de imagem.) Por exemplo, em vez de enviar dados de duas marcas para dois conjuntos de relatórios "secundários" separados mais um conjunto de relatórios "global" em que os dados entre marcas são trazidos juntos, é possível enviar dados de duas marcas somente para o conjunto de relatórios global. Dessa forma, você usaria os VRS para limitar o acesso do usuário aos dados (por marca) ao replicar os conjuntos de relatórios secundários.

Substituir a marcação de multiconjunto pelo conjunto de relatórios global e os VRS permite simplificar sua implementação do Adobe Analytics e reduzir o consumo de chamada do servidor, o que geralmente é recomendado. No entanto, há algumas limitações importantes dos VRS que você deveria levar em consideração ao decidir se usa a marcação de multiconjunto ou um único conjunto de relatórios global mais os VRS. As orientações a seguir podem ajudá-lo a decidir se a melhor opção para você é implementar os conjuntos de relatórios virtuais integrados em um conjunto de relatórios global.

## Diretrizes

>[!NOTE]
>
> As considerações a seguir aplicam-se SOMENTE a estes casos:
>
>* Você está considerando alterar a implementação para remover conjuntos de relatórios secundários e depender exclusivamente de conjuntos de relatórios virtuais &gt; conjuntos de relatórios para controlar visualizações em dados para usuários finais, ou
>* Os usuários do Adobe Analytics em sua empresa vão recorrer aos conjuntos de relatórios virtuais como a primeira exibição dos dados.


Se não tiver certeza se os casos de uso descritos se aplicam a você e a sua empresa, consulte outros administradores do Adobe Analytics ou sua equipe da conta da Adobe. Eles podem ajudar a avaliar suas necessidades corporativas e recomendar a melhor opção.

Usar conjuntos de relatórios virtuais para substituir a marcação de multiconjunto é recomendado se:

## Publicar segmentos do Adobe Analytics para o resto da Adobe Experience Cloud é necessário somente no nível de conjunto de relatórios global e todos os usuários que publicam segmentos tiverem acesso ao conjunto de relatórios global.

Resumo:

* O compartilhamento de segmentos na Adobe Experience Cloud não é suportado para os conjuntos de relatórios virtuais.
* Os usuários que precisam compartilhar um segmento na Experience Cloud devem ter acesso a um conjunto de relatórios (principal ou secundário).

No momento, os segmentos não podem ser publicados na Adobe Experience Cloud a partir de um conjunto de relatórios virtual para personalização e marcação. Todos os usuários que publicam segmentos precisam acessar um conjunto de relatórios verdadeiro para este propósito. Uma abordagem de marcação de multiconjunto cria conjuntos de relatórios secundários em um nível de marca, propriedade, região etc. que permite que os usuários que não têm acesso ao conjunto de relatórios virtuais publiquem segmentos somente no conjunto de dados disponibilizado para eles no conjunto de relatórios secundário.

Por exemplo, seus usuários podem ter acesso somente a conjuntos de relatórios virtuais de suas regiões geográficas, mas você quer que eles consigam criar e compartilhar segmentos a partir do Adobe Analytics na Adobe Experience Cloud para direcionamento no Adobe Target. Neste caso, esses usuários não conseguiriam publicar segmentos, e você deve pensar em usar a marcação de multiconjunto para garantir que os usuários possam publicar segmentos.

## Você não precisa de relatórios em tempo real (ou “Dados atuais”) no nível do Conjunto de relatórios virtuais.

Resumo:

* Os relatórios em tempo real não são suportados nos conjuntos de relatórios virtuais, pois os dados são segmentados.
* "Dados atuais" não é compatível com os conjuntos de relatórios virtuais, pois eles não suportam segmentação.

[Os relatórios em tempo real](/help/admin/admin/realtime/t-realtime-admin.md) e ["Dados atuais"](../../technotes/latency.md) não estão disponíveis em conjuntos de relatórios virtuais. Esses recursos do Reports &amp; Analytics fornecem acesso a tipos limitados de dados de forma acelerada, dentro de segundos ou minutos. Uma das limitações dessas exibições é que elas não oferecem suporte à segmentação; em outras palavras, os dados em tempo real do Reports &amp; Analytics não podem ser segmentados. Como um conjunto de relatórios virtual é integrado usando a segmentação, é incompatível com os relatórios em tempo real. Isso afeta os usuários que respondem a tendências vistas no Adobe Analytics dentro de segundos ou alguns minutos da coleta de dados, como editores em uma redação que ajustam manchetes com base no consumo de conteúdo em tempo real. Nesse caso, você deve:

* Considerar usar a marcação de multiconjunto para garantir que cada usuário veja somente os dados em tempo real que eles tenham permissão para ver, ou
* Conceder a esses usuários acesso a um conjunto de relatórios verdadeiro (global) caso eles devessem ter acesso a todo o seu conjunto de dados.

## Você não excede os limites de valor exclusivo para dimensões principais nos conjuntos de relatórios globais, ou não se importa que os seus usuários vejam "Tráfego baixo " nos conjuntos de relatórios virtuais deles.

Resumo:

* Os conjuntos de relatórios virtuais não têm seus próprios limites de valor exclusivo para dimensões, e os herdam do conjunto de relatórios principal.
* Se os usuários do Adobe Analytics precisarem de acesso a cada valor de uma dimensão que recebe com frequência mais de 500.000 valores exclusivos por mês, considere dar continuidade à marcação de multiconjunto.

No caso de alta cardinalidade (grandes números de valores exclusivos em uma determinada dimensão, como SKUs de produto ou Páginas), os buckets do Adobe Analytics raramente encontraram valores cada mês em um item de linha de “Tráfego baixo" agregado dentro de qualquer dimensão em um conjunto de relatórios. Os valores incluídos no bucket “Tráfego baixo" não podem ser segmentados. Isso permite que as consultas do Adobe Analytics retornem rapidamente, enquanto foca nos primeiros 500.000 itens de linha vistos com mais frequência para a dimensão nas propriedades digitais. (Por exemplo, isso pode ser os 500.000 principais nomes de página.) Leia mais sobre os limites de valor exclusivo [aqui](../../technotes/low-traffic.md).

Os conjuntos de relatórios virtuais não possuem seu próprio conjunto de 500.000 valores exclusivos por dimensão mensal. Se o conjunto de relatórios no qual o VRS é baseado tiver excedido 500.000 valores exclusivos de uma determinada dimensão, e tiver começado a combinar valores de frequência baixa no item de linha “Tráfego baixo' para essa dimensão, você também poderá ver “Tráfego baixo” no conjunto de relatórios virtual.

**Exemplo**: um conectores de mídia é proprietário de properties 00 propriedades da Web. Cada propriedade publica alguns milhares de novos arquivos mensalmente, em adição à hospedagem de todos os artigos de meses anteriores, e todas as propriedades são combinadas em um conjunto de relatórios lobal. Na dimensão 'Nome do artigo', no conjunto de relatórios global, suponha que há 4 milhões de nomes de artigo exclusivo cada mês, das diversas propriedades. Os 500.000 valores principais que compreende a massa do tráfego são mostrados e podem ser segmentado, mas os 3,5 milhões de valores restantes são classificados no item de linhas "Tráfego baixo".

Neste caso, você poderia criar 100 conjuntos de relatórios virtuais para as equipes que trabalham nas propriedades individuais. Embora isso seja aceitável, considere que na dimensão 'Nome do artigo' em cada conjunto de relatórios virtual, os valores exibidos como itens de linha distintos são somente aqueles dos 500.000 principais no conjunto de relatórios global da determinada propriedade. Os conjuntos de relatórios virtuais não possuem sua própria alocação de 500.000 valores exclusivos por dimensão. Os valores acumulados no item "Tráfego baixo" no conjunto de relatórios virtual não serão mostrados individualmente no VRS. Isso pode gerar uma confusão entre os usuários que esperam ver um conjunto completo de valores de dimensão em um conjunto de relatórios virtual e, em vez disso, acabam vendo somente os valores de tráfego alto.

Se você saber que excede os limites de valor exclusivo com frequência em seu conjunto de relatórios global ou nos conjuntos de relatórios secundários, considere se os usuários precisam de acesso a esses valores vistos raramente antes de migrar para os conjuntos de relatórios virtuais. Caso os usuários precisem de acesso a cada valor exclusivo em uma dimensão que excede os limites de valor exclusivo com frequência em seu conjunto de relatórios global, considere dar continuidade ao uso da marcação de multiconjunto para fornecer esse acesso.

Além disso, observe que o Atendimento ao cliente pode aumentar os limites de valor exclusivo de um conjunto de relatórios global de forma restrita para um pequeno número de dimensões, o que pode sanar esse problema. Consulte sua equipe de conta e o Atendimento ao cliente para obter mais informações.

## É possível usar o conjunto disponível de dimensões personalizadas (eVars e propriedades) e métricas (eventos) no conjunto de relatórios global para rastrear todos os pontos de dados críticos em todas as propriedades.

Resumo:

* Os conjuntos de relatórios virtuais não possuem seus próprios conjuntos de dimensões e métricas; eles os herdam do conjunto de relatórios principal.
* Sendo assim, o conjunto de relatórios principal deve poder capturar todas as dimensões e métricas relevantes de cada propriedade que é combinada nele usando somente as dimensões personalizadas e métricas disponíveis para o conjunto de relatórios global (325 e 1000, respectivamente).

Uma vantagem atual da marcação de muticonjunto é que você pode permitir que diferentes propriedades, marcas, regiões etc. captures diferentes tipos de dados. Por exemplo, uma unidade de negócios pode usar o eVar76 para capturar 'Palavras-chave de pesquisa interna', enquanto que outra unidade pode usar o mesmo eVar para capturar o 'Nome de vídeo'. Os grupos são livres para implementar o Adobe Analytics de acordo com suas necessidades.

Com o conjunto de relatórios global, todas as propriedades devem transmitir os mesmos pontos de dados na mesma dimensão e métricas. No exemplo anterior, essas duas marcas precisariam alinhas no eVar76 usado para 'Palavra-chave de pesquisa interna' ou 'Nome do vídeo' e, então colocar o outro ponto de dados em uma dimensão diferente nas respectivas implementações. A falha dessa ação levará à corrupção de dimensões e/ou métricas no conjunto de relatórios global. Isso tende a ser um problema em situações em que várias propriedades, marcas, regiões etc. que você suporta (com conjuntos de relatórios individuais) usam todo o contingete de dimensões personalizadas ou métricas disponível. Como consequência, elas não poderiam acomodar a reserva de algumas dimensões ou métricas para as necessidades de rastreamento de outras propriedades, marcas, regiões etc.

O número máximo de dimensões personalizadas do Adobe Analytics por relatório é 325, o o número máximo de eventos personalizados por conjuntos de relatórios é 1000. Sendo assim, mover para um conjunto de relatórios global requer que todos os pontos de dados críticos em todas as propriedades digitais possam ser rastreados usando as mesmas 325 dimensões personalizadas e 1000 eventos personalizados.

Se estiver nessa situação e está pensando em mover para um conjunto de relatórios global com VRS, consulte as várias implementações do Adobe Analytics em sua empresa para acessar a quantidade de sobreposições/dissonâncias nessas implementações, e para ver quais dimensões ou métricas não são fundamentais para o sucesso dos negócios. Também considere usar [classificações](/help/components/c-classifications2/c-classifications.md) no conjunto global para relatar valores que podem estar usando suas próprias dimensões no momento. As classificações são disponibilizadas automaticamente em qualquer VRS baseado nesse conjunto global. Por exemplo, em vez de capturar 'Nome do produto' no eVar5, crie uma classificação 'Nome do produto' baseada na dimensão 'Produto'.

Se não for viável consolidar essas dimensões e eventos personalizados, a Adobe recomenda continuar a usar a marcação de multiconjunto.

>[!IMPORTANT]
>
>With the introduction of [virtual report suite curation](/help/analyze/analysis-workspace/curate-share/curate-projects-vrs.md), you can now change the name of a given dimension or &gt;metric on a per-VRS basis. Se você segmentar o conjunto de relatórios virtuais, isso significa que agora você pode usar o mesmo evar, prop ou evento para capturar coisas diferentes em conjuntos de relatórios virtuais diferentes. No entanto, passar dois &gt; diferentes tipos de dados para a mesma dimensão ou métrica tornará esse ponto de dados praticamente inutilizável no conjunto de relatórios global. Também pode causar problemas com a atribuição, como neste exemplo: se um usuário receber dois &gt; valores para evar 10, uma que é uma «Campanha interna» na propriedade A e a outra que é um «Nome da página» em &gt; propriedade B, isso significa que o sucesso agora é dividido em «Campanha interna» e «Nome da página», que deve operar em níveis diferentes. Portanto, a Adobe geralmente não recomenda usar a sequência de VRS como solução &gt; para esse problema específico.

## Os segmentos que você usará com os Conjuntos de relatórios virtuais não dividem os dados de maneiras que podem confundir os usuários.

Resumo:

* Segmentar dados de um conjunto de relatórios global em conjuntos de relatório virtuais pode criar resultados diferentes, que podem confundir alguns usuários.
* Leve em consideração como seus segmentos em conjuntos de relatórios virtuais podem afetar dimensões e recursos como página de entrada, domínio de referência, caminho etc.

Lembre-se de que um conjunto de relatórios virtuais é apenas um segmento aplicado a um conjunto de relatórios; todas as nuances nos dados segmentados se aplicam a conjuntos de relatórios virtuais. Os segmentos (e os conjuntos de relatórios virtuais) podem ser usados para dividir os dados de forma que pareçam não intuitivos para seus usuários do Adobe Analytics.

Por exemplo, suponha que você tem duas marcas, A e B, cujas propriedades digitais estão enviando dados para um conjunto de relatórios global. Alguns usuários atravessarão do site A para o B e vice-versa, e esse movimento é visível no caminho do conjunto de relatórios global. No entanto, se você integrar conjuntos de relatórios virtuais para as marcas A e B, os usuários que acessam o conjunto de relatórios virtual B poderão ver resultados não intuitivos de determinadas dimensões e métricas. Uma visita iniciada na marca A e finalizada na marca B não mostrará a página de entrada no conjunto de relatórios virtual B, pois a página de entrada da visita entre sites iniciou na marca A, que não consta na segmentação deste conjunto de relatórios virtual.

Um exemplo semelhante lida com o 'Número de visitas'. No conjunto de relatórios virtual da marca B, os usuários podem ver alguns visitantes que parecem ter uma segunda, terceira e quarta visita, mas nenhuma "primeira visita". Isso ocorreria quando a primeira visita do cliente for na marca A, e todas as visitas subsequentes na marca B. Como os dados da marca A não são incluídos no conjunto de relatórios virtual, todas as informações sobre a primeira visita (incluindo o fato de que aconteceu) não são incluídas nesse conjunto de relatórios virtual.

A Adobe recomenda usar a marcação de multiconjunto nesses cenários ou em outras situações em que parte de uma jornada do cliente pode ocorrer fora de um conjunto de relatórios virtual, de forma que possa confundir os usuários. A marcação de multiconjunto permite rastrear uma jornada em um nível entre propriedades em um conjunto de relatórios global, mas também fornece equipes individuais com sua própria exibição completa da jornada em um nível de propriedade individual.

## Você e seus usuários não precisam conseguir exibir as transações em várias moedas internacionais.

Resumo:

* Atualmente, os conjuntos de relatórios virtuais não conseguem relatar em uma moeda diferente do conjunto de relatórios na qual eles são baseados.
* O Adobe Analytics permite a conversão monetária ao executar relatórios, mas a taxa de câmbio tem por base o dia atual, mesmo para dados históricos.

Atualmente, os conjuntos de relatórios virtuais não conseguem relatar em uma moeda diferente do conjunto de relatórios na qual eles são baseados. Se sua empresa e seus usuários do Adobe Analytics fizerem a análise em uma única moeda, isso não causará problemas para você. Contudo, se você tiver uma necessidade de negócios significativa para diferentes equipes regionais que precisam conseguir exibir receitas e métricas similares em suas moedas locais (convertida com base na taxa de intercâmbio no momento da coleta de dados), você deve usar a marcação de multiconjunto.

Isso permite enviar dados para o Adobe Analytics em diversas moedas ao mesmo tempo. Com a marcação de multiconjunto, uma transação que ocorre na versão em japonês do aplicativo poderia ser gravada no conjunto global em USD. Ela pode ser convertida de JPY na taxa de intercâmbio do dia específico, mas continua a ser mostrada no conjunto de relatórios em japonês em JPY.

>[!NOTE]
>
>Embora os conjuntos de relatórios virtuais não permitem converter os dados de receita em outra moeda em uma taxa histórica, você ainda pode converter moeda em um conjunto de relatórios virtuais com base em ad hoc. Você pode aplicar a taxa de câmbio do dia atual &gt; a taxa de câmbio para os dados históricos, acessando Componentes &gt; Configurações de relatório.

## É possível usar um Feed de dados único para receber todos os seus dados de um conjunto de relatórios global.

Resumo:

* Os Feeds de dados só podem ser criados com base em conjuntos de relatórios verdadeiros, não em conjuntos de relatórios virtuais.
* No entanto, você pode receber um Feed de dados de um conjunto de relatórios global e detalhar por marca, propriedade, região etc.

Os Feeds de dados permitem que você receba uma exportação diária ou a cada hora de todos os dados do Adobe Analytics em um nível de "evento" ou "ocorrência". Como os Feeds de dados não podem ser pré-segmentados antes de serem entregues a você, usar um conjunto de relatórios global com conjuntos de relatórios virtuais significa que você só pode receber um Feed de dados do conjunto de relatórios global. Não é possível configurar os Feeds de dados para conjuntos de relatórios virtuais.

Contudo, é possível configurar quantos Feeds de dados baseados em conjuntos de relatórios verdadeiros desejar. Após receber esses Feeds de dados, é possível segmentar e dividi-los em qualquer configuração útil. Por exemplo, após receber um Feed de dados de um conjunto de relatórios global, você poderia carregara partes desse feed que pertence ao seu site em um data warehouse. É possível carregar simultaneamente a porção que pertence ao seu aplicativo móvel em um data warehouse diferente.

Observe, no entanto, que alguns campos pré calculados no Feed de dados podem precisar ser recalculados após a receita. Consulte o tem 5 (acima) para obter exemplos de campos que podem precisar ser recalculados ao filtrar um Feed e dados om base em alguns critérios.

Se sua empresa tiver uma grande necessidade por Feeds de dados individuais em um nível de marca, propriedade, região etc. , você pode considerar usar a marcação de multiconjunto.

## Você não usa uma integração do Exchange (conectores de dados) que permite somente uma conta de parceiro por conjunto de relatórios e não tem várias contas de parceiros que deseja integrar.

Resumo:

* Certas integrações de parceiros da Adobe no Adobe Analytics são limitadas a uma conta de parceiro por conjunto de relatórios.
* Algumas organizações podem querer usar várias contas de parceiros no Adobe Analytics, o que requer a marcação de multiconjunto.

O Adobe Exchange permite integrar outras soluções de marketing e tecnologia de anúncio ao Adobe Analytics. Os exemplos de integrações disponíveis incluem anuncio de exibição, email, VOC e call center. Devido às variações em como os dados são coletados, apresentados e integrados, alguns parceiros da Adobe que você pode optar por usar com o Adobe Exchange possuem uma limitação de uma instância da integração por conjunto de relatórios. Cada instância é mapeada a uma conta com o parceiro.

Um exemplo é o Google DCM. Muitas empresas possuem várias contas DCM, o que permite que diferentes marcas, unidades de negócios, regiões etc. gerenciem os anúncios de exibição separados uns dos outros. Contudo, ao integrar o DCM ao Adobe Analytics, só é possível usar uma conta DCM por conjunto de relatórios. Não é possível integrar cada uma das várias contas DCM no mesmo conjunto. Além disso, não é possível configurar uma integração diretamente em um conjunto de relatórios virtual.

Como resultado, a marcação de multiconjunto é a abordagem preferida se diferentes equipes na empresa precisarem ter seus próprios dados de conta no Adobe Analytics para um parceiro do Adobe Exchange Se estiver usando (ou usará) quaisquer integrações do Adobe Exchange em que diferentes grupos gerenciam contas distintas, verifique com o parceiro da Adobe para saber se é permitido várias contas por conjunto de relatórios.

>[!NOTE]
>
>O termo "conta" pode significar coisas diferentes para fornecedores diferentes. No contexto da tecnologia de marketing, ele normalmente não se refere a uma conta de usuário individual, mas sim a um conjunto de serviços disponibilizado para uma equipe &gt; toda a equipe ou organização. Assim, enquanto você pode ter vários nomes de usuário fazendo logon no serviço de um parceiro da Adobe, todos esses nomes de usuário podem pertencer à mesma conta.

>[!NOTE]
>
>As métricas «pré-click» (resumidas/agregadas) que são importadas de um parceiro do Adobe Exchange não estão disponíveis para segmentação e, portanto, podem não estar visíveis em um conjunto de relatórios virtuais. Exemplos dessas métricas &gt; incluem emails enviados ou impressões de anúncios, ambos ocorrem fora do site/fora do aplicativo e são importados para Adobe &gt; Analytics em um formulário agregado.

## Você não depende de Fontes de dados de resumo em sua propriedade, marca, região etc. nível.

Resumo:

* As 'Fontes de dados de resumo' permitem importar métricas agregadas para o Adobe Analytics a um nível de conjunto de relatórios.
* Mover para um conjunto de relatórios global com conjuntos de relatórios virtuais necessitaria que todos os uploads das 'Fontes de dados de resumo' ocorressem no conjunto de relatórios global.

As 'Fontes de dados de resumo' permitem importar métricas pré-agregadas em um conjunto de relatórios real no Adobe Analytics. Os exemplos de 'Fontes de dados de resumo' incluem métricas como 'Receita offline' ou 'Exibições de página' que ocorreram em outra solução anterior à implementação do Adobe Analytics. Como os uploads das Fontes de dados de resumo contêm métricas agregadas, eles não podem ser segmentados. Consequentemente, eles não aparecem segmentados em conjuntos de relatórios virtuais.

A marcação de multiconjunto fornece a sua organização a capacidade de importar métricas agregadas em um nível de conjunto de relatórios individual. Se a Marca A quiser importar a receita offline, ela pode fazer isso separada da Marca B, e seus dados serão exibidos no conjunto de relatórios da Marca A. A Marca B poderia fazer o mesmo. Se sua organização usa ou planeja usar Fontes de dados de resumo a um nível de propriedade, marca, região etc., considere usar a marcação de multiconjunto em vez de conjuntos de relatórios virtuais.

## Etapas a serem seguidas se tiver decidido usar o VRS

Após ter lido atentamente todas as considerações acima, decidido remover as chamadas de servidor secundárias e usar, em vez disso, conjuntos de relatórios virtuais, siga estas recomendações:

**Primeiro,** crie conjuntos de relatórios virtuais para corresponder aos dados dos conjuntos de relatórios secundários/filhos. Segmente em uma dimensão personalizada, como "marca", "plataforma", "domínio". Escolha uma dimensão que facilite distinguir uma propriedade digital de outra e aplique esses segmentos ao VRS.

* Se estiver migrando de uma implantação de marcação de multiconjunto existente do Adobe Analytics, lembre-se de comparar os segmentos dos conjuntos de relatórios virtuais antes de migrar os usuários. Certifique-se de que os segmentos que estão sendo usados nos conjuntos de relatórios virtuais estejam corretos.

* Se necessário, ajuste os segmentos nos quais os conjuntos de relatórios virtuais se baseiam.

* Como prática recomendada, use o [empilhamento de segmentos](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md) sempre que possível, para poder editar um segmento em um local e aplicar esse procedimento a todos os conjuntos de relatórios virtuais que usam esse segmento. Por exemplo, para criar um VRS para “usuários móveis da Europa” e outro para “usuários móveis da Ásia” crie um segmento para usuários móveis e, em seguida, separe segmentos para os usuários da Europa e da Ásia. Assim, se você quiser atualizar a definição do seu segmento “usuários móveis”, pode fazê-lo uma única vez, sem precisar atualizar cada segmento de conjunto de relatórios virtuais individualmente.

* Procure por conjuntos de dados mutualmente exclusivos nos conjuntos de relatórios virtuais. Por exemplo, você pode querer ver "Domínio A" e "Domínio B" como conjuntos de relatórios separados, e não querer o tráfego do Domínio A no conjunto de relatórios do Domínio B. Nesse caso, use um contêiner "ocorrência" para seus segmentos.

**Segundo**, depois de confirmar que os conjuntos de relatórios virtuais criados estão configurados corretamente e resolverão as necessidades da sua equipe, remova as IDs do conjunto de relatórios secundário da sua implementação.

Para remover conjuntos de relatórios secundários:

* Na Adobe Experience Platform Launch, acesse o "x" ao lado de quaisquer conjuntos de relatórios que não deseja mais usar.
* No DTM, localize a propriedade e a ferramenta do Adobe Analytics em questão. Nos campos ID da conta do produto e ID da conta de preparo, remova as IDs de conjunto de relatórios que não deseja mais usar.
* In legacy JavaScript implementations, locate the `s.account` variable and remove any report suites that you no longer wish to use.

Deixe somente as IDs do conjunto de relatórios global/pai para coletar dados dos seus sites e aplicativos. Na interface do Adobe Analytics, é possível ocultar conjuntos de relatórios herdados dos seus usuários ao acessar Admin &gt; Configurações da empresa.

Se não conseguir editar sua implementação, peça ajuda à equipe da sua conta da Adobe. Eles podem buscar opções para evitar que chamadas de servidor secundárias sejam processadas pelo Adobe Analytics.