---
title: Dimensões de saída
description: Lista as dimensões de saída e o seu uso.
keywords: página de saída, seção do site de saída, servidor de saída, sair do Custom Insight
feature: Dimensions
exl-id: b2b1ee88-e5c3-44b5-8159-85ec53d20258
TQID: 'https://experienceleague.adobe.com/YRjvhW8OzBlip9ok0-1D4rYSljkccpIAlDkqCQv7nyo'
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
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 74%
---
# Dimensões de saída

>[!BEGINSHADEBOX]

*Esta página de ajuda descreve como as saídas funcionam como uma [dimensão](overview.md). Para obter informações sobre como as saídas funcionam como uma métrica, consulte a métrica [Saídas](../metrics/exits.md).*

>[!ENDSHADEBOX]

As dimensões de saída registram o item da última dimensão e o aplicam retroativamente a todos os hits na visita. As dimensões de saída estão disponíveis para todas as variáveis com definição de caminho habilitada em [Variáveis de tráfego](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md) nas configurações do conjunto de relatórios.

## Preencher dimensões de saída com dados

Uma determinada dimensão de saída é baseada em sua variável de tráfego associada. O Adobe deriva cada dimensão de saída do último valor visto para essa variável durante a visita; não há nenhuma variável dedicada para definir. Se a variável de não saída tiver dados, sua dimensão de saída associada também terá dados. Nenhuma alteração na implementação é necessária para as dimensões de saída se suas variáveis de tráfego tiverem dados.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (derivado da última ocorrência do visitante) |
| **Web SDK / campo XDM** | Nenhum (derivado da última ocorrência do visitante) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | Visita |

## Itens de dimensão

Como as variáveis de saída normalmente se baseiam em strings personalizadas na sua implementação, sua organização determina quais são os itens de dimensão. Os valores de uma determinada dimensão de saída correspondem aos itens da sua dimensão de não saída associada. Por exemplo, os itens de dimensão na dimensão “Página de saída” contêm itens de dimensão semelhantes na dimensão “Página”.
