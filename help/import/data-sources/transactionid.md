---
title: Fontes de dados de ID de transação
description: Saiba mais sobre o fluxo de trabalho geral do uso de fontes de dados de ID de transação.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
role: Admin
source-git-commit: e281d43204e1c5b10508661f04b880125fe8671c
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 7%

---

# Fontes de dados de ID de transação

As fontes de dados de ID de transação são uma variação das fontes de dados de resumo que permitem unir dados online e offline. Ela requer o uso da variável [`transactionID`](/help/implement/vars/page-vars/transactionid.md) na implementação do Analytics.

* Se uma linha em um arquivo de fontes de dados incluir uma ID de transação que corresponda a uma ID de transação já coletada pelo AppMeasurement, as dimensões e métricas serão anexadas à ocorrência online.
* Se uma linha em um arquivo de origens de dados incluir uma ID de transação que não contenha uma correspondência, a linha será tratada de forma semelhante às origens de dados de resumo.

>[!NOTE]
>
>Antes de usar fontes de dados de ID de transação, você deve primeiro habilitá-lo em [Configurações Gerais da Conta](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) para o conjunto de relatórios desejado.

Ao enviar uma ocorrência online que contém um valor [`transactionID`](/help/implement/vars/page-vars/transactionid.md), o Adobe captura um &quot;instantâneo&quot; de todas as variáveis definidas ou persistentes em seguida. Se uma ID de transação correspondente carregada por meio de fontes de dados for encontrada, os dados offline e online serão vinculados.

As fontes de dados de ID de transação têm as seguintes propriedades:

* Os dados online devem ser coletados e processados primeiro. Se uma fonte de dados de ID de transação for carregada antes de um conjunto de relatórios processar uma ocorrência correspondente a essa ID de transação, os dados não serão vinculados.
* As IDs de transação coletadas por meio do AppMeasurement expiram após 25 meses.
* As fontes de dados carregadas com uma ID de transação expirada são tratadas de forma semelhante aos dados carregados sem uma ID de transação.
* Se a mesma variável for incluída na ocorrência online e na fonte de dados da ID de transação, o valor da fonte de dados da ID de transação será usado.
* Se uma variável for incluída em uma ocorrência online, mas não em uma ocorrência de fonte de dados de ID de transação correspondente, a variável de ocorrência online será preservada.
* Se você definir a mesma ID de transação em várias ocorrências online, somente a primeira ocorrência será alterada com dados de uma fonte de dados de ID de transação correspondente.
* Se você definir a mesma ID de transação em várias linhas de fonte de dados para as mesmas dimensões, o item de dimensão mais recente será usado.

Por exemplo:

1. Você envia uma exibição de página do AppMeasurement onde:
   * `eVar1` é igual a `blue`
   * `eVar2` é igual a `water`
   * `events` é igual a `event1`
   * `transactionID` é igual a `1256`
2. Depois que a ocorrência for coletada e processada, faça upload de uma fonte de dados de ID de transação onde:
   * `eVar1` é igual a `yellow`
   * `eVar3` é igual a `bird`
   * `events` é igual a `event2`
   * `transactionID` é igual a `1256`
3. Depois que a ocorrência das fontes de dados for processada, você visualizará um relatório no espaço de trabalho. Os dados mostrariam o seguinte:
   * `eVar1` é igual a `yellow`
   * `eVar2` é igual a `water`
   * `eVar3` é igual a `bird`
   * `events` é igual a `event2`

O valor de eVar 1 `blue` e a métrica `event1` não estão presentes no relatório, pois a ocorrência da ID de transação substituiu esses respectivos valores.
