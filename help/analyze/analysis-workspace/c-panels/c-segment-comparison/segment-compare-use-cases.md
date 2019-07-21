---
description: O IQ do segmento (comparação de segmento) é um dos recursos mais usados na Analysis Workspace e os clientes estão constantemente encontrando novas formas de inovação e insight com ele. Aqui estão alguns casos de uso bem-sucedidos.
keywords: IQ do segmento
seo-description: O IQ do segmento (comparação de segmento) é um dos recursos mais usados na Analysis Workspace e os clientes estão constantemente encontrando novas formas de inovação e insight com ele. Aqui estão alguns casos de uso bem-sucedidos.
seo-title: Casos de uso do IQ do segmento
title: Casos de uso do IQ do segmento
uuid: 2 a 98 b 96 b -5529-4 c 7 f-a 787-27920603 d 5 b 0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Casos de uso do IQ do segmento

O IQ do segmento (comparação de segmento) é um dos recursos mais usados na Analysis Workspace e os clientes estão constantemente encontrando novas formas de inovação e insight com ele. Aqui estão alguns casos de uso bem-sucedidos.

## Use case 1: compare mobile vs desktop implementations {#section_B3A5983E58D0470895C030EA527C4966}

**"Comparamos o número de ocorrências diárias de um site ao de outro site e rapidamente encontramos um número de inconsistências na marcação. Dessa forma, evitamos problemas de dados antes o lançamento do produto."**

**Cenário**: um gerente de produto responsável por um site de web móvel de desktop foi marcado certificando-se de que as tags eram consistentes em todo o dispositivo móvel e de desktop. Para nos certificarmos de que não deixamos passar nada importante, ele utilizou o IQ do segmento para comparar o número de ocorrências diárias do site móvel ao número de ocorrências diárias do site de desktop. Ele observou que esqueceu de marcar o evento de checkout no site de web móvel e foi capaz de localizar as tags antes que o site móvel fosse lançado. Como resultado, o gerente de produto evitou um desastre nos dados devido ao site móvel não ter registrado qualquer conversão. 

**Como configurar essa comparação**

<table id="table_B5FA23CB34DE4331A8BD65ED4B351038"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Segmento 1 </th> 
   <th colname="col3" class="entry"> Segmento 2 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Usar/Criar um segmento nível-ocorrência onde </p> <p> </p> <p> 
     <ul id="ul_1F5D5136620E449D93A771CD2576A18A"> 
      <li id="li_CB32DD1033DA4E5CA3B9AD41030800E6">O tipo de dispositivo móvel equivale ao celular ou tablet </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Usar/Criar um segmento nível-ocorrência onde </p> <p> </p> <p> 
     <ul id="ul_79CC51C4C9494275B3F37B6D2AB0505E"> 
      <li id="li_83BE21AD1FB34195BAFF3F15421DBB3D">O tipo de dispositivo móvel não equivale ao celular ou tablet </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Use case 2: compare customers who use a certain feature to those who don't {#section_878B08FDD70A45E186C1F28EBA296636}

**"Descobrimos que os clientes que utilizavam nosso recurso de comparação de produto era 10% mais passível de conversão. O movemos para o início da página e os pedidos aumentaram em 4%!"**

**Cenário:** uma equipe de otimização de um site de venda queria entender melhor os usuários que estavam interagindo com o recurso de comparação de produto recentemente lançado. Ao criar um segmento de visitantes que interagiram com o recurso, eles foram capazes de usar o IQ do segmento para comparar aqueles usuários a todos os outros no site. O IQ do segmento identificou rapidamente diversas diferenças importantes, incluindo o fato de que esses usuários tinham uma probabilidade 10% maior de comprar um produto. A equipe de otimização do site decidiu testar o recurso de comparação de produto com destaque no topo da página.

**Como configurar essa comparação**

| Segmento 1 | Segmento 2 |
|--- |--- |
| Usar/criar um segmento de nível-visitante para visitantes que interagiam com a ferramenta de comparação de preço. | Use o segmento Todos gerado automaticamente e englobe os todos não inclusos no segmento 1. |

## Use case 3: compare news site visitors to other site section visitors {#section_0EAFC90C450244058B161200AC9901B8}

**"Descobrimos que os visitantes em nossa nova seção de notícias eram duas vezes mais prováveis de assistir os comerciais do vídeo, então adicionamos mais opções de vídeo àquela seção. Vivenciamos um aumento de 7% de comerciais de vídeo assistidos!"**

**Cenário:** uma grande empresa de comunicação estava procurando formas de aprimorar a participação com conteúdo de público-alvo na seção de notícias. Para entender melhor o público-alvo das notícias, eles criaram um segmento de visitantes que tinham visitado a seção de notícias do site. O IQ do segmento escaneou cada métrica e dimensão e descobriu imediatamente que os usuários estavam duas vezes mais suscetíveis de assistir comerciais em vídeo que os visitantes de qualquer outra seção do site. A equipe de vídeo elaborou uma seção de vídeo recomendada no painel lateral do site e conseguiram um aumento de 7% de comerciais em vídeo assistidos. Considerando todas as coisas nas quais eles poderiam ter desperdiçado tempo e empenho, isso facilitou e resultou em resultados rápidos e mensuráveis.

**Como configurar essa comparação**

| Segmento 1 | Segmento 2 |
|--- |--- |
| Usar/criar um segmento de nível-visitante na seção de noticias do site. | Use o segmento Todos gerado automaticamente e englobe os todos não inclusos no segmento 1. |

## Use case 4: compare visitors from paid search to everyone else {#section_73912670409349CAB131FE9D8B4FB11C}

**"Visitantes vindos de ferramentas de busca eram 3 vezes mais suscetíveis à venda agregada que qualquer outro. Como resultado, aumentamos nosso gasto com palavras-chave específicas e atingimos um aumento de 56% em nossas vendas agregadas."**

**Cenário:** uma importante empresa de serviços Business-to-Business (B2B) queria entender o tipo de tráfego que as palavras-chave de pesquisa pagas estavam levando para o site. A pesquisa paga não resultou em muitas conversões diretas e o executivo de marketing estava considerando diminuir o custo. A equipe de marketing criou um segmento de visitantes que iam para o site por meio da pesquisa paga e os comparou com os outros visitantes, utilizando o IQ do segmento. Eles descobriram que, embora esses visitantes não estivessem tão suscetíveis a converter diretamente, eles eram, contudo, 3 vezes mais suscetíveis à venda agregada em um serviço comprado anteriormente. A equipe de marketing foi, então, capaz de focar o orçamento apenas nas palavras-chave relativas à venda agregada e tiveram um aumento de 56% em serviços de vendas agregadas.

**Como configurar essa comparação**

| Segmento 1 | Segmento 2 |
|--- |--- |
| Usar/criar um segmento de nível de visitante para visitantes referenciados por Pesquisa natural ou que vieram de uma campanha SEM. | Use o segmento Todos gerado automaticamente e englobe os todos não inclusos no segmento 1. |

## Use case 5: compare Fitbit purchasers to everyone else {#section_9142B8A270764545B0A516AA309F1785}

**"Descobrimos que as pessoas que compravam fitbit estavam 6 vezes mais suscetíveis a receber uma mensagem de "fora de estoque" que qualquer outra pessoa, então pedimos rapidamente por mais fitbits e evitamos que acabasse o estoque!"**

**Cenário:** Um grande varejista online estava interessado em como um dos melhores produtos de datas de datas - o Fitbit - estava sendo vendido e o que fazia com que os compradores do Fitbit fossem exclusivos entre outros clientes. A equipe foi capaz de apenas clicar com o botão direito no item da linha "Fitbit" no relatório de produto e executar uma análise IQ de segmento rapidamente. Eles descobriram que os usuários que compravam fitbit estavam 6 vezes mais suscetíveis a receber uma mensagem de "fora de estoque" que qualquer outro cliente. Após a análise, a equipe de marketing foi capaz de direcionar esses visitantes para suas lojas tradicionais enquanto eles aguardavam o departamento de compra pedir mais Fitbits para serem enviados. Como resultado, a varejista evitou mais mensagens de “produto esgotado” e pode satisfazer as demandas de datas festivas.

**Como configurar essa comparação**

<table id="table_9018BEB4C2DE429FA773B250CB5C3E58"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Segmento 1 </th> 
   <th colname="col3" class="entry"> Segmento 2 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Usar/Criar um segmento nível-ocorrência onde, </p> <p> 
     <ul id="ul_52E8ED6F4F7241D5ABE4EE7EA1E556D8"> 
      <li id="li_33750601AB2A43728834B29AF86D5CCF">os pedidos são maiores ou iguais a 1, E </li> 
      <li id="li_4E09D1286DAE4BABA49E4834E73BDC28">a marca equivale ao Fitbit </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Use o segmento <span class="wintitle">Todos</span> gerado automaticamente e englobe os todos não inclusos no segmento 1. </p> </td> 
  </tr> 
 </tbody> 
</table>

