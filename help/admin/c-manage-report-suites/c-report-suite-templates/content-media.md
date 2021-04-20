---
description: Define configurações comuns de um site que desenvolve conteúdo original e exibe artigos e vídeos.
title: Conteúdo e mídia
feature: Admin Tools
uuid: 281b0bf8-59dc-46dc-b5d5-5e42827b785d
exl-id: 9983ff86-9341-4b01-b4f3-41042874a9fb
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 100%

---

# Conteúdo e mídia

Define configurações comuns de um site que desenvolve conteúdo original e exibe artigos e vídeos.

| Variáveis de conversão | Tipo | Sub-relações | Alocação | Expiração | `s_code`variável |
|---|---|---|---|---|---|
| Campanha interna | String | Básica | Mais recente (último) | Visita | `evar1` |
| Termos de pesquisa interna | String | Básica | Mais recente (último) | Visita | `evar2` |
| Variável de comércio 3 | String | Básica | Mais recente (último) | Visita | `evar3` |
| Variável de comércio 4 | String | Básica | Mais recente (último) | Visita | `evar4` |

| Eventos bem-sucedidos | Tipo | `s_code`variável |
|---|---|---|
| Registros | Contador (sem sub-relações) | `event1` |
| Registros por email | Contador (sem sub-relações) | `event2` |
| Assinaturas | Contador (sem sub-relações) | `event3` |
| Exibições de página | Contador (sem sub-relações) | `event4` |
| Impressões da publicidade | Contador (sem sub-relações) | `event5` |
| Cliques de anúncios | Contador (sem sub-relações) | `event6` |

| Variáveis de Insight personalizado | `s_code`variável |
|---|---|
| Propriedade de tráfego 1 - 5 | `prop1, prop2, prop3, prop4, prop5` |

A seguinte tabela contém uma lista de eventos padrão de comércio. A configuração inicial desses eventos é idêntica em todos os modelos de conjunto de relatórios. Os eventos com uma variável s_code de N/A não precisam ser definidos, eles serão fornecidos automaticamente.

| Eventos padrão de comércio | Tipo | `s_code`variável |
|---|---|---|
| Receita | Contador | `purchase` |
| Pedidos | Contador | `purchase` |
| Unidades | Contador | `purchase` |
| Carrinhos | Contador | `scOpen` |
| Exibições do carrinho | Contador | `scView` |
| Instâncias | Contador | N/D |
| Finalizações | Contador | `scCheckout` |
| Adições ao carrinho | Contador | `scAdd` |
| Remoções do carrinho | Contador | `scRemove` |
| Visitas | Contador (sem sub-relações) | N/D |
| Exibições de página | Contador (sem sub-relações) | N/D |
| Visitantes únicos diários | Contador (sem sub-relações) | N/D |
| Visitantes únicos | Contador (sem sub-relações) | N/D |
