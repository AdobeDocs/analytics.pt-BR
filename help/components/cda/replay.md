---
title: Como funcionam as repetições
description: Entenda o conceito de “repetição” no Cross-Device Analytics
exl-id: 0b7252ff-3986-4fcf-810a-438d9a51e01f
feature: CDA
role: Admin
source-git-commit: f75a1f6d9f08f422595c24760796abf0f8332ddb
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 89%

---

# Como funcionam as repetições

{{available-existing-customers}}

O Cross-Device Analytics faz duas passagens de dados em um conjunto de relatórios virtual:

* **Compilação em tempo real**: o CDA tenta compilar cada ocorrência à medida que elas chegam. Os novos dispositivos de rede para o conjunto de relatórios que nunca se conectaram normalmente não são compilados neste nível. Os dispositivos já reconhecidos são imediatamente compilados.
* **Repetições**: aproximadamente uma vez por semana, o CDA “repete” dados com base em identificadores exclusivos que aprendeu. É nesse estágio que os novos dispositivos do conjunto de relatórios são compilados.

## Tabela de exemplo

As tabelas a seguir ilustram como a ([Compilação em campo](field-based-stitching.md) calcula o número de pessoas únicas:

### Compilação em tempo real

Assim que uma ocorrência é coletada, o CDA tenta compilá-la em dispositivos conhecidos. Considere o exemplo a seguir, em que Bob usa dois dispositivos.

*Dados como aparecem no dia em que são coletados:*

| Carimbo de data e hora | ECID | eVar1 ou CustomerID | Explicação da ocorrência | Métrica Pessoas (cumulativa) usando a compilação em campo |
| --- | --- | --- | --- | --- | 
| `1` | `246` | - | Bob no seu computador desktop, não autenticado | `1` (246) |
| `2` | `246` | `Bob` | Bob faz logon em seu desktop | `2` (246 e Bob) |
| `3` | `3579` | - | Bob no seu dispositivo móvel, não autenticado | `2` (246 e 3579) | `3` (246, Bob e 3579) |
| `4` | `3579` | `Bob` | Bob faz logon no dispositivo móvel | `3` (246, Bob e 3579) |
| `5` | `246` | - | Bob acessa seu site novamente no desktop, não autenticado | | `3` (246, Bob e 3579) |
| `6` | `246` | `Bob` | Bob faz logon novamente via desktop | `3` (246, Bob e 3579) |
| `7` | `3579` | - | Bob acessa seu site novamente em um dispositivo móvel | `3` (246, Bob e 3579) |
| `8` | `3579` | `Bob` | Bob faz logon novamente via celular | `3` (246, Bob e 3579) |

As ocorrências não autenticadas e autenticadas em novos dispositivos são contadas como pessoas separadas (temporariamente).
As ocorrências não autenticadas em dispositivos reconhecidos são compiladas em tempo real a partir desse ponto. A atribuição funciona assim que a variável personalizada de identificação se vincula a um dispositivo. No exemplo acima, todas as ocorrências, exceto as 1 e 3, são compiladas em tempo real (todas usam o identificador `Bob`). A atribuição funciona nas ocorrências 1 e 3 após a repetição da compilação.

>[!NOTE]
>
>As ocorrências com carimbo de data e hora com mais de 12 horas não são compiladas no fluxo ativo. No entanto, essas ocorrências são incluídas na repetição da compilação, desde que estejam na janela de retrospectiva de repetição.

### Repetir a compilação

A repetição ocorre diariamente ou semanalmente, dependendo de como você solicitou a configuração do CDA. Durante a repetição, o CDA tenta reafirmar os dados históricos em uma janela de pesquisa definida:

* A repetição diária usa uma janela de pesquisa de 1 dia
* A repetição semanal usa uma janela de pesquisa de 7 dias.

Se um dispositivo enviar dados inicialmente sem autenticação e fizer logon, o CDA vinculará essas ocorrências não autenticadas à pessoa correta. A tabela a seguir representa os mesmos dados acima, mas mostra números diferentes com base na repetição dos dados.

*Os mesmos dados após a repetição:*

| Carimbo de data e hora | ECID | eVar1 ou CustomerID | Explicação da ocorrência | Métrica Pessoas (cumulativa) usando a compilação em campo |
| --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob no seu computador desktop, não autenticado | `1` (Bob) |
| `2` | `246` | `Bob` | Bob faz logon em seu desktop | `1` (Bob) |
| `3` | `3579` | - | Bob no seu dispositivo móvel, não autenticado | `1` (Bob) |
| `4` | `3579` | `Bob` | Bob faz logon no dispositivo móvel | `1` (Bob) |
| `5` | `246` | - | Bob acessa seu site novamente no desktop, não autenticado | `1` (Bob) |
| `6` | `246` | `Bob` | Bob faz logon novamente via desktop | `1` (Bob) |
| `7` | `3579` | - | Bob acessa seu site novamente em um dispositivo móvel | `1` (Bob) |
| `8` | `3579` | `Bob` | Bob faz logon novamente via celular | `1` (Bob) |
