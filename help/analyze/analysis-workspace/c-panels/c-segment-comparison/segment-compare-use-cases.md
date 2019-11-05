---
title: Casos de uso de comparação de segmentos
description: Saiba mais sobre casos de uso reais sobre como o painel de comparação de segmentos pode ser usado para obter informações sobre a estratégia de marketing.
keywords: IQ do segmento
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Casos de uso da IQ de segmento

O painel de comparação de segmentos é um recurso amplamente usado na Analysis Workspace. Os clientes frequentemente descobrem novas maneiras de gerar insights com ele. A seguir estão vários casos de uso bem-sucedidos.

## Caso de uso 1: comparar implementações móveis vs. desktop

> *"Comparamos o número de ocorrências diárias de um site ao de outro site e rapidamente encontramos um número de inconsistências na marcação. Dessa forma, evitamos problemas de dados antes o lançamento do produto."*

Um gerente de produto responsável por um site de web móvel e desktop foi incumbido de verificar se as tags eram consistentes em dispositivos móveis e desktop. Para certificar-se de que ele não perdeu nada importante, ele usou o painel de comparação de segmentos para comparar as ocorrências vindas de seu site móvel às ocorrências vindas de seu site de desktop. Ele notou que não havia eventos de checkout no site móvel e colocou as tags corretas antes do site móvel ser lançado. Como resultado, o gerente de produto evitou um desastre nos dados devido ao site móvel não ter registrado qualquer conversão. 

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contêiner de ocorrência onde o Tipo de dispositivo móvel é igual a Celular ou Tablet | Todos os outros |

## Caso de uso 2: compare os clientes que usam um certo recurso com aqueles que não

> *"Descobrimos que os clientes que utilizavam nosso recurso de comparação de produto era 10% mais passível de conversão. O movemos para o início da página e os pedidos aumentaram em 4%!"*

Uma equipe de otimização de site de varejo queria entender melhor os usuários que estavam interagindo com um recurso de comparação de produtos lançado recentemente. Eles usaram o painel de comparação de segmentos para comparar usuários que usaram o recurso de comparação de produtos a todos os outros no site. Eles identificaram rapidamente várias diferenças importantes, incluindo o fato de que esses usuários tinham 10% mais probabilidade de comprar um produto. A equipe de otimização do site decidiu testar o recurso de comparação de produto com destaque no topo da página.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contêiner de visitante onde o evento personalizado (ferramenta de comparação de preços) existe | Todos os outros |

## Caso de uso 3: comparar os visitantes do site de notícias com outros visitantes da seção do site

> *"Descobrimos que os visitantes em nossa nova seção de notícias eram duas vezes mais prováveis de assistir os comerciais do vídeo, então adicionamos mais opções de vídeo àquela seção. Vivenciamos um aumento de 7% de comerciais de vídeo assistidos!"*

Uma grande empresa de publicação de mídia observou maneiras de melhorar o envolvimento do conteúdo para os públicos-alvo em sua seção de notícias. Eles criaram um segmento de visitantes que visitaram a seção de notícias do site para entender melhor o público-alvo das notícias. Eles descobriram imediatamente que esses usuários tinham duas vezes mais probabilidade de assistir a anúncios de vídeo do que os visitantes de qualquer outra seção do site. A equipe de vídeo montou uma seção de vídeo recomendada em seu painel lateral de notícias e obteve um aumento de 7% nos anúncios de vídeo visualizados.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contêiner de visitante onde Seção do site é igual a "Notícias" | Todos os outros |

## Caso de uso 4: comparar os visitantes da pesquisa paga a todos os outros

> *"Visitantes vindos de ferramentas de busca eram 3 vezes mais suscetíveis à venda agregada que qualquer outro. We upped our spend on specific keywords as a result and achieved a 56% increase in up-sells."*

Uma importante empresa de serviços Business-to-Business (B2B) queria entender o tipo de tráfego que as palavras-chave de pesquisa pagas estavam levando para o site. A pesquisa paga não resultou em muitas conversões diretamente, e o executivo de marketing considerou diminuir o orçamento para ela. A equipe de marketing criou um segmento de visitantes que chegaram ao site por meio de pesquisa paga e os comparou a todos os outros visitantes usando o painel de comparação de segmentos. Eles descobriram que, embora esses visitantes não fossem tão susceptíveis a serem convertidos diretamente, eles eram três vezes mais susceptíveis a aumentar a venda em um serviço comprado anteriormente. A equipe de marketing focou seu orçamento apenas nas palavras-chave relacionadas à venda agregada e viu um aumento de 56% no serviço de vendas agregadas.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contêiner de visitante onde Tipo de referenciador é igual a Pesquisa paga | Todos os outros |

## Caso de uso 5: comparar compradores do Fitbit com todos os outros

> *"Descobrimos que as pessoas que compravam fitbits estavam 6 vezes mais susceptíveis a receber uma mensagem de 'fora de estoque' do que qualquer outra pessoa, então rapidamente pedimos mais fitbits e evitamos ficar sem estoque!"*

**** Cenário: Um grande varejista online estava interessado em saber como um dos melhores produtos de férias - a Fitbit - estava sendo vendido e o que fazia com que os compradores da Fitbit fossem únicos entre outros clientes. A equipe foi capaz de apenas clicar com o botão direito no item da linha "Fitbit" no relatório de produto e executar uma análise IQ de segmento rapidamente. Eles descobriram que os usuários que compravam fitbit estavam 6 vezes mais suscetíveis a receber uma mensagem de "fora de estoque" que qualquer outro cliente. Após a análise, a equipe de marketing foi capaz de direcionar esses visitantes para suas lojas tradicionais enquanto eles aguardavam o departamento de compra pedir mais Fitbits para serem enviados. Como resultado, a varejista evitou mais mensagens de “produto esgotado” e pode satisfazer as demandas de datas festivas.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contêiner de visitante onde existem pedidos e dimensão personalizada Marca igual a FitBit | Todos os outros |
