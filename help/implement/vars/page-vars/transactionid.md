---
title: transactionID
description: Use essa variável para vincular dados online e offline.
translation-type: ht
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# transactionID

A variável `transactionID` atribui uma identificação exclusiva a uma transação para que a ocorrência possa se vincular aos dados carregados por meio de Fontes de dados. Essa variável é importante quando você deseja usar dados de outros canais e quer vinculá-los aos dados coletados com o AppMeasurement.

> [!NOTE] Antes de usar essa variável, verifique se o [!UICONTROL Armazenamento da ID de transação] em um conjunto de relatórios está ativado. Consulte [Configurações gerais da conta](/help/admin/admin/general-acct-settings-admin.md) no Guia do usuário de administração para obter mais informações.

Quando você configura `transactionID` em uma ocorrência, a Adobe captura uma &quot;imagem&quot; de todas as variáveis do Analytics definidas ou mantidas até o momento. Os dados carregados por meio das Fontes de Dados com um ID de transação correspondente são permanentemente vinculados a esses valores de variáveis.

Por padrão, a Adobe lembra de todos os valores de IDs de transação (vinculados e desvinculados) por até 90 dias. Se o processo de interação offline for superior a 90 dias, entre em contato com o Atendimento ao cliente para ampliar esse limite.

## ID de transação no Adobe Experience Platform Launch

Você pode definir o ID de transação ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL ID de transação].

É possível definir o ID da transação como qualquer valor de string, incluindo elementos de dados.

## s.transactionID no AppMeasurement e no editor de código personalizado do Launch

A variável `s.transactionID` é uma string que contém um identificador exclusivo para uma transação. Valores válidos incluem caracteres alfanuméricos de até 100 bytes de tamanho. Seu valor padrão é uma string vazia.

```js
s.transactionID = "ABC123";
```

Se você tiver mais de uma ID de transação para uma ocorrência, é possível delimitar cada ID com uma vírgula. As várias IDs de transação ainda estão sujeitas ao limite de 100 bytes.

```js
s.transactionID = "ABC123,XYZ456";
```

> [!NOTE] Se você integrar vários canais offline usando essa variável, verifique se canais diferentes não sobrepõem as IDs de transação. Por exemplo, se você tiver um ID de transação da central de atendimento com o valor `1234` e um ID de transação de venda de cliente potencial com o valor `1234`, eles poderão entrar em conflito e causar resultados inesperados. Verifique se os IDs de transação contêm formatos exclusivos para cada canal offline e os diferencie, se necessário. Por exemplo, defina a ID de transação da central de atendimento como `call_1234` e a ID de transação de venda de cliente potencial como `lead_1234` nas Fontes de dados e no AppMeasurement.
