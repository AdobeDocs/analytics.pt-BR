---
title: Código de rastreamento
description: O nome do código de rastreamento ou da campanha.
translation-type: tm+mt
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---


# Código de rastreamento

A dimensão &#39;Código de rastreamento&#39; lista os nomes dos códigos de rastreamento no site. Normalmente, essa dimensão é coletada usando parâmetros de string de query. Você pode colocar links com diferentes valores de parâmetro de string de query em diferentes lugares na Internet. Esta dimensão relata quais links foram os mais bem-sucedidos ao direcionar o tráfego para o site.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da string [`v0` do](/help/implement/validate/query-parameters.md) query em solicitações de imagem. O AppMeasurement coleta esses dados usando a [`campaign`](/help/implement/vars/page-vars/campaign.md) variável.

## itens de Dimension

Os itens de Dimension incluem os nomes dos códigos de rastreamento no site. Sua organização determina quais itens de dimensão você deseja usar.

## Compare a dimensão do código de rastreamento com canais de marketing que coletam códigos de rastreamento

Alguns usuários que configuram regras de processamento de canais de marketing configuram uma regra que utiliza todos os valores usados na dimensão de código de rastreamento. Embora excelente, são diferentes por causa das diferenças inerentes ao processamento e à arquitetura. A lista a seguir explica por que essas duas dimensões, embora semelhantes num relance, não podem ser comparadas entre si.

* **canais anteriores nas regras** de processamento: As regras de processamento de canais de marketing mais altas na lista podem impedir que as ocorrências sejam atribuídas ao canal de marketing de Códigos de rastreamento. Por exemplo:

   1. Você tem &quot;Redes sociais&quot; configuradas como sua primeira regra e &quot;Códigos de rastreamento&quot; como sua segunda.
   2. Um usuário publica um link para seu site contendo um código de rastreamento em um site de mídia social, e vários de seus amigos clicam nesse link para seu site.

   Como &#39;Redes sociais&#39; é a primeira regra de processamento de canais de marketing, esses usuários atribuem ao canal de marketing &#39;Redes sociais&#39; e não ao canal de marketing de códigos de rastreamento.
* **Outros canais de marketing podem roubar atribuição**: Ao lidar com uma dimensão de Códigos de rastreamento padrão, você não precisa se preocupar com outras partes do site roubando atribuição. No entanto, com canais de marketing, um usuário pode corresponder a uma regra diferente, dando atribuição diferente. Por exemplo:
   1. Você tem &#39;Códigos de rastreamento&#39; como seu primeiro canal, e &#39;Direto&#39; como seu segundo.
   2. Inicialmente, um usuário chega ao seu site por meio de um código de rastreamento, mas depois sai.
   3. No dia seguinte, eles digitam seu URL na barra de endereços e fazem uma compra.

   O canal de marketing dos códigos de rastreamento não obteria crédito de último toque para essa compra. Em vez disso, iria para o canal de marketing &#39;Direto&#39;.
* **Diferenças** de expiração: Os canais de marketing têm uma expiração contínua de 30 dias de envolvimento do visitante, quer o canal tenha sido tocado ou não. Os códigos de rastreamento têm uma expiração com base em quando a variável foi definida. Por exemplo:
   1. Você tem uma expiração de envolvimento de visitante de 30 dias e também configurou a dimensão Código de rastreamento para expirar após 30 dias.
   2. Um usuário chega ao seu site por meio de um código de rastreamento. Eles navegam pelo site, depois vão embora.
   3. Três semanas depois, eles voltam sem um código de rastreamento ou canal de marketing e depois saem novamente.
   4. Outras duas semanas depois (cinco semanas após a visita inicial), eles voltam sem um código de rastreamento ou canal de marketing e, em seguida, fazem uma compra.
   Em última análise, o usuário fez uma compra além de 30 dias, mas nunca esteve inativo por mais de 30 dias. Você veria a receita atribuída ao canal de marketing dos códigos de rastreamento, mas não à dimensão independente.
