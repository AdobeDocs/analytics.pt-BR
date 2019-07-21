---
description: Define configurações comuns de um site que desenvolve conteúdo original e exibe artigos e vídeos.
seo-description: Define configurações comuns de um site que desenvolve conteúdo original e exibe artigos e vídeos.
seo-title: Conteúdo e mídia
solution: Analytics
title: Conteúdo e mídia
topic: Ferramentas administrativas
uuid: 281 b 0 bf 8-59 dc -46 dc-b 5 d 5-5 e 42827 b 785 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Conteúdo e mídia

Define configurações comuns de um site que desenvolve conteúdo original e exibe artigos e vídeos.

| Variáveis de conversão | Tipo | Sub-relações | Alocação | Expiração | `s_code` variável |
|---|---|---|---|---|---|
| Campanha interna | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar1` |
| Termos de pesquisa interna | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar2` |
| Variável de comércio 3 | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar3` |
| Variável de comércio 4 | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar4` |

| Eventos bem-sucedidos | Tipo | `s_code` variável |
|---|---|---|
| Registros | Contador (sem sub-relações) | `event1` |
| Registros por email | Contador (sem sub-relações) | `event2` |
| Assinaturas | Contador (sem sub-relações) | `event3` |
| Exibições de página | Contador (sem sub-relações) | `event4` |
| Impressões da publicidade | Contador (sem sub-relações) | `event5` |
| Cliques de anúncios | Contador (sem sub-relações) | `event6` |

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

