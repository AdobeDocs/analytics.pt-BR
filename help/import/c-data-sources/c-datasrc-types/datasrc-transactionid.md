---
title: Fontes de dados de ID de transação
description: Saiba mais sobre o fluxo de trabalho geral do uso de fontes de dados de ID de transação.
translation-type: tm+mt
source-git-commit: c54704bef49a2c3076caac6fe7dd3ec8d40596ef

---


# Fontes de dados de ID de transação

As fontes de dados da ID de transação permitem que você visualize dados online e offline lado a lado, mas vincule os dados juntos. Ela requer o uso da [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variável na implementação do Analytics.

Quando você envia uma ocorrência on-line que contém um `transactionID` valor, a Adobe captura um &quot;instantâneo&quot; de todas as variáveis definidas ou persistentes no momento. Se uma ID de transação correspondente carregada por meio das Fontes de Dados for encontrada, os dados offline e online serão vinculados. Não importa qual fonte de dados é vista primeiro.

## Fluxo de trabalho geral das fontes de dados da ID de transação

Use o fluxo de trabalho genérico a seguir para começar a usar fontes de dados da ID de transação:

1. Crie uma fonte de dados (categoria &quot;Genérica&quot; e tipo &quot;Fonte de Dados Genérica (ID de Transação)&quot;).
1. Siga o assistente de configuração do feed de dados para obter um local FTP para carregar dados e baixar um arquivo de modelo de fontes de dados.
1. Atualize sua implementação para incluir a `transactionID` variável.
1. Carregue um arquivo de fontes de dados no site FTP com um `.fin` arquivo.

## Exemplo de arquivo de upload e código de implementação

Se você carregasse o arquivo de fontes de dados a seguir e implementasse o seguinte código no site, você veria os dados vinculados no relatório. O arquivo de fontes de dados usa eVar1 e event1, enquanto a implementação online usa eVar2 e event2. Como a ID de transação corresponde, você pode ver os dados event2 para eVar1 e event1 para eVar2.

### Exemplo de arquivo

Baixe o modelo, atualize os valores e faça upload dele para o local FTP das fontes de dados:

| `# Generic Data Source (Transaction ID) template file (user: 0 ds_id: 1)` |  |  |  |
|---|---|---|---|
| `#` | `Example eVar1 name` | `Example event 1 name` | `1` |
| `Date` | `Evar 1` | `Event 1` | `transactionID` |
| `01/01/2020/12/00/00` | `Example eVar1 value` | `1` | `1234` |

### Exemplo de código de implementação

Para obter uma explicação mais detalhada sobre a ID de transação, consulte [`transactionID`](/help/implement/vars/page-vars/transactionid.md) No guia Implementação do usuário.

```js
var s = s_gi("examplersid");
s.eVar2 = "Example eVar2 value";
s.events = "event2";
s.transactionID = "1234";
s.t();
```
