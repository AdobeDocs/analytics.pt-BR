---
description: Define configurações comuns para um site que fornece informações sobre serviços e produtos que normalmente são vendidos por meio de mais participação.
seo-description: Define configurações comuns para um site que fornece informações sobre serviços e produtos que normalmente são vendidos por meio de mais envolvimento.
seo-title: Geração de clientes potenciais
solution: Analytics
title: Geração de leads
topic: Ferramentas administrativas
uuid: e 7 d 3 cc 4 a -1 bee -4722-92 c 1-4454 f 7613 d 39
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Geração de leads

Define configurações comuns para um site que fornece informações sobre serviços e produtos que normalmente são vendidos por meio de mais participação.

| Variáveis de conversão | Tipo | Sub-relações | Alocação | Expiração | `s_code` variável |
|---|---|---|---|---|---|
| Promoção interna | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar1` |
| Termos de pesquisa interna | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar2` |
| Evento tipo self-service | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar3` |

Não há eventos bem-sucedidos configurados por este modelo de conjunto de relatórios.

| Variáveis de insight personalizado | `s_code` variável |
|---|---|
| Seguro/não seguro | `prop1` |
| Propriedade de tráfego 2 - 5 | `prop2, prop3, prop4, prop5` |

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

