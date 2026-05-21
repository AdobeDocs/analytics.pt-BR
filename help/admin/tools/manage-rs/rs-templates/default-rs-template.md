---
description: Configura diversas variáveis comuns e eventos bem-sucedidos para um site típico.
title: Modelo padrão
feature: Report Suite Settings
uuid: edcf1b97-4ff2-4e98-b84c-199af2181d68
exl-id: 36aaded4-5c46-41af-a5c6-216bd2fcadb2
TQID: https://experienceleague.adobe.com/Tz2kROFW9n8apieb-bLIEPJ26LsZIhci5Azf1dvxRLI
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
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 205
ht-degree: 69%

---

# Modelo padrão

Configura diversas variáveis comuns e eventos bem-sucedidos para um site típico.

| Variáveis de conversão | Tipo | Sub-relações | Alocação | Expiração | `s_code`variável |
|---|---|---|---|---|---|
| Campanha interna | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar1` |
| Termos de pesquisa interna | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar2` |
| Variável 3 do Commerce | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar3` |
| Variável 4 do Commerce | Sequência de caracteres | Básica | Mais recente (último) | Visita | `evar4` |

| Eventos bem-sucedidos | Tipo | `s_code`variável |
|---|---|---|
| Registros | Contador (sem sub-relações) | `event1` |
| Registros de email | Contador (sem sub-relações) | `event2` |
| Subscrições | Contador (sem sub-relações) | `event3` |
| Exibições de página | Contador (sem sub-relações) | `event4` |
| Impressões do anúncio | Contador (sem sub-relações) | `event5` |
| Cliques de anúncio | Contador (sem sub-relações) | `event6` |

| Variáveis de Insight personalizado | `s_code`variável |
|---|---|
| Propriedade de tráfego 1 - 5 | `prop1, prop2, prop3, prop4, prop5` |

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
