---
title: Tipos de sistema operacional
description: O sistema operacional independentemente da versão.
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
TQID: 'https://experienceleague.adobe.com/onZ7Wt7A44gd42hqmjqYHL7OF6VtBke1NDgu1tsnMIg'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
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
source-wordcount: '165'
ht-degree: 40%
---
# Tipos de sistema operacional

A [dimensão](overview.md) de &#39;Tipos de sistema operacional&#39; mostra o SO abrangente que o visitante usou, independentemente de versões específicas. Essa dimensão é útil para entender não apenas qual sistema operacional e versão específicos são mais comuns, mas qual plataforma de SO típica os visitantes usam.

## Preencher esta dimensão com dados

A Adobe deriva essa dimensão do cabeçalho HTTP `User-Agent`, comparando-a com uma tabela de pesquisa interna que a Adobe mantém em parceria com o [DeviceAtlas](https://deviceatlas.com/). Não há variável a ser definida.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (derivado do agente do usuário) |
| **Web SDK / campo XDM** | Nenhum (derivado do agente do usuário) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | N/D |

* Para implementações do AppMeasurement, essa dimensão funciona imediatamente.
* Para implementações do Web SDK, habilite a [!UICONTROL Pesquisa de Dispositivo] ao [configurar uma sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-BR).

## Itens de dimensão

Os itens do Dimension incluem o tipo de sistema operacional usado. Os exemplos incluem `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"` e `"Apple iOS"`.
