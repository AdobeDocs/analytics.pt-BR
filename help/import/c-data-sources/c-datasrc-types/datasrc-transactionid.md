---
title: Fontes de dados de ID de transação
description: Saiba mais sobre o fluxo de trabalho geral do uso de fontes de dados de ID de transação.
translation-type: ht
source-git-commit: c6f84f470dcf97f49ce7dc9d2c5dd8c65cc6cf67

---


# Fontes de dados de ID de transação

As fontes de dados de ID de transação permitem não apenas visualizar os dados online e offline lado a lado, mas também uni-los. Ela requer o uso da variável [`transactionID`](/help/implement/vars/page-vars/transactionid.md) na implementação do Analytics.

Ao enviar uma ocorrência online que contém um valor `transactionID`, a Adobe captura um &quot;instantâneo&quot; de todas as variáveis definidas ou persistentes no momento. Se uma ID de transação correspondente carregada por meio de Fontes de dados for encontrada, os dados offline e online serão vinculados. Não importa qual fonte de dados é vista primeiro.

## Fluxo de trabalho geral de fontes de dados de ID de transação

Use o fluxo de trabalho genérico a seguir para começar a usar fontes de dados de ID de transação:

1. Crie uma fonte de dados (categoria &quot;Genérica&quot; e tipo de &quot;Fonte de dados genérica (ID de transação)&quot;).
1. Siga o assistente de configuração do feed de dados para obter um local FTP para carregar dados e baixar um arquivo de modelo de fontes de dados.
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
