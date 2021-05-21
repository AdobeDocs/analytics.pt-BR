---
title: Como funcionam as repetições
description: Entenda o conceito de “repetição” no Cross-Device Analytics
exl-id: 0b7252ff-3986-4fcf-810a-438d9a51e01f
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '589'
ht-degree: 100%

---

# Como funcionam as repetições

O Cross-Device Analytics faz duas passagens de dados em um conjunto de relatórios virtual:

* **Compilação em tempo real**: o CDA tenta compilar cada ocorrência à medida que elas chegam. Os novos dispositivos de rede para o conjunto de relatórios que nunca se conectaram normalmente não são compilados neste nível. Os dispositivos já reconhecidos são imediatamente compilados.
* **Repetições**: aproximadamente uma vez por semana, o CDA “repete” dados com base em identificadores exclusivos que aprendeu. É nesse estágio que os novos dispositivos do conjunto de relatórios são compilados.

## Tabela de exemplo

As tabelas a seguir ilustram como ambos os métodos do CDA ([Compilação em campo](field-based-stitching.md) e [Gráfico de dispositivos](device-graph.md)) calculam o número de pessoas únicas:

### Compilação em tempo real

Assim que uma ocorrência é coletada, o CDA tenta compilá-la em dispositivos conhecidos. Considere o exemplo a seguir, em que Bob usa dois dispositivos.

*Dados como aparecem no dia em que são coletados:*

| Carimbo de data e hora | ECID | eVar1 ou CustomerID | Explicação da ocorrência | Métrica Pessoas (cumulativa) usando o Gráfico de dispositivos | Métrica Pessoas (cumulativa) usando a Compilação em campo |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob no seu computador desktop, não autenticado | `1` (246) | `1` (246) |
| `2` | `246` | `Bob` | Bob faz logon em seu desktop | `1` (246) | `2` (246 e Bob) |
| `3` | `3579` | - | Bob no seu dispositivo móvel, não autenticado | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `4` | `3579` | `Bob` | Bob faz logon no dispositivo móvel | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `5` | `246` | - | Bob acessa seu site novamente no desktop, não autenticado | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `6` | `246` | `Bob` | Bob faz logon novamente via desktop | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `7` | `3579` | - | Bob acessa seu site novamente em um dispositivo móvel | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `8` | `3579` | `Bob` | Bob faz logon novamente via celular | `2` (246 e 3579) | `3` (246, Bob e 3579) |

As ocorrências não autenticadas e autenticadas em novos dispositivos são contadas como pessoas separadas (temporariamente).

* **Se estiver usando o gráfico de dispositivos**, as ocorrências não autenticadas em dispositivos reconhecidos serão colocadas em ponto ativo depois que um cluster for publicado pelo gráfico de dispositivos. A publicação em cluster leva de três horas a duas semanas.

   Uma terceira pessoa cumulativa também é adicionada quando um cluster é publicado. Essa terceira pessoa representa o próprio cluster, além dos dispositivos individuais. Este terceiro “indivíduo” permanece até que os dados sejam repetidos.

   A atribuição não funciona em dispositivos até que um cluster seja publicado e, mesmo assim, somente pontos ativos da publicação em diante. No exemplo acima, nenhuma das ocorrências é compilada em dispositivos ainda. A atribuição entre dispositivos em ocorrências existentes não funciona até após a repetição da compilação.
* **Se estiver usando a compilação em campo,** as ocorrências não autenticadas em dispositivos reconhecidos serão compiladas em tempo real a partir desse ponto.

   A atribuição funciona assim que a variável personalizada de identificação se vincula a um dispositivo. No exemplo acima, todas as ocorrências, exceto as 1 e 3, são compiladas em tempo real (todas usam o identificador `Bob`). A atribuição funciona nas ocorrências 1 e 3 após a repetição da compilação.

### Repetir a compilação

A repetição ocorre diariamente ou semanalmente, dependendo de como você solicitou a configuração do CDA. Durante a repetição, o CDA tenta reafirmar os dados históricos em uma janela de pesquisa definida:

* A repetição diária usa uma janela de pesquisa de 1 dia
* A repetição semanal usa uma janela de pesquisa de 7 dias.

Se um dispositivo enviar dados inicialmente sem autenticação e fizer logon, o CDA vinculará essas ocorrências não autenticadas à pessoa correta. A tabela a seguir representa os mesmos dados acima, mas mostra números diferentes com base na repetição dos dados.

*Os mesmos dados após a repetição:*

| Carimbo de data e hora | ECID | eVar1 ou CustomerID | Explicação da ocorrência | Métrica Pessoas (cumulativa) usando o Gráfico de dispositivos | Métrica Pessoas (cumulativa) usando a Compilação em campo |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob no seu computador desktop, não autenticado | `1` (Cluster1) | `1` (Bob) |
| `2` | `246` | `Bob` | Bob faz logon em seu desktop | `1` (Cluster1) | `1` (Bob) |
| `3` | `3579` | - | Bob no seu dispositivo móvel, não autenticado | `1` (Cluster1) | `1` (Bob) |
| `4` | `3579` | `Bob` | Bob faz logon no dispositivo móvel | `1` (Cluster1) | `1` (Bob) |
| `5` | `246` | - | Bob acessa seu site novamente no desktop, não autenticado | `1` (Cluster1) | `1` (Bob) |
| `6` | `246` | `Bob` | Bob faz logon novamente via desktop | `1` (Cluster1) | `1` (Bob) |
| `7` | `3579` | - | Bob acessa seu site novamente em um dispositivo móvel | `1` (Cluster1) | `1` (Bob) |
| `8` | `3579` | `Bob` | Bob faz logon novamente via celular | `1` (Cluster1) | `1` (Bob) |
