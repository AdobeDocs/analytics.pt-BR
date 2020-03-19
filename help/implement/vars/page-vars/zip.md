---
title: zip
description: Preencha manualmente a dimensão “CEP” se as configurações do conjunto de relatórios permitirem.
translation-type: ht
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# zip

A variável `zip` permite preencher manualmente a dimensão “CEP” se a [!UICONTROL opção CEP] nas configurações do conjunto de relatórios permitir. Em versões anteriores do Adobe Analytics, essa variável só podia ser definida manualmente, geralmente ao inserir informações de envio em um site de varejo. Melhorias no Adobe Analytics permitem que essa variável seja definida automaticamente usando dados de localização geográfica. Essa variável não persiste para além da ocorrência à qual está atrelada.

> [!IMPORTANT] Verifique se a [!UICONTROL Opção de CEP] nas configurações do conjunto de relatórios está definida com o valor desejado. Não é possível usar essa variável se o [!UICONTROL CEP] for sempre usado. Consulte [Configurações gerais da conta](/help/admin/admin/general-acct-settings-admin.md) no Guia do usuário de administração para obter mais informações.

## CEP no Adobe Experience Platform Launch

Você pode definir o CEP ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL CEP].

É possível definir o CEP como qualquer valor de string, incluindo elementos de dados.

## s.zip no AppMeasurement e no editor de código personalizado do Launch

A variável `s.zip` é uma string que geralmente contém um CEP, mas que pode conter qualquer valor desejado de até 50 bytes de tamanho.

```js
s.zip = "84043";
```
