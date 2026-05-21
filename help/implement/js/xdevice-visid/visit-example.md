---
description: Exemplo contendo as chamadas do servidor enviadas em uma interação com cliente comum.
keywords: Implementação do Analytics
subtopic: Visitors
title: Exemplo de identificação de visitante entre dispositivos
feature: Implementation Basics
exl-id: c68bb745-29de-48e3-8731-d714503a2447
role: Developer
TQID: https://experienceleague.adobe.com/ZYFxZyY5ZzmM064d2vx-8Ek-LftVwhxSsvLkzE9mgCI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 386
ht-degree: 77%

---

# Exemplo de identificação de visitante entre dispositivos

>[!IMPORTANT]
>
>Esse método de identificação de visitantes entre dispositivos não é mais recomendado. Consulte [Cross-Device Analytics](/help/components/cda/overview.md) no guia do usuário de Componentes.

O exemplo a seguir ilustra como a identificação de visitantes entre dispositivos funciona usando uma amostra de chamadas de servidor enviadas em uma interação comum com o cliente.

| Chamada de servidor | Ação | Cookie da ID de visitante | Variável de ID de visitante | ID efetiva do visitante | Número de visitas à página | Número da visita |
|--- |--- |--- |--- |--- |--- |--- |
| 1 | Um visitante clica em um link em um email de marketing e visita seu site do computador doméstico. Este visitante visitou o site 7 outras vezes no passado. | 1 | - | 1 | 1 | 8 |
| 2-8 | Visita 7 páginas adicionais em seu site. | 1 | - | 1 | 2-8 | 8 |
| 9 | É autenticado no computador doméstico. | 1 | CID1 | CID1 | 9 <br>(Este é o primeiro hit do CID1, por isso ele assume o controle e continua no perfil do visitante a partir da ID de visitante 1.) | 8 |
| 10 | Visita 1 página adicional. | 1 | CID1 | CID1 | 10 | 8 |
| 11 | Abre o site a partir do laptop no escritório. Este visitante não visitou o site antes de usar este dispositivo. | 2 | - | 2 | 1 | 1 |
| 12 | É autenticado no laptop. | 2 | CID1 | CID1 | 1 | 9 |
| 13 | Visualizações 1 página adicional. | 2 | CID1 | CID1 | 2 | 9 |

## Contagem de visitas

O Analytics conta uma visita sempre que encontra uma ocorrência com um número de página de visita igual a 1.

Usando a tabela acima, uma nova visita foi contada 4 vezes: nas ocorrências 1, 9, 11 e 12.

## Contagem de visitantes

O Analytics conta cada ID de visitante efetivo exclusivo como visitante único.

Usando a tabela acima, um novo visitante foi contado 3 vezes: nas ocorrências 1, 9 e 10.

Ao usar a identificação de visitantes entre dispositivos, a quantidade de visitantes únicos exibida pode aumentar. O visitante pode ser contado duas vezes na mesma visita: uma para a visita inicial e novamente depois que o usuário é autenticado.

![](assets/visitors.png)

Depois da associação inicial, as contagens de visita retornam ao normal, pois o visitante é associado por meio do cookie do navegador. Se posteriormente o visitante exibir seu site e se autenticar, a contagem de visitantes não será aumentada, pois a ID de visitante efetiva não é alterada após a autenticação.

![](assets/visitors_2.png)

Certifique-se de ser o mais consistente possível ao identificar visitantes únicos. Por exemplo, sempre use a variável `visitorID` quando o usuário estiver autenticado.
