---
title: Como as réplicas funcionam
description: Entenda o conceito de "reprodução" no Analytics entre dispositivos
translation-type: tm+mt
source-git-commit: 2230fa2c48358346d1d449f2db335ff75c6b1631
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 1%

---


# Como as réplicas funcionam

O Analytics entre dispositivos faz duas passagens de dados em um conjunto de relatórios virtual:

* **Arranque ao vivo**: O CDA tenta costurar cada ocorrência à medida que entra. Geralmente, novos dispositivos de rede para o conjunto de relatórios que nunca fizeram logon não são costurados neste nível. Os dispositivos já reconhecidos são imediatamente suturados.
* **Reproduzir**: Aproximadamente uma vez por semana, o CDA &quot;replica&quot; dados com base em identificadores únicos que ele aprendeu. Esse estágio é onde novos dispositivos do conjunto de relatórios se tornam costurados.

## Exemplo de tabela

As tabelas a seguir ilustram como ambos os métodos CDA (costura[baseada em](field-based-stitching.md) campo e gráfico [de](device-graph.md)dispositivo) calculam o número de pessoas exclusivas:

### costura ao vivo

Assim que uma ocorrência é coletada, o CDA tenta costurá-la em dispositivos conhecidos. Considere o exemplo a seguir, onde Bob usa dois dispositivos.

*Dados como aparecem no dia em que são coletados:*

| Carimbo de data e hora | ECID | eVar1 ou CustomerID | Explicação da ocorrência | Métrica de pessoas (cumulativa) usando o Gráfico de dispositivos | Métrica de pessoas (cumulativa) usando a costura baseada em campo |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob no seu computador desktop, não autenticado | `1` (246) | `1` (246) |
| `2` | `246` | `Bob` | Bob faz logon em seu desktop | `1` (246) | `2` (246 e Bob) |
| `3` | `3579` | - | Bob no seu dispositivo móvel, não autenticado | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `4` | `3579` | `Bob` | Bob faz logon no dispositivo móvel | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `5` | `246` | - | Bob acessa seu site novamente no desktop, não autenticado | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `6` | `246` | `Bob` | Bob faz logon novamente via desktop | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `7` | `3579` | - | Bob acessa seu site novamente em dispositivos móveis | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `8` | `3579` | `Bob` | Bob entra novamente via celular | `2` (246 e 3579) | `3` (246, Bob e 3579) |

As ocorrências não autenticadas e autenticadas em novos dispositivos são contadas como pessoas separadas (temporariamente).

* **Se estiver usando o gráfico de dispositivos,** as ocorrências não autenticadas em dispositivos reconhecidos serão colocadas em ponto ativo depois que um cluster for publicado pelo gráfico de dispositivos. A publicação em cluster leva de três horas a duas semanas.

   Uma terceira pessoa cumulativa também é adicionada quando um cluster é publicado. Essa terceira pessoa representa o próprio cluster, além dos dispositivos individuais. Este terceiro &quot;indivíduo&quot; permanece até que os dados sejam reproduzidos.

   A atribuição não funciona em dispositivos até que um cluster seja publicado e, mesmo assim, somente pontos ativos desse ponto em diante. No exemplo acima, nenhuma das ocorrências é costurada em dispositivos ainda. A atribuição entre dispositivos em ocorrências existentes não funciona até após a reapresentação da sutura.
* **Se estiver usando a sutura baseada em campo,** as ocorrências não autenticadas em dispositivos reconhecidos serão pontilhadas ao vivo a partir desse ponto.

   A atribuição funciona assim que a variável personalizada de identificação se vincula a um dispositivo. No exemplo acima, todas as ocorrências, exceto as 1 e 3, são pontilhadas ao vivo (todas usam o `Bob` identificador). A atribuição funciona nas ocorrências 1 e 3 após reproduzir a costura.

### Reproduzir pontilhamento

Aproximadamente uma vez por semana, o CDA recalcula os dados históricos com base nos dispositivos que agora reconhece. Se um dispositivo enviar dados inicialmente sem autenticação e fizer logon, o CDA vinculará essas ocorrências não autenticadas à pessoa correta. A tabela a seguir representa os mesmos dados acima, mas mostra números diferentes com base na reprodução dos dados.

*Os mesmos dados após a reprodução:*

| Carimbo de data e hora | ECID | eVar1 ou CustomerID | Explicação da ocorrência | Métrica de pessoas (cumulativa) usando o Gráfico de dispositivos | Métrica de pessoas (cumulativa) usando a costura baseada em campo |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob no seu computador desktop, não autenticado | `1` (Cluster1) | `1` (Bob) |
| `2` | `246` | `Bob` | Bob faz logon em seu desktop | `1` (Cluster1) | `1` (Bob) |
| `3` | `3579` | - | Bob no seu dispositivo móvel, não autenticado | `1` (Cluster1) | `1` (Bob) |
| `4` | `3579` | `Bob` | Bob faz logon no dispositivo móvel | `1` (Cluster1) | `1` (Bob) |
| `5` | `246` | - | Bob acessa seu site novamente no desktop, não autenticado | `1` (Cluster1) | `1` (Bob) |
| `6` | `246` | `Bob` | Bob faz logon novamente via desktop | `1` (Cluster1) | `1` (Bob) |
| `7` | `3579` | - | Bob acessa seu site novamente em dispositivos móveis | `1` (Cluster1) | `1` (Bob) |
| `8` | `3579` | `Bob` | Bob entra novamente via celular | `1` (Cluster1) | `1` (Bob) |

## Recap

* **Se estiver usando um Gráfico de dispositivos,** os dados são costurados quando um cluster é publicado (normalmente de 3 horas a 2 semanas).
* **Se estiver usando a sutura baseada em campo,** os dados com menos de uma semana imediatamente unirão os dispositivos conhecidos, mas não unirão imediatamente dispositivos novos ou não reconhecidos.
* Os dados são reproduzidos uma vez por semana e alteram os dados históricos no conjunto de relatórios virtual com base nos dispositivos que eles aprenderam a identificar.
