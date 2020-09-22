---
title: Código de rastreamento
description: O nome do código de rastreamento ou da campanha.
translation-type: ht
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: ht
source-wordcount: '525'
ht-degree: 100%

---


# Código de rastreamento

A dimensão “Código de rastreamento” lista os nomes dos códigos de rastreamento no site. Normalmente, essa dimensão é coletada usando parâmetros de sequência de consulta. Você pode colocar links com diferentes valores de parâmetro de sequência de consulta em diferentes lugares na Internet. Esta dimensão relata quais links foram os mais bem-sucedidos ao direcionar o tráfego para o site.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da [`v0` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável [`campaign`](/help/implement/vars/page-vars/campaign.md).

## Itens de dimensão

Os itens de dimensão incluem os nomes dos códigos de rastreamento no site. A organização escolhe quais itens de dimensão específicos quer utilizar.

## Compare a dimensão Código de rastreamento com Canais de marketing que coletam códigos de rastreamento

Alguns usuários que configuram regras de processamento de canais de marketing configuram uma regra que utiliza todos os valores usados na dimensão Código de rastreamento. Embora excelente, são distintas por causa das diferenças inerentes ao processamento e à arquitetura. A lista a seguir explica por que essas duas dimensões, embora semelhantes a princípio, não podem ser comparadas entre si.

* **Canais anteriores em regras de processamento**: as regras de processamento dos canais de marketing em posições mais altas na lista podem evitar que as ocorrências sejam atribuídas ao seu canal de marketing Códigos de rastreamento. Por exemplo:

   1. Você tem “Redes sociais” configuradas como a primeira regra e “Códigos de rastreamento” como a segunda.
   2. Um usuário publica um link para seu site contendo um código de rastreamento em um site de mídia social, e vários de seus amigos clicam nesse link.

   Como “Redes sociais” é a primeira regra de processamento de canais de marketing, esses usuários atribuem ao canal de marketing “Redes sociais” e não ao canal de marketing Códigos de rastreamento.
* **Outros canais de marketing podem roubar atribuição**: ao lidar com uma dimensão Códigos de rastreamento padrão, você não precisa se preocupar porque outras partes do site não roubarão a atribuição. No entanto, com canais de marketing, um usuário pode corresponder a uma regra diferente, oferecendo atribuição diferente. Por exemplo:
   1. Você tem “Códigos de rastreamento” como o primeiro canal, e “Direto” como o segundo.
   2. Inicialmente, um usuário chega ao seu site por meio de um código de rastreamento, mas depois sai.
   3. No dia seguinte, eles digitam seu URL na barra de endereços e fazem uma compra.

   O canal de marketing Códigos de rastreamento não obteria crédito de último contato para essa compra. Em vez disso, iria para o canal de marketing “Direto”.
* **Diferenças de expiração**: Os canais de marketing têm uma expiração contínua do engajamento do visitante de 30 dias, independentemente de um canal ter tido ou não contato. A expiração dos códigos de rastreamento se baseia em quando a variável foi definida. Por exemplo:
   1. Você tem uma expiração de engajamento de visitante de 30 dias e também configurou a dimensão Código de rastreamento para expirar após 30 dias.
   2. Um usuário chega ao seu site por meio de um código de rastreamento. Eles navegam pelo site, depois saem.
   3. Três semanas depois, eles voltam sem um código de rastreamento ou canal de marketing e depois saem novamente.
   4. Mais duas semanas depois (cinco semanas após a visita inicial), eles voltam sem um código de rastreamento ou canal de marketing e, em seguida, fazem uma compra.
   O usuário acabou fazendo uma compra depois de 30 dias, mas nunca ficou inativo por mais de 30 dias. Você veria a receita atribuída ao canal de marketing dos códigos de rastreamento, mas não à dimensão independente.
