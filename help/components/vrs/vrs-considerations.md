---
description: Os conjuntos de relatórios virtuais e a marcação de vários conjuntos têm vantagens diferentes. Saiba qual é o melhor para sua organização.
keywords: Virtual Report Suite,VRS
title: Considerações sobre Conjuntos de relatórios virtuais e Marcação de vários conjuntos
topic: Adobe Analytics
uuid: f17d3659-a5b1-4807-a01d-a1b422009a64
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Considerações sobre Conjuntos de relatórios virtuais e Marcação de vários conjuntos

Os Conjuntos de relatórios virtuais (VRS) permitem exibir dados de um conjunto de relatórios que está coletando dados de suas propriedades digitais, mas com um segmento aplicado permanentemente.

Em muitos casos, você pode usar conjuntos de relatórios virtuais para substituir a marcação de vários conjuntos. Alternar para conjuntos de relatórios virtuais pode efetivamente remover a necessidade de [chamadas de servidor secundárias](/help/admin/c-server-call-usage/overage-overview.md). Por exemplo, sua organização tem 6 sites diferentes, cada um enviando dados para seu próprio conjunto de relatórios, bem como um conjunto de relatórios global combinado. Cada site recebe uma chamada de servidor secundária; um para o conjunto de relatórios de marca individual e um segundo para o conjunto de relatórios global. Em vez disso, você pode enviar dados de todos os sites exclusivamente para o conjunto de relatórios global e, em seguida, usar vários conjuntos de relatórios virtuais para separar cada marca.

Substituir a marcação de vários conjuntos pelo conjunto de relatórios global e os VRS permite simplificar sua implementação do Adobe Analytics e reduzir o consumo de chamada do servidor, o que é recomendado. No entanto, há algumas limitações importantes do VRS a serem consideradas. As orientações a seguir podem ajudá-lo a decidir se a melhor opção para você é implementar os conjuntos de relatórios virtuais integrados em um conjunto de relatórios global.

## Diretrizes

Se não tiver certeza se os casos de uso descritos se aplicam a você e a sua empresa, consulte outros administradores do Adobe Analytics ou o gerente de conta da Adobe. Eles podem ajudar a avaliar suas necessidades corporativas e recomendar a melhor opção.

Tenha as seguintes considerações em mente ao determinar se deve usar a marcação de vários conjuntos ou conjuntos de relatórios virtuais:

### Publicar segmentos na Adobe Experience Cloud

O compartilhamento de segmentos na Adobe Experience Cloud não é suportado para os conjuntos de relatórios virtuais. Os usuários que desejam compartilhar um segmento na Experience Cloud devem ter acesso ao conjunto de relatórios de origem.

Os segmentos ainda não podem ser publicados na Adobe Experience Cloud a partir de um conjunto de relatórios virtual para personalização e marcação. Todos os usuários que publicam segmentos precisam acessar o conjunto de relatórios de origem para este propósito. Por exemplo, seus usuários podem ter acesso somente a dados de suas regiões geográficas, mas você quer que eles consigam criar e compartilhar segmentos a partir do Adobe Analytics na Adobe Experience Cloud para direcionamento no Adobe Target. Nesse caso, a Adobe recomenda usar marcação de vários conjuntos. Se você não se importar com o acesso dos usuários ao conjunto de relatórios global ou se não precisar publicar segmentos para uso em outras soluções, os conjuntos de relatórios virtuais poderão ser usados.

### Dados atuais e em tempo real

Os relatórios em tempo real não são suportados nos conjuntos de relatórios virtuais, pois os dados são segmentados. Dados atuais não é compatível com os conjuntos de relatórios virtuais, pois eles não suportam segmentação. Ambos os recursos são específicos do Reports &amp; Analytics.

[Relatórios em tempo real](/help/admin/admin/realtime/t-realtime-admin.md) e [Dados atuais](/help/technotes/latency.md) não estão disponíveis nos conjuntos de relatórios virtuais. Isso afeta os usuários que respondem às tendências observadas no Reports &amp; Analytics em segundos ou alguns minutos de coleta de dados. Por exemplo, isso poderia incluir editores em uma sala de notícias que ajustam manchetes com base no consumo de conteúdo em tempo real. Considere usar a marcação de vários conjuntos se tiver necessidades significativas de dados em tempo real específicas para conjuntos de relatórios individuais. Os dados atuais e em tempo real ainda podem ser usados no conjunto de relatórios global.

### Limites únicos

Caso tenha um conjunto de relatórios global que combina um grande número de sites, é possível executar o item de linha de [baixo tráfego](/help/technotes/low-traffic.md) com frequência. Se você usar a marcação de vários conjuntos, isso será um problema apenas para o conjunto de relatórios global (os conjuntos de relatórios individuais têm menos probabilidade de ver tráfego baixo). Se usar conjuntos de relatórios virtuais, limites exclusivos serão compartilhados, fazendo com que os conjuntos de relatórios individuais também mostrem tráfego baixo. Considere usar a marcação de vários conjuntos se desejar evitar a definição de dados em tráfego baixo.

Por exemplo, uma grande organização de mídia possui 100 propriedades da Web. Cada propriedade publica algumas milhares de notícias por mês, além de hospedar todos os artigos de meses anteriores. Essa organização usa um conjunto de relatórios global no qual a eVar1 é &#39;Nome do artigo&#39;. Neste relatório, há aproximadamente 4 milhões de nomes de artigos únicos a cada mês das várias propriedades combinadas. Se estiver usando um conjunto de relatórios virtual, os 500.000 valores principais que compõem a maior parte do tráfego serão incluídos nos conjuntos de relatórios virtuais; os 3,5 restantes milhões estão incluídos no tráfego reduzido. Se a marcação de vários conjuntos for usada, cada conjunto de relatórios poderá ver seus próprios 500k valores principais. Os limites exclusivos do conjunto de relatórios global são os mesmos entre o uso da marcação de vários conjuntos e de conjuntos de relatórios virtuais.

O Atendimento ao cliente da Adobe pode aumentar os limites de valor exclusivos de um pequeno número de dimensões, o que pode eliminar esse problema por completo. Consulte sua equipe de conta e o Atendimento ao cliente para obter mais informações.

### Variáveis compartilhadas em conjuntos de relatórios

Os conjuntos de relatórios virtuais não possuem seus próprios conjuntos de dimensões e métricas; eles os herdam do conjunto de relatórios original. O conjunto de relatórios global deve capturar todas as dimensões e métricas de todos os sites. Os conjuntos de relatórios têm atualmente um máximo de 250 eVars e 1000 eventos personalizados.

Diferentes sites têm necessidades de implementação diversas. Algumas dimensões e eventos podem ser compartilhados entre dois sites. Por exemplo, um registro por email pode usar o mesmo evento em vários sites, acionando o mesmo evento personalizado. Outras dimensões podem ser específicas de um site. Por exemplo, apenas um de seus sites tem a capacidade de o usuário alterar a imagem de perfil. Este evento personalizado só seria implementado no site que o suporta.

Certifique-se de que o número de dimensões e métricas exclusivas possa se ajustar a um único conjunto de relatórios global. Se você descobrir que existem muitas dimensões ou métricas exclusivas, analise cada dimensão em cada implementação. Há, provavelmente, sobreposição e dimensões que não são essenciais para o sucesso dos negócios. Considere usar as [classificações](/help/components/c-classifications2/c-classifications.md) também. Por exemplo, em vez de capturar &#39;Nome do produto&#39; no eVar5, crie uma classificação &#39;Nome do produto&#39; baseada na dimensão &#39;Produto&#39;. As classificações em um conjunto de relatórios de origem são disponibilizadas automaticamente para qualquer conjunto de relatórios virtual dependente.

> [!TIP] Com a introdução da [curadoria](/help/analyze/analysis-workspace/curate-share/curate-projects-vrs.md), agora é possível alterar o nome de uma determinada dimensão ou métrica com base no VRS.

### Nuances de segmentação

Um conjunto de relatórios virtual em um nível fundamental é simplesmente um segmento aplicado a um conjunto de relatórios. As dimensões com base em visita e em visitantes podem fornecer resultados de relatório intuitivos.

Por exemplo, você tem dois sites, A e B, ambos enviando dados para um conjunto de relatórios global. Alguns visitantes inevitavelmente passam do site A para o site B, e esse movimento de um para o outro é visível na definição de caminho no conjunto de relatórios global. Se você criar conjuntos de relatórios virtuais para os sites A e B, uma visita que começou no site A e terminou no site B não mostraria uma página de entrada no VRS B. A página de entrada desta visita começou no site A, que é segmentado para fora do conjunto de relatórios virtual.

### Conversão de moeda

Os conjuntos de relatórios virtuais não são relatados em uma moeda diferente do conjunto de relatórios no qual eles são baseados. O Adobe Analytics permite a conversão monetária ao executar relatórios, mas a taxa de câmbio tem por base o dia atual (mesmo para dados históricos).

Se sua organização fizer a análise em uma única moeda, isso não causará problemas. No entanto, se tiver uma necessidade significativa de negócios por diferentes equipes regionais que precisam visualizar a receita em sua própria moeda local, considere usar a marcação de vários conjuntos.

### Feeds de dados

Os Feeds de dados não podem usar conjuntos de relatórios virtuais. No entanto, você pode receber um feed de dados de um conjunto de relatórios global e depois separá-lo.

Os Feeds de dados permitem que você receba uma exportação diária ou a cada hora de todos os dados do Adobe Analytics em um nível de ocorrência individual. Os Feeds de dados não podem ser pré-segmentados antes de serem entregues a você. Sendo assim, você só pode receber um feed de dados para seu conjunto de relatórios global. Se sua organização tiver uma grande necessidade por feeds de dados individuais em uma marca, propriedade, região ou outro nível granular, considere usar a marcação de vários conjuntos.

### Conectores de dados com contas de parceiros

Certas integrações de parceiros da Adobe no Adobe Analytics são limitadas a uma conta de parceiro por conjunto de relatórios. Algumas organizações podem exigir várias contas de parceiros para a mesma integração.

Por exemplo, somente um DCM do Google é permitido por conjunto de relatórios. Muitas empresas têm várias contas DCM, o que permite que diferentes marcas, unidades de negócios e regiões gerenciem seus anúncios separadamente. As integrações não podem ser configuradas em conjuntos de relatórios virtuais. Caso tenha conectores de dados dependentes com várias contas, considere usar a marcação de vários conjuntos.

### Fontes de dados de resumo

As Fontes de dados de resumo permitem importar métricas agregadas para o Adobe Analytics a um nível de conjunto de relatórios. Como os uploads das Fontes de dados de resumo contêm métricas agregadas, eles não podem ser segmentados. Como o VRS opera usando a segmentação, todos os dados importados usando fontes de dados de resumo não estão disponíveis nos conjuntos de relatórios virtuais. As fontes de dados de resumo estão visíveis somente no conjunto de relatórios de origem.

> [!TIP] As fontes de dados de processamento completo oferecem suporte à segmentação e podem ser usadas em conjuntos de relatórios virtuais.

## Etapas a serem seguidas se tiver decidido usar o VRS

Se optar por remover chamadas de servidor secundárias em favor dos conjuntos de relatórios virtuais:

1. Crie conjuntos de relatórios virtuais que correspondam aos dados dos conjuntos de relatórios secundários. Segmentar em uma dimensão personalizada que distingue seus sites uns dos outros.
   * Se migrar de uma implementação com tags de vários conjuntos, compare os segmentos do conjunto de relatórios virtual com os conjuntos de relatórios secundários existentes. Certifique-se de que os dados sejam comparáveis antes de mover os usuários para o conjunto de relatórios virtual.
   * Como prática recomendada, considere usar o [empilhamento de segmentos](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md) para poder editar um segmento em um local e aplicá-lo a todos os conjuntos de relatórios virtuais dependentes.
   * Use contêineres de ocorrência se desejar manter os conjuntos de relatórios virtuais mais mutuamente exclusivos.
2. Depois de confirmar que os conjuntos de relatórios virtuais estão configurados corretamente, remova as IDs do conjunto de relatórios secundário de sua implementação. Para remover conjuntos de relatórios secundários:
   * No Adobe Experience Platform Launch, clique no &quot;x&quot; ao lado de qualquer conjunto de relatórios que você não queira mais usar.
   * No DTM, localize a propriedade e a ferramenta do Analytics. Nos campos ID da conta do produto e ID da conta de preparo, remova as IDs de conjunto de relatórios que não deseja mais usar.
   * Em implementações JavaScript herdadas, localize a variável `s.account` e remova as IDs de conjunto de relatórios que você não deseja mais usar.
   * Em todos os casos, deixe apenas a ID do conjunto de relatórios global/principal para coletar dados para seus sites e aplicativos.
   * Navegue até Administração > Conjuntos de relatórios e oculte todos os conjuntos de relatórios secundários que não forem mais usados.
