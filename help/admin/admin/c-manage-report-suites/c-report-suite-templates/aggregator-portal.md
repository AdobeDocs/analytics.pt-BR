---
description: Define configurações comuns para um site que agrega conteúdo, como um portal de notícias.
title: Portal agregador
feature: Report Suite Settings
exl-id: 48f57f27-289c-4e26-9fb2-e34d48c1f2e6
source-git-commit: 9057cc83881a72fa039e9398ed3daaf4259ef2bf
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 100%

---

# Portal agregador

Define configurações comuns para um site que agrega conteúdo, como um portal de notícias.

| Variáveis de conversão | Tipo | Sub-relações | Alocação | Expiração | `s_code`variável |
|---|---|---|---|---|---|
| Campanha interna | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar1` |
| Termos de pesquisa interna | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar2` |
| Categoria de referência | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar3` |

| Eventos bem-sucedidos | Tipo | `s_code`variável |
|---|---|---|
| Entrar | Contador (sem sub-relações) | `event1` |
| Exibição de referência | Contador (sem sub-relações) | `event2` |
| Cliques de referência | Contador (sem sub-relações) | `event3` |

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
| Visualizações do carrinho | Contador | `scView` |
| Instâncias | Contador | N/D |
| Check-outs | Contador | `scCheckout` |
| Adições ao carrinho | Contador | `scAdd` |
| Remoções do carrinho | Contador | `scRemove` |
| Visitas | Contador (sem sub-relações) | N/D |
| Exibições de página | Contador (sem sub-relações) | N/D |
| Visitantes únicos diários | Contador (sem sub-relações) | N/D |
| Visitantes únicos | Contador (sem sub-relações) | N/D |
