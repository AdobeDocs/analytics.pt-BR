---
description: Instruções para ajudar a localizar suas IDs de conta para o Google Ads e o Microsoft Advertising.
title: Localizar IDs de conta
feature: Advertising Analytics
exl-id: 2faccfd1-df7b-4b0c-a2f3-23138c39a838
source-git-commit: 586459d99674f01a3b18f84f975a3365ddf2fcd9
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 3%

---

# Localizar IDs de conta {#locate-your-account-ids}

Saiba como localizar suas IDs de conta para o Google Ads e o Microsoft Advertising.

## Anúncios do Google (AdWords) {#google}

>[!IMPORTANT]
>
>O Google Ads usa dois tipos de conta:
>
>- Conta MCC (Meu centro do cliente) e
>- Conta Padrão.
>
>Para esta integração com o Adobe Analytics, **você deve usar um logon de Conta Padrão**, não um logon de Conta MCC. O motivo é que uma conta MCC atua como uma conta &quot;guarda-chuva&quot; que pode acessar várias contas do Google Ads com um único logon, enquanto o logon de Conta padrão pode acessar apenas uma conta por logon. Embora o Google ofereça suporte à vinculação de um email para gerenciar cinco contas, o Advertising Analytics ainda não oferece suporte a esse recurso. Um email pode ser vinculado somente a uma conta do Google Ads.

Clique no ícone Conta na parte superior direita para exibir o número de conta do Google Ads (ID de cliente).

![Conta do Gerente do Google Ads](assets/google-account.png)

## Microsoft Advertising (Bing) {#microsoft}

>[!NOTE]
>
>Se sua conta do Microsoft Advertising (antigo Bing) usar o recurso de importação do Google, atualize a sequência de caracteres de rastreamento correta. A cadeia de caracteres de rastreamento não é atualizada automaticamente da versão do Google para a cadeia de caracteres de rastreamento correta do Microsoft Advertising e pode resultar em dados não especificados. Consulte [O que é importado do Google Ads](https://help.ads.microsoft.com/apex/index/3/en/50851/) na ajuda do Microsoft Advertising para obter mais informações.

A **[!UICONTROL ID da Conta]** e a **[!UICONTROL ID da conta do gerente]** são obrigatórias.

- A **[!UICONTROL ID da Conta]** está localizada em **[!UICONTROL Configurações]** > **[!UICONTROL Configurações da Conta]** > **[!UICONTROL ID da Conta]**. Use a [!UICONTROL ID de conta] e NÃO o [!UICONTROL número de conta].
- A **[!UICONTROL ID da conta do gerente]** está localizada em **[!UICONTROL Configurações]** > **[!UICONTROL Configurações da conta do gerente]** > **[!UICONTROL ID da conta do gerente]**. Use a [!UICONTROL ID de conta de gerente] e NÃO o [!UICONTROL número de conta de gerente].

![Navegação no Microsoft Advertising](assets/bing-id.png)

>[!CONTEXTUALHELP]
>id="adanalytics_ma_account_id"
>title="ID da Conta"
>abstract="A &quot;ID da conta&quot; é um valor numérico localizado na interface do Microsoft Advertising. Você pode localizá-la navegando até Configurações > Configurações da conta > ID da conta."

>[!CONTEXTUALHELP]
>id="adanalytics_ma_manager_account_id"
>title="ID da conta do gerente"
>abstract="A &quot;ID da conta do gerente&quot; é um valor numérico localizado na interface do Microsoft Advertising. Você pode localizá-la navegando até Configurações > Configurações da conta do gerente > ID da conta do gerente."
