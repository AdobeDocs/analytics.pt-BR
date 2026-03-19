---
title: ID de clique de anúncios Meta do AMO
description: A ID de cliques do Adobe Media Otimizer Meta Ads, usada em integrações do Adobe Advertising.
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 10%

---

# ID de clique de anúncios Meta do AMO

A **[!UICONTROL ID de Clique do AMO Meta Ads]** é um identificador de clique de anúncio usado em integrações do Adobe Advertising. A dimensão é criada automaticamente ao habilitar a integração do [Analytics para Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview). É útil principalmente como um identificador de rastreamento bruto em vez de uma dimensão de relatório legível.

## Preencher esta dimensão com dados

Essa dimensão coleta seus valores de várias maneiras:

* Para o tráfego de click-through, os dados são coletados do parâmetro da sequência de consulta `fbclid` na [URL da página](page-url.md), geralmente na página pela qual o tráfego orientado por anúncio entra no site.
* O tráfego de click-through também pode ser capturado quando o URL não contém códigos de rastreamento, mas o Adobe Advertising JavaScript detecta um clique nos dois minutos anteriores.

## Itens de dimensão

Os itens do Dimension incluem identificadores de cliques em anúncios gerados pelas redes de publicidade do Meta (Facebook). Os comprimentos desses valores com hash podem variar, mas normalmente têm centenas de caracteres. Os valores de exemplo (truncados) incluem:

```text
IwY2xjawP0bVtleHRuA2FlbQIxMAB[...]AVp_aem_l5TPw-muraFjBGOq8l1w0g
PAb21jcAQB1LNleHRuA2FlbQIxMQB[...]PoFocE1FH44g_aem_FNMJG5EydJ_59aBwKIf4uA
```
