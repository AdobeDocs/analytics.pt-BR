---
description: Define configurações comuns para um site que fornece informações sobre serviços e produtos que normalmente são vendidos por meio de mais engajamento.
title: Geração de leads
feature: Admin Tools
uuid: e7d3cc4a-1bee-4722-92c1-4454f7613d39
exl-id: 4a629908-2bb4-4d61-a934-42906edff9df
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 100%

---

# Geração de leads

Define configurações comuns para um site que fornece informações sobre serviços e produtos que normalmente são vendidos por meio de mais engajamento.

| Variáveis de conversão | Tipo | Sub-relações | Alocação | Expiração | `s_code`variável |
|---|---|---|---|---|---|
| Promoção interna | String | Básica | Mais recente (último) | Visita | `evar1` |
| Termos de pesquisa interna | String | Básica | Mais recente (último) | Visita | `evar2` |
| Evento tipo self-service | String | Básica | Mais recente (último) | Visita | `evar3` |

Não há eventos bem-sucedidos configurados por este modelo de conjunto de relatórios.

| Variáveis de Insight personalizado | `s_code`variável |
|---|---|
| Seguro/não seguro | `prop1` |
| Propriedade de tráfego 2 - 5 | `prop2, prop3, prop4, prop5` |

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
