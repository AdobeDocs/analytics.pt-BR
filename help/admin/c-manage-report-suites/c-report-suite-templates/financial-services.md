---
description: Define configurações comuns para bancos e outras instituições que fornecem acesso a serviços online.
title: Serviços financeiros
feature: Admin Tools
uuid: a321b409-24a4-4d9f-9aac-65761261e991
exl-id: 2ab435e2-3fc7-46f9-aee9-961f6730f3e8
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 100%

---

# Serviços financeiros

Define configurações comuns para bancos e outras instituições que fornecem acesso a serviços online.

| Variáveis de conversão (eVars) | Tipo | Sub-relações | Alocação | Expiração | `s_code`variável |
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
