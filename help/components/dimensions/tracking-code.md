---
title: Código de rastreamento
description: O nome do código de rastreamento ou da campanha.
feature: Dimensions
exl-id: e4f70552-6946-4974-a9e2-928faf563ecd
TQID: 'https://experienceleague.adobe.com/8e9126PxGCNXJqo4a3XYTgXwrcHdf34FVwygpHXm5JI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 88%
---
# Código de rastreamento

A [dimensão](overview.md) “Código de rastreamento” lista os nomes dos códigos de rastreamento no site. Você pode colocar links com diferentes valores de parâmetro de sequência de consulta em diferentes lugares na Internet. Essa dimensão ajuda a entender quais links foram os mais bem-sucedidos em direcionar tráfego para o site.

Anexar strings de consulta de código de rastreamento é comum em emails, anúncios, publicações em redes sociais e outros esforços de marketing da organização.

## Preencher esta dimensão com dados

O AppMeasurement coleta esses dados usando a variável [`campaign`](/help/implement/vars/page-vars/campaign.md). Normalmente, essa variável obtém seu valor de uma cadeia de caracteres de consulta usando o método de utilitário [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md), embora sua organização determine exatamente como defini-la.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | [`campaign`](/help/implement/vars/page-vars/campaign.md) |
| **Web SDK / campo XDM** | [`marketing.trackingCode`](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/field-groups/event/campaign-marketing-details) |
| **Parâmetro de consulta** | [`v0`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Marca XML** | [`<campaign>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite de bytes** | 255 bytes |
| **Persistência** | Configurável |

## Itens de dimensão

Os itens de dimensão incluem os nomes dos códigos de rastreamento no site. A organização escolhe quais itens de dimensão específicos deseja utilizar. Consulte [Rastreamento de campanha](/help/implement/use-cases/campaign-tracking.md) para obter mais informações.

## Compare a dimensão Código de rastreamento com Canais de marketing que coletam códigos de rastreamento

Alguns usuários que configuram regras de processamento de canais de marketing configuram uma regra que utiliza todos os valores usados na dimensão Código de rastreamento. Embora excelente, são distintas por causa das diferenças inerentes ao processamento e à arquitetura. A lista a seguir explica por que esses dois métodos, embora semelhantes a princípio, podem alterar o comportamento da atribuição.

### Canais anteriores nas regras de processamento

As regras de processamento dos canais de marketing nas posições mais altas na lista podem evitar que hits sejam atribuídos ao canal de marketing Códigos de rastreamento. Por exemplo:

1. Você tem “Redes sociais” configuradas como a primeira regra e “Códigos de rastreamento” como a segunda.
2. Um usuário publica um link para seu site contendo um código de rastreamento em um site de mídia social, e vários de seus amigos clicam nesse link.

Como “Redes sociais” é a primeira regra de processamento de canais de marketing, esses usuários atribuem ao canal de marketing “Redes sociais” e não ao canal de marketing Códigos de rastreamento.

### Outros canais de marketing podem receber a atribuição por meio do último contato

Ao lidar com uma dimensão Códigos de rastreamento padrão, não é necessário se preocupar com outras partes do site roubando atribuições. No entanto, com canais de marketing, um usuário pode corresponder a uma regra diferente, oferecendo atribuição diferente. Por exemplo:

1. Você tem “Códigos de rastreamento” como o primeiro canal, e “Direto” como o segundo.
2. Inicialmente, um usuário chega ao seu site por meio de um código de rastreamento, mas depois sai.
3. No dia seguinte, eles digitam seu URL na barra de endereços e fazem uma compra.

Nesse exemplo, o canal de marketing Códigos de rastreamento não obteria crédito de último contato para essa compra. Em vez disso, iria para o canal de marketing “Direto”.


### Diferenças de expiração

Os canais de marketing têm um período de expiração do engajamento do visitante de 30 dias contínuos, independentemente de um canal ter tido ou não contato. A expiração dos códigos de rastreamento se baseia em quando a variável foi definida. Por exemplo:

1. Você tem uma expiração de engajamento de visitante de 30 dias e também configurou a dimensão Código de rastreamento para expirar após 30 dias.
2. Um usuário chega ao seu site por meio de um código de rastreamento. Eles navegam pelo site, depois saem.
3. Três semanas depois, eles voltam sem um código de rastreamento ou canal de marketing e depois saem novamente.
4. Mais duas semanas depois (cinco semanas após a visita inicial), eles voltam sem um código de rastreamento ou canal de marketing e, em seguida, fazem uma compra.

O usuário acabou fazendo uma compra depois de 30 dias, mas nunca ficou inativo por mais de 30 dias. Nesse caso, seria possível visualizar a receita atribuída ao canal de marketing Códigos de rastreamento, mas não para a dimensão Código de rastreamento.



