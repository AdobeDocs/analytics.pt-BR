---
description: Instruções para ajudar a localizar suas IDs de conta para o Google Ads e o Microsoft Advertising.
title: Localizar IDs de conta
feature: Advertising Analytics
exl-id: 2faccfd1-df7b-4b0c-a2f3-23138c39a838
TQID: https://experienceleague.adobe.com/5Z2hL08Ynl9M6abCm2bchArEOIYDz0cPTRIxQeqLbZ8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 344
ht-degree: 22%

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
>abstract="A &quot;ID da conta&quot; é um valor numérico localizado na interface do Microsoft Advertising. É possível localizá-la navegando até Configurações > Configurações da conta > ID da conta."

>[!CONTEXTUALHELP]
>id="adanalytics_ma_manager_account_id"
>title="ID da conta de gerente"
>abstract="A &quot;ID da conta de gerente&quot; é um valor numérico localizado na interface do Microsoft Advertising. É possível localizá-la navegando até Configurações > Configurações da conta de gerente > ID da conta de gerente."
