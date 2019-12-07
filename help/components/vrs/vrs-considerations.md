---
description: Os conjuntos de relatórios virtuais e a marcação de vários conjuntos têm vantagens diferentes. Saiba qual é o melhor para sua organização.
keywords: Virtual Report Suite,VRS
title: Considerações sobre conjuntos de relatórios virtuais e marcação de vários conjuntos
topic: Adobe Analytics
uuid: f17d3659-a5b1-4807-a01d-a1b422009a64
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Considerações sobre conjuntos de relatórios virtuais e marcação de vários conjuntos

Os Conjuntos de relatórios virtuais (VRS) permitem exibir dados de um conjunto de relatórios que está coletando dados de suas propriedades digitais, mas com um segmento aplicado permanentemente.

Em muitos casos, você pode usar conjuntos de relatórios virtuais para substituir a marcação de vários conjuntos. A alternância para conjuntos de relatórios virtuais pode efetivamente remover a necessidade de chamadas [de servidor](/help/admin/c-server-call-usage/overage-overview.md)secundárias. Por exemplo, sua organização tem 6 sites diferentes, cada um enviando dados para seu próprio conjunto de relatórios, bem como um conjunto de relatórios global combinado. Cada site recebe uma chamada de servidor secundária; um para o conjunto de relatórios de marca individual e um segundo para o conjunto de relatórios global. Em vez disso, você pode enviar dados de todos os sites exclusivamente para o conjunto de relatórios global e, em seguida, usar vários conjuntos de relatórios virtuais para separar cada marca.

Substituir a marcação de vários relatórios por um conjunto de relatórios global e um VRS permite simplificar a implementação do Adobe Analytics e reduzir o consumo de chamadas do servidor, além de ser uma prática recomendada. No entanto, há algumas limitações importantes do VRS a serem consideradas. As orientações a seguir podem ajudá-lo a decidir se a melhor opção para você é implementar os conjuntos de relatórios virtuais integrados em um conjunto de relatórios global.

## Diretrizes

Se não tiver certeza se os casos de uso descritos se aplicam a você e à sua organização, consulte seus outros administradores do Adobe Analytics ou seu gerente de contas da Adobe. Eles podem ajudar a avaliar suas necessidades corporativas e recomendar a melhor opção.

Tenha as seguintes considerações em mente ao determinar se você deve usar tags de vários conjuntos ou conjuntos de relatórios virtuais:

### Publicar segmentos na Adobe Experience Cloud

O compartilhamento de segmentos na Adobe Experience Cloud não é suportado para os conjuntos de relatórios virtuais. Os usuários que desejam compartilhar um segmento na Experience Cloud devem ter acesso ao conjunto de relatórios de origem.

Os segmentos ainda não podem ser publicados na Adobe Experience Cloud a partir de um conjunto de relatórios virtual para personalização e direcionamento. Todos os usuários que publicam segmentos precisam acessar o conjunto de relatórios de origem para essa finalidade. Por exemplo, você deseja que os usuários tenham acesso apenas aos dados de suas regiões geográficas, mas deseja que eles possam criar e compartilhar segmentos do Adobe Analytics na Adobe Experience Cloud para definição de metas no Adobe Target. Nesse caso, a Adobe recomenda usar marcação de vários relatórios. Se você não se importar com o acesso dos usuários ao conjunto de relatórios global ou se não precisar publicar segmentos para uso em outras soluções, os conjuntos de relatórios virtuais poderão ser usados.

### Dados atuais e em tempo real

Os relatórios em tempo real não são suportados nos conjuntos de relatórios virtuais, pois os dados são segmentados. Os dados atuais também não são suportados em conjuntos de relatórios virtuais, pois não são compatíveis com a segmentação. Ambos os recursos são específicos do Relatórios e análises.

[Relatórios](/help/admin/admin/realtime/t-realtime-admin.md) em tempo real e Dados [](/help/technotes/latency.md) atuais não estão disponíveis em conjuntos de relatórios virtuais. Isso afeta os usuários que respondem às tendências observadas no Relatórios e análises em segundos ou alguns minutos de coleta de dados. Por exemplo, isso pode incluir editores em uma sala de notícias que ajustam manchetes com base no consumo de conteúdo em tempo real. Considere usar a marcação de vários conjuntos se você tiver necessidades significativas de dados em tempo real específicas para conjuntos de relatórios individuais. Os dados atuais e em tempo real ainda podem ser usados no conjunto de relatórios global.

### Limites únicos

Se você tiver um conjunto de relatórios global que combina um grande número de sites, é possível que você execute o item de linha de [baixo tráfego](/help/technotes/low-traffic.md) com frequência. Se você usar a marcação de vários relatórios, isso será apenas um problema para o conjunto de relatórios global (os conjuntos de relatórios individuais têm menos probabilidade de ver tráfego baixo). Se você usar conjuntos de relatórios virtuais, limites exclusivos serão compartilhados, fazendo com que conjuntos de relatórios individuais também mostrem tráfego baixo. Considere usar a marcação de vários conjuntos se desejar evitar a definição de dados em tráfego baixo.

Por exemplo, uma grande organização de mídia possui 100 propriedades da Web. Cada propriedade publica algumas milhares de notícias por mês, além de hospedar todos os artigos de meses anteriores. Essa organização usa um conjunto de relatórios global no qual a eVar1 é 'Nome do artigo'. Neste relatório, há aproximadamente 4 milhões de nomes de artigos únicos a cada mês das várias propriedades combinadas. Se estiver usando um conjunto de relatórios virtual, os 500.000 valores principais que compõem a maior parte do tráfego serão incluídos nos conjuntos de relatórios virtuais; os restantes 3,5 milhões estão incluídos no tráfego reduzido. Se a marcação de vários relatórios for usada, cada conjunto de relatórios pode ver seus próprios valores 500k principais. Os limites exclusivos do conjunto de relatórios global são os mesmos entre o uso de tags de vários conjuntos e conjuntos de relatórios virtuais.

O Atendimento ao cliente da Adobe pode aumentar os limites de valor exclusivos para um pequeno número de dimensões, o que pode eliminar esse problema por completo. Consulte sua equipe de conta e o Atendimento ao cliente para obter mais informações.

### Variáveis compartilhadas em conjuntos de relatórios

Os conjuntos de relatórios virtuais não têm seus próprios conjuntos de dimensões e métricas; eles herdam esses dados do conjunto de relatórios de origem. O conjunto de relatórios global deve capturar todas as dimensões e métricas de todos os sites. Os conjuntos de relatórios têm atualmente um máximo de 250 eVars e 1000 eventos personalizados.

Diferentes sites têm necessidades de implementação diferentes. Algumas dimensões e eventos podem ser compartilhados entre dois sites. Por exemplo, um registro por email pode usar o mesmo evento em vários sites, acionando o mesmo evento personalizado. Outras dimensões podem ser específicas a um site. Por exemplo, apenas um de seus sites tem a capacidade de o usuário alterar sua imagem de perfil. Este evento personalizado só seria implementado no site que o suporta.

Certifique-se de que o número de dimensões e métricas exclusivas possa se ajustar em um único conjunto de relatórios global. Se você descobrir que existem muitas dimensões ou métricas exclusivas, analise cada dimensão em cada implementação. Há provavelmente sobreposição e dimensões que não são essenciais para o sucesso dos negócios. Considere usar [as classificações](/help/components/c-classifications2/c-classifications.md) também. Por exemplo, em vez de capturar 'Nome do produto' no eVar5, crie uma classificação 'Nome do produto' baseada na dimensão 'Produto'. As classificações em um conjunto de relatórios de origem ficam automaticamente disponíveis para qualquer conjunto de relatórios virtual dependente.

> [!TIP] Com a introdução da [curadoria](/help/analyze/analysis-workspace/curate-share/curate-projects-vrs.md), é possível alterar o nome de uma determinada dimensão ou métrica com base em cada VRS.

### Nuances de segmentação

Um conjunto de relatórios virtual em um nível fundamental é simplesmente um segmento aplicado a um conjunto de relatórios. As dimensões com base em visita e visitantes podem fornecer resultados de relatório inintuitivos.

Por exemplo, você tem dois sites, A e B, ambos enviando dados para um conjunto de relatórios global. Alguns visitantes inevitavelmente passam do site A para o site B, e esse movimento de um para o outro é visível na definição de caminho no conjunto de relatórios global. Se você criar conjuntos de relatórios virtuais para os sites A e B, uma visita que começou no site A e terminou no site B não mostraria uma página de entrada no VRS B. A página de entrada desta visita começou no site A, que é segmentado para fora do conjunto de relatórios virtual.

### Conversão de moeda

Os conjuntos de relatórios virtuais não relatam em uma moeda diferente do conjunto de relatórios em que se baseiam. O Adobe Analytics permite a conversão monetária ao executar relatórios, mas a taxa de câmbio se baseia no dia atual (mesmo para dados históricos).

Se sua organização fizer a análise em uma única moeda, isso não causará problemas. No entanto, se você tiver uma necessidade significativa de negócios para diferentes equipes regionais que precisam visualizar a receita em sua própria moeda local, considere usar a marcação de vários conjuntos.

### Feeds de dados

Os Feeds de dados não podem usar conjuntos de relatórios virtuais. No entanto, você pode receber um feed de dados de um conjunto de relatórios global e depois separá-lo.

Os Feeds de dados permitem que você receba uma exportação diária ou horária de todos os dados do Adobe Analytics em um nível de ocorrência individual. Os Feeds de dados não podem ser pré-segmentados antes de serem entregues a você, portanto, você só pode receber um feed de dados para seu conjunto de relatórios global. Se sua organização tiver uma grande necessidade de feeds de dados individuais em uma marca, propriedade, região ou outro nível granular, considere usar a marcação de vários conjuntos.

### Conectores de dados com contas de parceiros

Certas integrações de parceiros da Adobe no Adobe Analytics são limitadas a uma conta de parceiro por conjunto de relatórios. Algumas organizações podem exigir várias contas de parceiros para a mesma integração.

Por exemplo, somente um DCM do Google é permitido por conjunto de relatórios. Muitas empresas têm várias contas DCM, o que permite que diferentes marcas, unidades de negócios e regiões gerenciem seus anúncios separadamente. As integrações não podem ser configuradas em conjuntos de relatórios virtuais. Se você tiver conectores de dados dependentes com várias contas, considere usar a marcação de vários conjuntos.

### Fontes de dados de resumo

As fontes de dados de resumo permitem importar métricas agregadas para o Adobe Analytics em um nível de conjunto de relatórios. Como os uploads da fonte de dados de resumo contêm métricas agregadas, eles não podem ser segmentados. Como o VRS opera usando a segmentação, todos os dados importados usando fontes de dados de resumo não estão disponíveis nos conjuntos de relatórios virtuais. As fontes de dados de resumo estão visíveis somente no conjunto de relatórios de origem.

> [!TIP] As fontes de dados de processamento completo oferecem suporte à segmentação e podem ser usadas em conjuntos de relatórios virtuais.

## Etapas a serem seguidas se tiver decidido usar o VRS

Se você optar por remover chamadas de servidor secundárias em favor dos conjuntos de relatórios virtuais:

1. Crie conjuntos de relatórios virtuais para corresponder aos dados nos conjuntos de relatórios secundários. Segmentar em uma dimensão personalizada que distingue seus sites uns dos outros.
   * Se você migrar de uma implementação com tags de vários conjuntos, compare os segmentos do conjunto de relatórios virtual com os conjuntos de relatórios secundários existentes. Certifique-se de que os dados sejam comparáveis antes de mover os usuários para o conjunto de relatórios virtual.
   * Como prática recomendada, considere usar o empilhamento [de](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md) segmentos para poder editar um segmento em um local e aplicá-lo a todos os conjuntos de relatórios virtuais dependentes.
   * Use contêineres de ocorrência se desejar manter os conjuntos de relatórios virtuais mais mutuamente exclusivos.
2. Depois de confirmar que os conjuntos de relatórios virtuais estão configurados corretamente, remova as IDs do conjunto de relatórios secundário de sua implementação. Para remover conjuntos de relatórios secundários:
   * No Adobe Experience Platform Launch, clique no "x" ao lado de qualquer conjunto de relatórios que você não queira mais usar.
   * No DTM, localize a propriedade e a ferramenta Analytics. Nos campos ID da conta de produção e ID da conta de armazenamento temporário, remova todas as IDs do conjunto de relatórios que você não deseja mais usar.
   * Em implementações JavaScript herdadas, localize a `s.account` variável e remova quaisquer IDs de conjunto de relatórios que você não deseja mais usar.
   * Em todos os casos, deixe apenas a ID do conjunto de relatórios global/pai para coletar dados para seus sites e aplicativos.
   * Navegue até Administrador &gt; Conjuntos de relatórios e oculte todos os conjuntos de relatórios secundários que não forem mais usados.
