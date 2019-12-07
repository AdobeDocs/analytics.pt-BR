---
description: Define as configurações comuns para um site de comércio eletrônico.
title: Comércio
topic: Admin tools
uuid: 85fc235d-0180-4245-b831-0243ebe3c40c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Comércio

Define as configurações comuns para um site de comércio eletrônico.

| Variáveis de conversão | Tipo | Sub-relações | Alocação | Expiração | `s_code`variável |
|---|---|---|---|---|---|
| Promoções internas | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar1` |
| Termos de pesquisa interna | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar2` |
| Categoria de merchandising | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar3` |
| Variável de comércio 4 | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar4` |
| Variável de comércio 5 | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar5` |

| Eventos bem-sucedidos | Tipo | `s_code`variável |
|---|---|---|
| Registros | Contador (sem sub-relações) | `event1` |
| Eventos personalizados 1-5 | Contador (sem sub-relações) | `event1, event2, event3, event4, event5` |

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
| Visitantes únicos por dia | Contador (sem sub-relações) | N/D |
| Visitantes únicos | Contador (sem sub-relações) | N/D |

