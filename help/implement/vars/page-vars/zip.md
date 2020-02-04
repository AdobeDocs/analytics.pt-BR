---
title: zip
description: Preencha manualmente a dimensão 'CEP' se as configurações do conjunto de relatórios permitirem.
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# zip

A `zip` variável permite preencher manualmente a dimensão &#39;CEP&#39; se a opção  CEP nas configurações do conjunto de relatórios permitir. Em versões anteriores do Adobe Analytics, essa variável só podia ser definida manualmente, normalmente ao inserir informações de envio em um site de varejo. Melhorias no Adobe Analytics permitem que essa variável seja definida automaticamente usando dados de localização geográfica. Essa variável não persiste além da ocorrência definida.

> [!IMPORTANT] Verifique se a opção  CEP nas configurações do conjunto de relatórios está definida como o valor desejado. Não é possível usar essa variável se o zip [!UICONTROL geográfico] for sempre usado. See [General Account Settings](/help/admin/admin/general-acct-settings-admin.md) in the Admin user guide for more information.

## Zip no Adobe Experience Platform Launch

Você pode definir o CEP ao configurar a extensão do Analytics (variáveis globais) ou sob as regras.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone &#39;+&#39;.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o Tipo [!UICONTROL de] ação como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Zip] .

É possível definir CEP para qualquer valor de string, incluindo elementos de dados.

## s.zip no AppMeasurement e Iniciar editor de código personalizado

A `s.zip` variável é uma string que geralmente contém um CEP, mas pode conter qualquer valor desejado de até 50 bytes de comprimento.

```js
s.zip = "84043";
```
