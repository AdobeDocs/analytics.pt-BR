---
title: Configurar o Report Builder
description: Saiba mais sobre como instalar e configurar o Adobe Analytics Report Builder for Excel. Instruções de configuração passo a passo para uma integração perfeita.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 9d0161a9-ee7b-43a9-92ad-4079cf4b9c6c
source-git-commit: 1e893ce94ee3da46bbf22d7a90573681950d1135
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 39%

---

# Configurar o Report Builder

Este artigo descreve os requisitos para usar o Report Builder para Adobe Analytics no [!DNL Microsoft] [!DNL Excel]. E como instalar e configurar o suplemento.

## Requisitos

O Report Builder para Adobe Analytics é compatível com os seguintes sistemas operacionais e navegadores da Web.

### macOS

- macOS versão 10.x ou posterior
- Todas as [!DNL Microsoft] [!DNL Excel] Versões

### Windows

- Windows 10, versão 1904 ou posterior
- [!DNL Excel] Versão 2106 ou posterior

  Todos os usuários [!DNL Excel] da área de trabalho do Windows devem instalar o Microsoft Edge Webview2 para usar o suplemento. Para instalar o controlador:

   1. Vá para <https://aka.ms/webview2installer>.
   1. Selecione e baixe o instalador autônomo Evergreen.
   1. Siga o assistente de instalação.

### Web Office

- Suporta todos os navegadores e versões


## Suplemento Report Builder para o Excel

Você deve instalar o Suplemento Report Builder [!DNL Excel] para usar o [!DNL Report Builder] for Adobe Analytics. Depois de instalar o Suplemento Report Builder [!DNL Excel], você pode acessar o Report Builder de uma pasta de trabalho [!DNL Excel] aberta.

### Baixe e instale o Suplemento Report Builder

Para baixar e instalar o Suplemento Report Builder

1. Inicie [!DNL Excel] e abra uma nova pasta de trabalho.

1. Selecione **[!UICONTROL Inserir]** > **[!UICONTROL Obter Suplementos]**.

1. Na caixa de diálogo Suplementos do Office, selecione a guia Loja.

1. Procure por &quot;Report Builder&quot; e clique em **[!UICONTROL Adicionar]**.

1. Na caixa de diálogo Termos de licença e política de privacidade, clique em **[!UICONTROL Continuar]**.

**Se a guia Loja não for exibida**

1. Em [!DNL Excel], selecione Arquivo > Conta > Gerenciar Configurações.

1. Marque a caixa ao lado de &quot;Habilitar experiências conectadas opcionais&quot;

1. Reinicie [!DNL Excel].

**Se sua organização bloquear o acesso à Microsoft Store**

- Entre em contato com a equipe de TI ou de segurança para solicitar aprovação para o Suplemento Report Builder. Após a concessão da aprovação, na caixa de diálogo Suplementos do Office, selecione a guia **[!UICONTROL Administrador Gerenciado]**.

  ![A guia Administrador Gerenciado na caixa de diálogo Suplementos do Office.](./assets/image1.png)

- Como alternativa, você pode recuperar manualmente o [arquivo de manifesto](https://reportbuilder.an.adobe.com/manifest.xml) e hospedar o arquivo em sua própria infraestrutura de TI. <br/>Siga a [documentação online](https://learn.microsoft.com/en-us/office/dev/add-ins/publish/publish) do Microsoft Office para obter instruções sobre como instalar um arquivo de Manifesto do Excel não fornecido pela Microsoft Store.

Depois de instalar o Suplemento Report Builder, o ícone do Report Builder é exibido na faixa de opções [!DNL Excel], na guia Página inicial.

![O ícone do Report Builder no Excel](/help/analyze/report-builder/assets/rb_app_icon.png)

## Fazer logon no Report Builder

Após instalar o Suplemento Report Builder for Excel na sua plataforma operacional ou navegador, siga estas etapas para fazer logon no Report Builder.

1. Abra uma pasta de trabalho do Excel.

1. Clique no ícone Report Builder para iniciar o Report Builder.

1. Na barra de ferramentas do Adobe Report Builder, clique em **[!UICONTROL Logon]**.

   ![Clique no botão de logon do Report Builder.](/help/analyze/report-builder/assets/rb_login.png)

1. Insira as informações da conta de ID da Adobe Experience. As informações da sua conta devem corresponder às suas credenciais da Adobe Analytics.

   ![Seu ícone e organização de logon.](/help/analyze/report-builder/assets/image4.png)

Depois de fazer logon, o ícone de logon e a organização aparecem na parte superior do painel

## Alternar organizações

Ao fazer logon pela primeira vez, você faz logon na organização padrão atribuída ao perfil.

1. Clique no nome da organização que é exibida ao fazer logon.

1. Selecione uma organização na lista de organizações disponíveis. Somente as organizações às quais você tem acesso são listadas.

   ![A lista de organizações que você pode acessar.](/help/analyze/report-builder/assets/image5.png)

## Fazer logoff

Você pode fazer logoff do Report Builder a partir do perfil do usuário.

1. Salve as alterações em qualquer pasta de trabalho aberta.

1. Clique no ícone de avatar para exibir seu perfil de usuário.

   ![O avatar do seu perfil de usuário e o botão Sair.](/help/analyze/report-builder/assets/image6.png)

1. Clique em **Fazer logoff**.
