---
title: CEP
description: Preencha manualmente a dimensão “CEP” se as configurações do conjunto de relatórios permitirem.
feature: Appmeasurement Implementation
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 75%

---

# CEP

A variável `zip` permite preencher manualmente a dimensão “CEP” se a [!UICONTROL opção CEP] nas configurações do conjunto de relatórios permitir. Em versões anteriores do Adobe Analytics, essa variável só podia ser definida manualmente, geralmente ao inserir informações de envio em um site de varejo. Melhorias no Adobe Analytics permitem que essa variável seja definida automaticamente usando dados de localização geográfica. Essa variável não persiste para além da ocorrência à qual está atrelada.

>[!IMPORTANT]
>
>Verifique se a [!UICONTROL Opção de CEP] nas configurações do conjunto de relatórios está definida com o valor desejado. Não é possível usar essa variável se o [!UICONTROL CEP] for sempre usado. Consulte [Configurações gerais da conta](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) no Guia do usuário de administração para obter mais informações.

## Código postal usando o Web SDK

O CEP é mapeado para as seguintes variáveis:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.placeContext.geo.postalCode`
* [Objeto de dados](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.zip`

## Código postal usando a extensão do Adobe Analytics

Você pode definir o CEP ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o [!UICONTROL Tipo de Ação] como [!UICONTROL Definir Variáveis].
6. Localize a seção [!UICONTROL CEP].

É possível definir o CEP como qualquer valor de string, incluindo elementos de dados.

## s.zip no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.zip` é uma string que geralmente contém um CEP, mas que pode conter qualquer valor desejado de até 50 bytes de tamanho.

```js
s.zip = "84043";
```
