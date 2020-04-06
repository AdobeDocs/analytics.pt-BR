---
title: zip
description: Preencha manualmente a dimensão “CEP” se as configurações do conjunto de relatórios permitirem.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# zip

The `zip` variable allows you to manually populate the &#39;Zip Code&#39; dimension if the [!UICONTROL Zip Option] in report suite settings allows it. Em versões anteriores do Adobe Analytics, essa variável só podia ser definida manualmente, geralmente ao inserir informações de envio em um site de varejo. Melhorias no Adobe Analytics permitem que essa variável seja definida automaticamente usando dados de localização geográfica. Essa variável não persiste para além da ocorrência à qual está atrelada.

>[!IMPORTANT] Verifique se as configurações do conjunto de relatórios [!UICONTROL Zip Option] estão definidas com o valor desejado. You cannot use this variable if [!UICONTROL geo zip] is always used. Consulte [Configurações gerais da conta](/help/admin/admin/general-acct-settings-admin.md) no Guia do usuário de administração para obter mais informações.

## CEP no Adobe Experience Platform Launch

Você pode definir o CEP ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Em [!UICONTROL Actions], clique em uma [!UICONTROL Adobe Analytics - Set Variables] ação existente ou no ícone &#39;+&#39;.
5. Defina a [!UICONTROL Extension] lista suspensa como Adobe Analytics e [!UICONTROL Action Type] como [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Zip] section.

É possível definir o CEP como qualquer valor de string, incluindo elementos de dados.

## s.zip no AppMeasurement e no editor de código personalizado do Launch

A variável `s.zip` é uma string que geralmente contém um CEP, mas que pode conter qualquer valor desejado de até 50 bytes de tamanho.

```js
s.zip = "84043";
```
