---
title: transactionID
description: Use essa variável para vincular dados online e offline.
feature: Appmeasurement Implementation
exl-id: 525e90d8-99a7-4f4f-9bce-1395bf72fd8f
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 89%

---

# transactionID

A variável `transactionID` atribui uma identificação exclusiva a uma transação para que a ocorrência possa se vincular aos dados carregados por meio de Fontes de dados. Essa variável é importante quando você deseja usar dados de outros canais e quer vinculá-los aos dados coletados com o AppMeasurement.

>[!NOTE]
>
>Antes de usar essa variável, verifique se o [!UICONTROL Armazenamento da ID de transação] em um conjunto de relatórios está ativado. Consulte [Configurações gerais da conta](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) no Guia do usuário de administração para obter mais informações.

Quando você configura `transactionID` em uma ocorrência, a Adobe captura uma &quot;imagem&quot; de todas as variáveis do Analytics definidas ou mantidas até o momento. Os dados carregados por meio das Fontes de Dados com um ID de transação correspondente são permanentemente vinculados a esses valores de variáveis.

O Adobe lembra de todos os valores de IDs de transação (vinculados e desvinculados) por até 25 meses.

## ID de transação usando o SDK da Web

A ID da transação é mapeada para as seguintes variáveis:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.commerce.order.payments[3].transactionID` ou `xdm.commerce.order.payments.transactionID`
* [Objeto de dados](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.transactionID` ou `data.__adobe.analytics.xact`

## ID de transação que usa a extensão do Adobe Analytics

Você pode definir o ID de transação ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o [!UICONTROL Tipo de Ação] como [!UICONTROL Definir Variáveis].
6. Localize a seção [!UICONTROL ID de transação].

É possível definir o ID da transação como qualquer valor de string, incluindo elementos de dados.

## s.transactionID no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.transactionID` é uma string que contém um identificador exclusivo para uma transação. Valores válidos incluem caracteres alfanuméricos de até 100 bytes de tamanho. Seu valor padrão é uma string vazia.

```js
s.transactionID = "ABC123";
```

Se você tiver mais de uma ID de transação para uma ocorrência, é possível delimitar cada ID com uma vírgula. As várias IDs de transação ainda estão sujeitas ao limite de 100 bytes.

```js
s.transactionID = "ABC123,XYZ456";
```

>[!TIP]
>
>Se você integrar vários canais offline usando essa variável, verifique se canais diferentes não sobrepõem as IDs de transação. Por exemplo, se você tiver um ID de transação da central de atendimento com o valor `1234` e um ID de transação de venda de cliente potencial com o valor `1234`, eles poderão entrar em conflito e causar resultados inesperados. Verifique se os IDs de transação contêm formatos exclusivos para cada canal offline e os diferencie, se necessário. Por exemplo, defina a ID de transação da central de atendimento como `call_1234` e a ID de transação de venda de cliente potencial como `lead_1234` nas Fontes de dados e no AppMeasurement.
