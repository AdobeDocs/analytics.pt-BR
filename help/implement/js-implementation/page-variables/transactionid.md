---
description: As variáveis de página populam diretamente um relatório, como pageName, Propriedades de lista, Variáveis de lista, entre outros.
keywords: Analytics Implementation
subtopic: Variables
title: Variáveis de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# transactionID

As [!UICONTROL Fontes de dados de integração] utilizam uma [!UICONTROL ID de transação ]para unir dados offline para uma transação online (como um cliente em potencial ou compra gerada online).


<!-- 

transactionID.xml

 -->

Cada *`transactionID`* única enviada para a Adobe é registrada em preparação para um upload de [!UICONTROL Fontes de dados ]de informações offline sobre essa transação. Consulte [Origens de Dados](https://marketing.adobe.com/resources/help/en_US/sc/datasources/).

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| 100 bytes | xact | n/a | "" |

**Ativar armazenamento da ID de transação** {#section_3EA2C9DC9D4C4F0FBE4AB67981BCB52E}

Antes de registrar os valores *`transactionID`*, o [!UICONTROL Armazenamento da ID de transação] deve estar ativado para o conjunto de relatórios selecionado no Gerenciador de conjuntos de relatórios. Esta configuração está localizada em

```
Analytics > Admin > Report Suites > Edit Settings > General > General Account Settings.
```

Para ver se *`transactionID Storage`* está ativado para um conjunto de relatórios, acesse

```
Analytics > Admin > Data Sources > Manage
```

**Sintaxe e valores possíveis** {#section_0C18329203DC45E989DBAE70C0FB4801}

```js
s.transactionID="unique_id"
```

O *`transactionID`* deve conter somente caracteres alfanuméricos. Se for necessário registrar várias [!UICONTROL transactionIDs] em uma única ocorrência, é possível usar uma vírgula para delimitar vários valores.

**Exemplos** {#section_A4C1F0E54CB54AD7B86A22147E9B5FEF}

```js
s.transactionID="11123456"
```

```js
s.transactionID="lead_12345xyz"
```

```js
s.transactionID=s.purchaseID
```

**Armadilhas, dúvidas e dicas** {#section_4299BAD5D0154DBC88A9EF0E2C252BB4}

* Se a gravação *`transactionID`* não estiver ativada, os valores *`transactionID`* serão descartados e não estarão disponíveis para uso com as [!UICONTROL Fontes de dados de integração]. Defina uma variável ou um evento de conversão (uma eVar ou a variável de eventos) na página em que *`transactionID`* foi definido. Do contrário, nenhum dado será gravado para *`transactionID`*.

* Se estiver registrando [!UICONTROL transactionIDs] para vários sistemas, como compras e leads, assegure que o valor em *`transactionID`* seja sempre único. Isso pode ser feito se você adicionar um prefixo à ID, como lead_1234 e purchase_1234. As [!UICONTROL Fontes de dados de integração] não funcionarão como esperado (os dados da [!UICONTROL Fonte de dados] se conectam aos dados errados) se um *`transactionID`* único for visualizado duas vezes.

* Por padrão, os valores *`transactionID`* são lembrados por 90 dias. Se o processo de interação offline for superior a 90 dias, entre em contato com o Atendimento ao cliente para ampliar o limite.

> [!NOTE]A variável *`transactionID`* pode conter qualquer caractere diferente de vírgula. Ela deve estar no mesmo local em que o limite de caracteres (100 bytes) é especificado. Se forem usados caracteres multibytes, será necessário ativar suporte a esses caracteres para evitar problemas com caracteres inesperados na *`transactionID`*.
