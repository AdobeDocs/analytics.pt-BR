---
description: Exibe os links preferidos dos visitantes de seu site. Por exemplo, a página inicial de seu site provavelmente terá diversos links que exibem a mesma página. Talvez haja tanto um link gráfico quanto um link de texto para a mesma página. Este relatório mostra qual porcentagem de visitantes usou o link gráfico e o link de texto.
title: Link personalizado
topic: Reports
uuid: 2e0d0175-d5e4-4919-b601-3f488ef3e090
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Link personalizado

Exibe os links preferidos dos visitantes de seu site. Por exemplo, a página inicial de seu site provavelmente terá diversos links que exibem a mesma página. Talvez haja tanto um link gráfico quanto um link de texto para a mesma página. Este relatório mostra qual porcentagem de visitantes usou o link gráfico e o link de texto.

Os links específicos que você gostaria que fossem rastreados devem ser modificados com tags especiais. Veja [Rastreamento de link](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html).

Você pode usar o [!UICONTROL Custom Links Report] para:

* Otimize o projeto de seu site sabendo que tipos de links seus visitantes preferem
* Valide a necessidade de links redundantes para páginas únicas

## Nomes de links SDK móveis {#section_70C91FE794104B5FBF289B19CC02EA8E}

Os [SDKs móveis](https://docs.adobe.com/content/help/pt-BR/mobile-services/using/home.html) utilizam links personalizados para rastrear ações e medições de ciclo de vida. Em conjuntos de relatórios usados para medir aplicativos móveis, é possível ver os seguintes nomes de links definidos pelo SDK:

| ADBINTERNAL:Lifecycle | Enviado pela chamada de ciclo de vida nos SDKs 4.x. |
|---|---|
| AMACTION:[action name] | Enviado pelo método trackAction() nos SDKs 4.x, onde o nome da ação é o nome que foi definido quando o método foi chamado. |
| Evento ADMS BP | Enviado pela chamada de ciclo de vida nos SDKs 3.x. |

