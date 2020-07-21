---
description: Exemplo contendo as chamadas do servidor enviadas em uma interação com cliente comum.
keywords: Analytics Implementation
subtopic: Visitors
title: Exemplo de identificação de visitante entre dispositivos
topic: Developer and implementation
uuid: bc5f8f56-52e3-42d8-af1a-7f5c7b9496c0
translation-type: tm+mt
source-git-commit: 9704267cd3ebf480facd68f6cca44167b1d9686d
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 100%

---


# Exemplo de identificação de visitante entre dispositivos

>[!IMPORTANT]
>
>Esse método de identificação de visitantes entre dispositivos não é mais recomendado. Consulte [Análise entre dispositivos](/help/components/cda/overview.md) no guia do usuário Componentes.

O exemplo a seguir ilustra como a identificação de visitantes entre dispositivos funciona usando uma amostra de chamadas de servidor enviadas em uma interação comum com o cliente.

| Chamada do servidor | Ação | Cookie da ID do visitante | Variável da ID do visitante | ID efetiva do visitante | Número de página da visita | Número da visita |
|--- |--- |--- |--- |--- |--- |--- |
| 1 | Um visitante clica em um link em um email de marketing e visita seu site, usando seu computador pessoal. Esse visitante já visitou o site 7 outras vezes no passado. | 1 | - | 1 | 1 | 8 |
| 2-8 | Visita 7 páginas adicionais no seu site. | 1 | - | 1 | 2-8 | 8 |
| 9 | Autentifica no computador pessoal. | 1 | CID1 | CID1 | 9 <br>(Este é o primeiro hit do CID1, por isso ele assume o controle e continua no perfil do visitante a partir da ID de visitante 1.) | 8 |
| 10 | Visita uma página adicional. | 1 | CID1 | CID1 | 10 | 8 |
| 11 | Abre o site em seu laptop, no escritório. O visitante não visitou o site antes de utilizar esse dispositivo. | 2 | - | 2 | 1 | 1 |
| 12 | Autentifica em laptop. | 2 | CID1 | CID1 | 1 | 9 |
| 13 | Visualiza 1 página adicional. | 2 | CID1 | CID1 | 2 | 9 |

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
