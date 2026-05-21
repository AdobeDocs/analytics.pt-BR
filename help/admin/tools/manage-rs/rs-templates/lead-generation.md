---
description: Define configurações comuns para um site que fornece informações sobre serviços e produtos que normalmente são vendidos por meio de mais engajamento.
title: Geração de leads
feature: Report Suite Settings
exl-id: 4a629908-2bb4-4d61-a934-42906edff9df
TQID: https://experienceleague.adobe.com/bgxn4yp6AJj2DHGnztM3cdIE5e1a8JX0C1O11VB-fLk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2:
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 196
ht-degree: 67%

---

# Geração de leads

Define configurações comuns para um site que fornece informações sobre serviços e produtos que normalmente são vendidos por meio de mais engajamento.

| Variáveis de conversão | Tipo | Sub-relações | Alocação | Expiração | `s_code`variável |
|---|---|---|---|---|---|
| Promoção interna | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar1` |
| Termos de pesquisa interna | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar2` |
| Tipo de Evento de Autoatendimento | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar3` |

Nenhum evento bem-sucedido está configurado por este modelo de conjunto de relatórios.

| Variáveis de Insight personalizado | `s_code`variável |
|---|---|
| Seguro/não seguro | `prop1` |
| Propriedade de tráfego 2 - 5 | `prop2, prop3, prop4, prop5` |

A tabela a seguir contém uma lista dos eventos padrão de comércio. A configuração inicial desses eventos é idêntica em todos os modelos de conjunto de relatórios. Eventos com uma variável s_code de N/D não precisam ser definidos, eles são fornecidos automaticamente.

| Eventos padrão do Commerce | Tipo | `s_code`variável |
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
