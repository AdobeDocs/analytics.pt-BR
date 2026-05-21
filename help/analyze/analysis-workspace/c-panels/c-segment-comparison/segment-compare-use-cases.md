---
title: Casos de uso de comparação de segmentos
description: Conheça casos de uso reais para saber como o painel de comparação de segmentos pode ser usado para obter insights sobre a estratégia de marketing.
keywords: Segment IQ
feature: Segmentation
role: User, Admin
exl-id: d7c02e5c-5313-4e12-86cb-d483644ccbc7
TQID: https://experienceleague.adobe.com/RSrhYA6EYk3UhFqMQ1FJVHzqA7RFIqdvSyvatTF0goE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 859
ht-degree: 13%

---

# Casos de uso de comparação de segmentos

O painel de comparação de segmentos é um recurso amplamente usado no Analysis Workspace. Os clientes frequentemente descobrem novas maneiras de gerar insights com o ao usar o painel. Encontre abaixo alguns casos de uso típicos

## Caso de uso 1: comparar a implementação em dispositivos móveis e em desktops

> *&quot;Você comparou ocorrências de um site a outro site e rapidamente encontrou várias inconsistências de marcação. Dessa forma, você evitou problemas de dados antes o lançamento do produto.&quot;*

Você é responsável por um site para dispositivos móveis e um site para desktop e tem a tarefa de garantir que as tags sejam consistentes entre as duas versões. Para não perder nada importante, use o painel de comparação de segmentos para comparar as ocorrências vindas do site para dispositivos móveis com as vindas do site para desktop. Você percebe que não há eventos de check-out no site para dispositivos móveis e coloca as tags corretas antes do lançamento do site. Como resultado, você evita um desastre nos dados porque o site para dispositivos móveis não está registrando conversões.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contêiner de ocorrências em que o Tipo de dispositivo móvel é Celular ou Tablet | Todos os outros |

{style="table-layout:fixed"}


## Caso de uso 2: comparar clientes que usam um determinado recurso com clientes que não o usam

> *&quot;Você descobriu que os clientes que utilizavam o recurso de comparação de produto eram 10% mais passíveis de conversão. Você moveu a comparação de produtos para o início da página e os pedidos aumentaram em 4%!&quot;*

Uma equipe de otimização de um site de varejo deseja entender melhor os usuários que estão interagindo com o recurso de comparação de produto lançado recentemente. Eles usam o painel de comparação de segmentos para comparar usuários que usam o recurso de comparação de produtos com todos os outros usuários do site. Eles identificam rapidamente várias diferenças importantes, incluindo a probabilidade 10% maior de que esses usuários comprem um produto. A equipe de otimização do site decide testar o recurso de comparação de produto com mais destaque na parte superior da página.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contêiner de visitantes com o evento personalizado (ferramenta de comparação de preços) | Todos os outros |

{style="table-layout:fixed"}


## Caso de uso 3: comparar visitantes da seção de notícias do site com visitantes de outras seções do site

> *&quot;Você descobriu que a probabilidade dos visitantes da sua seção de notícias assistir a comerciais de vídeo era duas vezes maior, então adicionou mais opções de vídeo àquela seção. Você experimentou um aumento de 7% de comerciais de vídeo assistidos!&quot;*

Uma grande empresa de publicação de mídia procura maneiras de melhorar o engajamento do público-alvo na seção de notícias. Eles criam um segmento de visitantes que visitam a seção de notícias do site para entender melhor o público de notícias. Eles percebem imediatamente que a probabilidade de assistir aos vídeos de anúncio é duas vezes maior nos usuários dessa seção do que nos visitantes de qualquer outra seção do site. A equipe de vídeo elaborou uma seção de vídeos recomendados no painel lateral do site de notícias e obteve um aumento de 7% na visualização de anúncios de vídeo.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contêiner de visitantes em que a Seção do site é “Notícias” | Todos os outros |

{style="table-layout:fixed"}


## Caso de uso 4: comparar visitantes vindos de ferramentas de pesquisa paga com todos os outros

> *&quot;A probabilidade de realizar uma venda adicional para visitantes vindos de mecanismos de pesquisa era 3 vezes maior do que para o resto. Como resultado, você aumentou seu investimento em palavras-chave específicas e obteve um aumento de 56% nas vendas adicionais.&quot;*

Uma importante empresa de serviços B2B deseja entender o tipo de tráfego que as palavras-chave de pesquisa pagas estão levando para o site da empresa. A pesquisa paga não resultou em várias conversões diretas e o executivo de marketing considera diminuir o orçamento. A equipe de marketing cria um segmento de visitantes que chegam ao site por meio de pesquisa paga e comparam esse segmento com todos os outros visitantes usando o painel de comparação de segmentos. Eles descobrem que, embora a probabilidade de conversão direta desses visitantes não seja alta, a probabilidade de venda adicional relacionada com um serviço adquirido anteriormente é 3 vezes maior. A equipe de marketing foca seu orçamento apenas nas palavras-chave relacionadas à venda adicional e observa um aumento de 56% nas vendas adicionais de serviços.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contêiner de visitante em que Tipo de referenciador é Pesquisa paga | Todos os outros |

{style="table-layout:fixed"}


## Caso de uso 5: comparar compradores de Fitbit com todos os outros

> *&quot;Você descobriu que a probabilidade de receber mensagens de &quot;Produto esgotado&quot; era 6 vezes maior para compradores de Fitbits do que para o resto. Assim, você rapidamente pediu mais Fitbits e evitou ficar sem estoque!&quot;*

**Cenário:** uma importante retailer online está interessada em saber como um dos melhores produtos de datas festivas, o Fitbit, está sendo vendido e o que torna os compradores do Fitbit únicos comparados aos outros clientes. A equipe de marketing pode selecionar o item de linha Fitbit no relatório de produtos e executar rapidamente uma análise de comparação de segmentos no menu de contexto. O que eles descobrem é que os usuários que compram Fitbits têm 6 vezes mais chances de receber uma mensagem de &quot;Produto esgotado&quot; do que qualquer outro cliente. Após uma análise mais aprofundada, a equipe de marketing é capaz de direcionar esses visitantes para suas lojas tradicionais enquanto eles esperam que o departamento de compra solicite mais Fitbits para serem enviados. Como resultado, a retailer evita mais mensagens de &quot;Produto esgotado&quot; e é capaz de atender mais da demanda nos feriados.

| Segmento 1 | Segmento 2 |
|--- |--- |
| Contêiner de visitante em que existe a seção Pedidos e a dimensão personalizada Marca é FitBit | Todos os outros |

{style="table-layout:fixed"}