---
description: Define configurações comuns para bancos e outras instituições que fornecem acesso a serviços online.
seo-description: Define configurações comuns para bancos e outras instituições que fornecem acesso a serviços online.
seo-title: Serviços financeiros
solution: Analytics
title: Serviços financeiros
topic: Ferramentas administrativas
uuid: a321b409-24a4-4d9f-9aac-65761261e991
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Serviços financeiros

Define configurações comuns para bancos e outras instituições que fornecem acesso a serviços online.

| Variáveis de conversão (eVars) | Tipo | Sub-relações | Alocação | Expiração | `s_code` variable |
|---|---|---|---|---|---|
| Promoção interna | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar1` |
| Termos de pesquisa interna | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar2` |
| Evento tipo self-service | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar3` |

Não há eventos bem-sucedidos configurados por este modelo de conjunto de relatórios.

| Variáveis de insight personalizado | `s_code` variable |
|---|---|
| Seguro/não seguro | `prop1` |
| Propriedade de tráfego 2 - 5 | `prop2, prop3, prop4, prop5` |

A seguinte tabela contém uma lista de eventos padrão de comércio. A configuração inicial desses eventos é idêntica em todos os modelos de conjunto de relatórios. Os eventos com uma variável s_code de N/A não precisam ser definidos, eles serão fornecidos automaticamente.

| Eventos padrão de comércio | Tipo | `s_code` variable |
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

