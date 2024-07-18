---
title: Consentimento da plataforma de publicidade
description: Consulte a configuração para consentimento de publicidade para provedores de anúncios de terceiros.
feature: Dimensions
exl-id: bf63112d-7d20-4e35-9a59-5be21135ae51
source-git-commit: 5df5cffbb6abf712cb36fd807ef54b8ebaae1c73
workflow-type: tm+mt
source-wordcount: '331'
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
* Relatórios de Data Warehouse: os dados de consentimento do anúncio estão disponíveis usando a dimensão **[!UICONTROL Consentimento da plataforma de publicidade]**.

Sua organização determina a lógica para implementar essa variável de dados de contexto. O valor não persiste além da ocorrência à qual está definido, portanto, você deve definir a variável de dados de contexto em cada página.

Ao enviar dados de publicidade do Adobe Analytics via Adobe Advertising como eventos de conversão para o Google, consulte a equipe do Adobe Advertising para ajudar na integração.

Para obter mais informações, consulte [Relatórios de privacidade](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md).
