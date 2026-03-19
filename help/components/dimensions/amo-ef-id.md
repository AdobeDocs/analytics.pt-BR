---
title: AMO EF ID
description: A ID EF do Adobe Media Otimizer, usada em integrações do Adobe Advertising.
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 4%

---

# AMO EF ID

A **[!UICONTROL ID EF AMO]** é um identificador de clique de anúncio usado em integrações do Adobe Advertising. É um token exclusivo que o Adobe Advertising usa para associar a atividade a uma exposição a cliques ou anúncios online em nível de visitante. A dimensão é criada automaticamente ao habilitar a integração do [Analytics para Advertising](https://experienceleague.adobe.com/pt-br/docs/advertising/integrations/analytics/overview).

## Preencher esta dimensão com dados

Essa dimensão coleta seus valores de várias maneiras:

* Para o tráfego de click-through, os dados são coletados do parâmetro da sequência de consulta `ef_id` na [URL da página](page-url.md), geralmente na página pela qual o tráfego orientado por anúncio entra no site.
* O tráfego de click-through também pode ser capturado quando o URL não contém códigos de rastreamento, mas o Adobe Advertising JavaScript detecta um clique nos dois minutos anteriores.
* Para tráfego de view-through com suporte, o Adobe Advertising complementa os valores no back-end usando uma ID complementar (`SDID`).

>[!NOTE]
>
>EF IDs fazem distinção entre maiúsculas e minúsculas. Se a sua implementação forçar o rastreamento de URL em minúsculas, a Adobe Advertising não reconhecerá a ID EF.

## Itens de dimensão

Os itens do Dimension incluem identificadores de cliques em anúncios gerados por redes de publicidade compatíveis. O formato da string depende da rede e do canal que a gerou.

### Anúncios de pesquisa do Google Ads

```text
{gclid}:G:{s}
```

* **`gclid`**: O ID de cliques do Google (GCLID).
* **`s`**: O tipo de rede (`"s"` para pesquisa).

### Anúncios de pesquisa do Microsoft Advertising

```text
{msclkid}:G:{s}
```

* **`msclkid`**: A ID de cliques do Microsoft (MSCLKID).
* **`s`**: O tipo de rede (`"s"` para pesquisa).

### Exibir anúncios e anúncios de pesquisa em outros mecanismos de pesquisa

```text
{amovid}:{ts}:{channel}
```

* **`amovid`**: a ID de visitante do Adobe Advertising, também conhecida como ID do surfer.
* **`ts`**: O carimbo de data/hora gerado pelo Adobe Advertising.
* **`channel`**: O tipo de canal responsável pelo clique ou exposição:
   * **`d`**: Um clique em um anúncio de exibição do DSP (click-through de exibição).
   * **`i`**: Uma impressão em um anúncio de exibição do DSP (view-through de exibição).
   * **`s`**: Um clique em um anúncio de pesquisa (click-through de pesquisa).

### Exemplos

```text
CjwKCAiAkbbMBhB2EiwANbxtbb9L573Dys0rjTDqcMo3x7tv2yEfh1RGb8exG9N892NoMqAzMBEGmhoCWxwQAvD_BwE:G:s
06207ca63ae6f4fa832197585547393c:20260301111101:i
WcmibgAAAHJK1RyY:1551968087687:d
```
