---
title: Fontes de dados de ID de transação
description: Saiba mais sobre o fluxo de trabalho geral do uso de fontes de dados de ID de transação.
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
source-git-commit: 4497ca252c4ee05175141e58d784ca2df215cb94
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 45%

---

# Fontes de dados de ID de transação

As fontes de dados de ID de transação permitem não apenas visualizar os dados online e offline lado a lado, mas também uni-los. Ela requer o uso da variável [`transactionID`](/help/implement/vars/page-vars/transactionid.md) na implementação do Analytics.

Ao enviar uma ocorrência online que contém um valor `transactionID`, a Adobe captura um &quot;instantâneo&quot; de todas as variáveis definidas ou persistentes no momento. Se uma ID de transação correspondente carregada por meio de Fontes de dados for encontrada, os dados offline e online serão vinculados.

Para usar as transações, a ocorrência online com uma ID de transação deve ter sido enviada e processada antes que qualquer fonte de dados da transação com essa ID de transação seja enviada. A ocorrência online contém variáveis (eVars etc.), mas não eventos, que estavam na ocorrência online salva com as informações da ID da transação.

Quando uma ocorrência da fonte de dados da transação é enviada para o , a ID da transação na ocorrência da transação da fonte de dados procura as vars etc. (não eventos) que foram associados à ocorrência online original com essa ID de transação. Ela usa essas vars na ocorrência da transação da fonte de dados, se não houver valor para uma variável transmitida na ocorrência da transação da fonte de dados.

## Exemplo

Se uma ocorrência online com ID de transação 1256 for transmitida e nela `evar1=blue`, `evar2=water` e `event1` forem definidas, os dados de transação da ID de transação 1256 serão salvos com `evar1=blue`, `evar2=water`. Nenhum valor de evento é salvo como parte das informações da transação.

Agora vamos supor que uma ocorrência de transação da fonte de dados seja passada pelo sistema com a ID de transação 1256 e `evar1=yellow`, `evar3=mountain` e `event2` definidas. O sistema encontra os dados da transação salvos e, nos conjuntos de ocorrências da transação da fonte de dados `evar2=water` (já que isso é o que foi definido na ocorrência original). Ele não define `evar1=blue` (como estava na ocorrência original) porque havia um valor para `evar1` (amarelo) já definido na ocorrência da transação da fonte de dados.  Portanto, a ocorrência da transação da fonte de dados resulta em ter `evar1=yellow`, `evar2=water` (da ocorrência online original) e `evar3=mountain`. Esses 3 valores de eVar têm `event2` definido - o evento da ocorrência de transação da fonte de dados.

Nenhum valor da ocorrência da transação da fonte de dados é definido `event1` quando a ocorrência da transação da fonte de dados é processada.

## Fluxo de trabalho geral de fontes de dados de ID de transação

Use o fluxo de trabalho genérico a seguir para começar a usar fontes de dados de ID de transação:

1. Crie uma fonte de dados (categoria &quot;Genérica&quot; e tipo de &quot;Fonte de dados genérica (ID de transação)&quot;).
1. Siga o assistente de configuração da fonte de dados para obter um local FTP para carregar dados e baixar um arquivo de modelo de fontes de dados.
1. Atualize a implementação para incluir a variável `transactionID`.
1. Faça o upload de um arquivo de fontes de dados no site FTP com um arquivo `.fin`.

## Exemplo de arquivo de upload e código de implementação

Se você fizesse upload do arquivo de fontes de dados a seguir e implementasse o seguinte código no site, você veria os dados vinculados no relatórios. O arquivo de fontes de dados usa eVar1 e evento1, enquanto a implementação online usa eVar2 e evento2. Como a ID de transação corresponde, você pode ver dados do evento2 para eVar1 e dados do evento1 para eVar2.

### Exemplo de arquivo

Baixe o modelo, atualize os valores e faça upload dele para o local FTP das fontes de dados:

| `#` | `Example eVar1 name` | `Example event 1 name` | `1` |
|---|---|---|---|
| `Date` | `Evar 1` | `Event 1` | `transactionID` |
| `01/01/2020/12/00/00` | `Example eVar1 value` | `1` | `1234` |

### Exemplo de código de implementação

Para obter uma explicação mais detalhada sobre ID de transação, consulte [`transactionID`](/help/implement/vars/page-vars/transactionid.md) no guia Implementação do usuário.

```js
var s = s_gi("examplersid");
s.eVar2 = "Example eVar2 value";
s.events = "event2";
s.transactionID = "1234";
s.t();
```
