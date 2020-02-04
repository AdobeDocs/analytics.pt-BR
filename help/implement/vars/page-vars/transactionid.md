---
title: transactionID
description: Use essa variável para vincular dados online e offline.
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# transactionID

A `transactionID` variável identifica exclusivamente uma transação para que a ocorrência possa se vincular aos dados carregados por meio das Fontes de Dados. Essa variável é importante nos casos em que você deseja usar dados de outros canais e vinculá-los aos dados coletados com o AppMeasurement.

> [!NOTE] Antes de usar essa variável, verifique se o Armazenamento [!UICONTROL da ID de] transação está ativado em um conjunto de relatórios. See [General Account Settings](/help/admin/admin/general-acct-settings-admin.md) in the Admin user guide for more information.

Quando você configura `transactionID` uma ocorrência, a Adobe captura um &quot;instantâneo&quot; de todas as variáveis do Analytics definidas ou mantidas nesse momento. Os dados carregados por meio das Fontes de Dados com uma ID de transação correspondente são permanentemente vinculados a esses valores variáveis.

Por padrão, a Adobe lembra todos os valores de ID de transação (vinculados e desvinculados) por até 90 dias. Se o processo de interação offline for superior a 90 dias, entre em contato com o Atendimento ao cliente para ampliar esse limite.

## ID de transação no Adobe Experience Platform Launch

É possível definir a ID da transação ao configurar a extensão do Analytics (variáveis globais) ou sob as regras.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone &#39;+&#39;.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o Tipo [!UICONTROL de] ação como [!UICONTROL Definir variáveis].
6. Localize a seção ID [!UICONTROL da] transação.

É possível definir a ID de transação com qualquer valor de string, incluindo elementos de dados.

## s.transactionID no AppMeasurement e no editor de código personalizado Iniciar

A `s.transactionID` variável é uma string que contém um identificador exclusivo para uma transação. Valores válidos incluem caracteres alfanuméricos de até 100 bytes de comprimento. Seu valor padrão é uma string vazia.

```js
s.transactionID = "ABC123";
```

Se você tiver mais de uma ID de transação para uma ocorrência, poderá delimitar cada uma com uma vírgula. Várias IDs de transação ainda estão sujeitas ao limite de 100 bytes.

```js
s.transactionID = "ABC123,XYZ456";
```

> [!NOTE] Se você integrar vários canais offline usando essa variável, verifique se diferentes canais não sobrepõem IDs de transação. Por exemplo, se você tiver um valor de ID de transação da central de atendimento `1234` e um valor de ID de transação de venda de cliente potencial de `1234`, eles poderão entrar em conflito e causar resultados inesperados. Verifique se as IDs de transação contêm formatos exclusivos por canal offline e os diferencie, se necessário. Por exemplo, defina a ID de transação da central de atendimento como `call_1234` e a ID de transação de venda de cliente potencial `lead_1234` nas Fontes de Dados e no AppMeasurement.
