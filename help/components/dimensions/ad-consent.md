---
title: Consentimento da plataforma de publicidade
description: Consulte a configuração para consentimento de publicidade para provedores de anúncios de terceiros.
feature: Dimensions
exl-id: bf63112d-7d20-4e35-9a59-5be21135ae51
TQID: https://experienceleague.adobe.com/Ou6-B5pFx-ku9H2iEqLN0Ly6-t01CzQUODo0poMk8Bs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e0eb8757-182f-49f3-94a4-1587d16f5094id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 342
ht-degree: 3%

---

# Consentimento da plataforma de publicidade

A [dimensão](overview.md) de &#39;Consentimento da Plataforma de Anúncio&#39; exibe se o consentimento é coletado para enviar dados a provedores de publicidade de terceiros, como Google, Meta e outros.

Atualmente, essa dimensão é usada somente para o Google. Devido às regulamentações europeias de privacidade, a Lei de Mercados Digitais (DMA), a Google exige que os dados enviados a seus servidores e coletados na Europa indiquem se o consentimento é coletado. Alguns clientes do Analytics enviam dados do evento via Adobe Advertising como eventos de conversão para o Google.

No futuro, essa dimensão poderá ser usada para aceitar a codificação de informações de consentimento adicionais para outros provedores de publicidade de terceiros.

## Preencher esta dimensão com dados

Esta dimensão coleta dados das [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md) a seguir

* `contextData.['adConsent']`

Preencha a variável de dados de contexto com valores relevantes para os campos de consentimento do Google

* `ad_user_data` (primeiro caractere) e
* `ad_personalization` (segundo caractere).

Consulte [Consentimento na referência à API do Google Ads](https://developers.google.com/google-ads/api/reference/rpc/v15/Consent) para obter mais informações.

Os valores possíveis para cada um desses campos podem ser:

| Valor | ad_user_data | ad_personalization |
|:-:|---|---|
| `Y` | Conceder consentimento ao Google para dados de usuário de anúncio. | Conceder consentimento ao Google para personalização de anúncios. |
| `N` | Negar consentimento ao Google para dados de usuário de anúncio. | Denty consente com o Google para personalização de anúncios. |
| `U` | Não especificado. | Não especificado. |

O exemplo abaixo consente com o Google para dados de usuário de anúncio, mas não para personalização de anúncio:

```
contextData.['adConsent'] = "YN..."
```

Os caracteres além do primeiro e do segundo caracteres são ignorados no momento.

## Usar os dados

Você pode usar os dados de consentimento de anúncio coletados:

* Feeds de dados: os dados de consentimento do anúncio estão disponíveis na `dataprivacydmaconsent` [coluna](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md).
* Relatórios do Data Warehouse: os dados de consentimento do anúncio estão disponíveis usando a dimensão **[!UICONTROL Consentimento da plataforma de anúncio]**.

Sua organização determina a lógica para implementar essa variável de dados de contexto. O valor não persiste além da ocorrência à qual está definido, portanto, você deve definir a variável de dados de contexto em cada página.

Ao enviar dados de publicidade do Adobe Analytics via Adobe Advertising como eventos de conversão para o Google, consulte a equipe do Adobe Advertising para ajudar na integração.

Para obter mais informações, consulte [Relatórios de privacidade](/help/admin/tools/manage-rs/edit-settings/privacy-reporting.md).
