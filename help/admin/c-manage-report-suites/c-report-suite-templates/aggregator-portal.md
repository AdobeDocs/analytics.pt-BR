---
description: Define configurações comuns para um site que agrega conteúdo, como um portal de notícias.
seo-description: Define configurações comuns para um site que agrega conteúdo, como um portal de notícias.
seo-title: Portal do Aggregator
solution: Analytics
title: Portal do Aggregator
topic: Ferramentas administrativas
uuid: d 227 c 209-4 d 88-4 eff-b 126-994 b 2 a 179 c 51
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Portal do Aggregator

Define configurações comuns para um site que agrega conteúdo, como um portal de notícias.

| Variáveis de conversão | Tipo | Sub-relações | Alocação | Expiração | `s_code` variável |
|---|---|---|---|---|---|
| Campanha interna | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar1` |
| Termos de pesquisa interna | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar2` |
| Categoria de referência | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar3` |

| Eventos bem-sucedidos | Tipo | `s_code` variável |
|---|---|---|
| Entrar | Contador (sem sub-relações) | `event1` |
| Exibição de referência | Contador (sem sub-relações) | `event2` |
| Cliques de referência | Contador (sem sub-relações) | `event3` |

| Variáveis de insight personalizado | `s_code` variável |
|---|---|
| Propriedade de tráfego 1 - 5 | `prop1, prop2, prop3, prop4, prop5` |

A seguinte tabela contém uma lista de eventos padrão de comércio. A configuração inicial desses eventos é idêntica em todos os modelos de conjunto de relatórios. Os eventos com uma variável s_code de N/A não precisam ser definidos, eles serão fornecidos automaticamente.

| Eventos padrão de comércio | Tipo | `s_code` variável |
|---|---|---|
| Receita | Contador | `purchase` |
| Pedidos | Contador | `purchase` |
| Unidades | Contador | `purchase` |
| Carrinhos | Contador | `scOpen` |
| Exibições do carrinho | Contador | `scView` |
| Instâncias | Contador | N/A |
| Finalizações | Contador | `scCheckout` |
| Adições ao carrinho | Contador | `scAdd` |
| Remoções do carrinho | Contador | `scRemove` |
| Visitas | Contador (sem sub-relações) | N/A |
| Exibições de página | Contador (sem sub-relações) | N/A |
| Visitantes únicos por dia | Contador (sem sub-relações) | N/A |
| Visitantes únicos | Contador (sem sub-relações) | N/A |

