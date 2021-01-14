---
description: Informações sobre as três formas de fazer logon no Report Builder.
title: Logon no Report Builder
topic: Report builder
uuid: 9a21b791-e323-46d2-b850-2d67babe964b
translation-type: tm+mt
source-git-commit: 5b130de23d7826a266f34ed1830540c8c0865560
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 70%

---


# Logon no Report Builder

>[!IMPORTANT]
>
>O Report Builder versão 5.6.47 e posterior é compatível apenas com o login no Experience Cloud e não é compatível com logons antigos, como o Logon Único do Site Catalyst ou o Logon Padrão. Até 30 de abril de 2021, todos os usuários do Report Builder devem atualizar o Report Builder para a versão 5.6.47 ou posterior, que inclui uma atualização crítica para o processo de logon.

Para fazer logon no Report Builder, use sua conta de login do Experience Cloud.

## Experience Cloud {#section_1FA230F35AB54021A874A7A28DE4C850}

O logon da Experience Cloud permite o uso da Enterprise ID (email e senha) para fazer logon na Adobe Experience Cloud. Clique em **[!UICONTROL Fazer logon]** > **[!UICONTROL Fazer logon com a Enterprise ID]** para ser redirecionado à página de logon único da empresa. Para saber mais sobre a Enterprise ID, clique [aqui](https://helpx.adobe.com/br/enterprise/kb/enterprise-id-faq.html#whatis).

![](assets/adobe_id_login.png)

>[!NOTE]
>
>O logon da Experience Cloud é baseado em sessões e o token expira após 30 dias.

## Fazer logon no Report Builder

Para efetuar login no Report Builder

1. No Excel, clique em **[!UICONTROL Suplementos]**.
1. Clique em **[!UICONTROL Fazer logon]**. Outras ações que efetuam seu logon incluem:

   * Clique em **[!UICONTROL Criar]**.
   * [Selecione uma solicitação no Gerenciador](/help/analyze/report-builder/manage-requests/r-arb-manage-requests.md) de solicitações e clique em  **** Addor  **[!UICONTROL Manage]**.
   * Duplo clique em uma solicitação no Excel.

1. Complete os campos na página de [!UICONTROL Logon], e depois clique em **[!UICONTROL OK]**.

## Tipos de logon antigos

>[!IMPORTANT]
>
>Até 30 de abril de 2021, os tipos de logon antigos não funcionarão. Todos os usuários do Report Builder devem atualizar o Report Builder Add-in para a versão 5.6.47 ou posterior, que inclui uma atualização crítica para o processo de logon. **O Report Builder versão 5.6.47 e posterior é compatível apenas com o login no Experience Cloud e não é compatível com logons antigos, como o logon padrão ou o logon único do Site Catalyst.**

<!-- ![](assets/login_screen.png) -->

* [Padrão ](/help/analyze/report-builder/setup/login.md#section_6D54B8ADAE7F416BB83F5082B3771CFA)
* [Logon único do Site Catalyst](/help/analyze/report-builder/setup/login.md#section_6970A5F926774976B85FFE576610E85F)

## Padrão {#section_6D54B8ADAE7F416BB83F5082B3771CFA}

Use essa opção se desejar fazer logon no Report Builder usando as credenciais do Adobe Analytics.

**Logon do Report Builder - Definições de campo**

| Campo | Definição |
|--- |--- |
| Empresa | A credencial de logon da Empresa que você usa para acessar o Adobe Analytics. |
| Nome de usuário | O Nome de usuário que você usa para fazer logon no Adobe Analytics. As tarefas agendadas para um usuário estão vinculadas ao nome do usuário. Você pode ver suas tarefas agendadas em qualquer computador, se fizer logon no Report Builder com as mesmas credenciais de logon. |
| Senha | Sua senha do Analytics. |
| Lembrar meus dados | As informações de logon são criptografadas e armazenadas no arquivo de perfil do usuário na máquina em que o Report Builder está instalado. Como as informações de logon são salvas, qualquer pessoa que use o mesmo PC que o criador do relatório que abra uma planilha que contém um relatório poderá atualizar e editar os dados. Se você compartilha seu computador com outras pessoas e desejar manter os dados da planilha confidenciais, não ative essa opção.  Para desativar a configuração de logon automático, clique em **[!UICONTROL Fazer logon com credenciais diferentes]** na barra de ferramentas e desative **[!UICONTROL Lembrar meus dados]**. |
| Usar um servidor proxy | Ative se você estiver acessando a Internet através de um servidor proxy e for solicitado a fornecer um nome de usuário proxy e senha. |

## Logon único {#section_6970A5F926774976B85FFE576610E85F}

Este logon único (herdado) permite acessar o Adobe Analytics apenas, não toda a Experience Cloud.

Também é possível inserir um domínio que será reconhecido pelo sistema e redirecionará o usuário até a página de logon único da empresa; lá, o usuário poderá fazer logon no Adobe Analytics.
