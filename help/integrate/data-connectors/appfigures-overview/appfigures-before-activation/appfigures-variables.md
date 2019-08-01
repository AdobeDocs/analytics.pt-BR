---
description: A integração de conectores de dados para appfigures usa variáveis do Analytics para rastrear várias métricas do appfigures.
seo-description: A integração de conectores de dados para appfigures usa variáveis do Analytics para rastrear várias métricas do appfigures.
seo-title: Variáveis de integração do Analytics
title: Variáveis de integração do Analytics
uuid: 08 d 5 b 714-1 c 97-4 be 6-aae 8-1 f 8192535425
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Analytics Integration Variables{#analytics-integration-variables}

A integração de conectores de dados para appfigures usa variáveis do Analytics para rastrear várias métricas do appfigures.

A tabela a seguir descreve as variáveis do Analytics ativadas automaticamente pela integração appfigures.

## Required Variables {#section-3ca8dc46bab0436cba0c9ef827c8356a}

>[!NOTE]
>
>Essa integração usa variáveis dedicadas para os dados da app store, de modo que você não precisa atribuir variáveis e eventos de comércio personalizados.

| Tipo de variável | Nome | Método de preenchimento | Descrição |
|---|---|---|---|
| eVar | ID do objeto da App Store | Importado do appfigures. | Configurar esta evar com a expiração da visita, a alocação mais recente e as sub-relações básicas. |
| event (numérico) | Downloads da App Store | Importado do appfigures. | O número de downloads de aplicativos para dispositivos móveis. |
| event (numérico) | Compras da App Store (no aplicativo) | Importado do appfigures. | O número de compras e assinaturas no aplicativo. |
| event (numérico) | Classificação na AppStore | Importado do appfigures. | Usado para definir a Métrica calculada Média de appfigures. Não usado diretamente. |
| event (numérico) | Divisor de classificação da App Store | Importado do appfigures. | Usado para definir a Métrica calculada Média de appfigures. Não usado diretamente. |
| event (numérico) | Classificação na App Store | Importado do appfigures. | Usado para definir a Métrica calculada Média de appfigures. Não usado diretamente. |
| event (numérico) | Divisor de classificação da App Store | Importado do appfigures. | Usado para definir a Métrica calculada Média de appfigures. Não usado diretamente. |
| event (moeda) | Receita da App Store (no aplicativo) | Importado do appfigures. | A quantidade de receita no aplicativo menos a taxa da loja. |
| event (moeda) | Receita da App Store (uma desligada) | Importado do appfigures. | A receita total das compras do aplicativo menos a taxa da loja. |
| event (moeda) | Royalties da App Store (no aplicativo) | Importado do appfigures. | Não usado |
| event (moeda) | Royalties da App Store (um desligado) | Importado do appfigures. | Não usado |

