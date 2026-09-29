---
title: ID de clique de anúncios do AMO Meta
description: A ID de cliques do Adobe Media Otimizer Meta Ads, usada em integrações do Adobe Advertising.
feature: Dimensions
exl-id: c1def73a-51b9-46bf-9dc7-0fbd46fd6e17
TQID: 'https://experienceleague.adobe.com/3J-pLiOz4QwUewRSmEFsJCg0v-PbEmksUzGKOI0hHoA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 7%
---
# ID de clique de anúncios do AMO Meta

A **[!UICONTROL ID de Clique do AMO Meta Ads]** é um identificador de clique de anúncio usado em integrações do Adobe Advertising. A dimensão é criada automaticamente ao habilitar a integração do [Analytics para Advertising](https://experienceleague.adobe.com/pt-br/docs/advertising/integrations/analytics/overview). É útil principalmente como um identificador de rastreamento bruto em vez de uma dimensão de relatório legível.

## Preencher esta dimensão com dados

Esta dimensão é preenchida automaticamente pela integração do [Analytics for Advertising](https://experienceleague.adobe.com/pt-br/docs/advertising/integrations/analytics/overview); não há variável para definir.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (preenchido pela integração do Adobe Advertising) |
| **Web SDK / campo XDM** | Nenhum (preenchido pela integração do Adobe Advertising) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | N/D |

Essa dimensão coleta seus valores de várias maneiras:

* Para o tráfego de click-through, os dados são coletados do parâmetro da sequência de consulta `fbclid` na [URL da página](page-url.md), geralmente na página pela qual o tráfego orientado por anúncio entra no site.
* O tráfego de click-through também pode ser capturado quando o URL não contém códigos de rastreamento, mas o Adobe Advertising JavaScript detecta um clique nos dois minutos anteriores.

## Itens de dimensão

Os itens do Dimension incluem identificadores de cliques em anúncios gerados pelas redes de publicidade do Meta (Facebook). Os comprimentos desses valores com hash podem variar, mas normalmente têm centenas de caracteres. Os valores de exemplo (truncados) incluem:

```text
IwY2xjawP0bVtleHRuA2FlbQIxMAB[...]AVp_aem_l5TPw-muraFjBGOq8l1w0g
PAb21jcAQB1LNleHRuA2FlbQIxMQB[...]PoFocE1FH44g_aem_FNMJG5EydJ_59aBwKIf4uA
```
