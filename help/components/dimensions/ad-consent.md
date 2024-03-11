---
title: Consentimento de publicidade
description: Consulte a configuração para consentimento de publicidade para provedores de anúncios de terceiros.
feature: Dimensions
source-git-commit: 31f61c64fef707e2d2499b853a9b54caf847634b
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 1%

---

# Consentimento de publicidade

O &#39;Consentimento do anúncio&#39; [dimension](overview.md) exibe se o consentimento é coletado para enviar dados a provedores de publicidade de terceiros, como Google, Meta e outros.

Atualmente, essa dimensão é usada somente para o Google. Devido às regulamentações europeias de privacidade, a Lei de Mercados Digitais (DMA), a Google exige que os dados enviados a seus servidores e coletados na Europa indiquem se o consentimento é coletado. Alguns clientes do Analytics enviam dados do evento via Adobe Advertising como eventos de conversão para o Google.

No futuro, essa dimensão poderá ser usada para suportar a codificação de informações de consentimento adicionais para outros provedores de publicidade de terceiros.


## Preencher esta dimensão com dados

Essa dimensão coleta dados dos seguintes [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md)

* `contextData.['adConsent']`

Preencha a variável de dados de contexto com valores relevantes para os campos de consentimento do Google

* `ad_user_data` (primeiro caractere) e
* `ad_personalization` (segundo caractere).

Consulte [Consentimento na referência da API do Google Ads](https://developers.google.com/google-ads/api/reference/rpc/v15/Consent) para obter mais informações.

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

* Feeds de dados: os dados de consentimento do anúncio estão disponíveis usando o `dataprivacydmaconsent` [coluna](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md).
* Relatórios do Data Warehouse: os dados de consentimento do anúncio estão disponíveis usando o **[!UICONTROL Consentimento da plataforma de publicidade]** dimensão.


Sua organização determina a lógica para implementar essa variável de dados de contexto. O valor não persiste além da ocorrência à qual está definido, portanto, você deve definir a variável de dados de contexto em cada página.

Ao enviar dados de publicidade do Adobe Analytics via Adobe Advertising como eventos de conversão para o Google, consulte a equipe do Adobe Advertising para ajudar na integração.
