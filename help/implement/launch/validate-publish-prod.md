---
title: Validar uma implementação de desenvolvimento e publicar na produção
description: Saiba como usar tags Adobe Experience Platform para implantar o Adobe Analytics no ambiente de produção.
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 64%

---

# Validar uma implementação de desenvolvimento e publicar na produção

Assim que sua biblioteca de tags for enviada para produção, sua organização poderá começar a usar o Adobe Analytics para obter relatórios básicos.

>[!NOTE]
>A Adobe Experience Platform Launch foi reformulada como um conjunto de tecnologias de coleta de dados no Experience Platform. Como resultado, várias alterações de terminologia foram implementadas na documentação do produto. Consulte o seguinte [documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) para obter uma referência consolidada das alterações de terminologia.

## Pré-requisitos

[Implante a implementação do Analytics no ambiente de desenvolvimento](deploy-dev.md): uma implementação do Analytics deve ser publicada no ambiente de desenvolvimento para que esta página possa ser seguida.

## Valide a implementação de desenvolvimento usando o Experience Cloud Debugger

O Experience Cloud Debugger é um plug-in do Chrome que mostra todas as tags da Experience Cloud presentes em uma página.

1. Abra o [navegador da Web Chrome](https://www.google.com/intl/pt-BR/chrome/) e acesse o [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) na Chrome Web Store para instalar a extensão.
2. Navegue até o site de desenvolvimento no qual você implementou tags.
3. Clique no ícone do Adobe Experience Cloud Debugger na parte superior direita do Chrome.
4. Se tudo estiver implementado corretamente, você verá o conteúdo dentro do Adobe Analytics, tags e o serviço de ID de visitante da Adobe Experience Cloud:

![depurador][assets/debugger.png]

## Implante a implementação de desenvolvimento para preparo/produção

Após a validação dos dados, você pode enviar a implementação para a versão ao vivo do site.

1. Vá para [experience.adobe.com](https://experience.adobe.com) e faça logon quando solicitado.
1. Selecione **[!UICONTROL Launch / Data Collection]**.
1. Clique em **[!UICONTROL Ir para Iniciar/Coleta de dados]** e selecione **[!UICONTROL Tags]**.
1. Clique na propriedade de tag que você pretende implementar em seu site.
1. Clique na guia **[!UICONTROL Publishing]** e localize a biblioteca na coluna de desenvolvimento.
1. Clique na lista suspensa da biblioteca e selecione **[!UICONTROL Enviar para aprovação]**. Clique em **[!UICONTROL Enviar]** na janela modal.
1. Clique na lista suspensa da biblioteca novamente (agora na coluna Enviado) e selecione **[!UICONTROL Criar para preparo]**.
1. Após alguns instantes, a luz amarela na biblioteca fica verde, indicando uma criação bem-sucedida.
1. Clique na lista suspensa da biblioteca novamente e selecione **[!UICONTROL Aprovar para publicação]**.
1. Clique na lista suspensa da biblioteca novamente (agora na coluna [!UICONTROL Aprovado]) e selecione **[!UICONTROL Criar e publicar na produção]**.
1. Vá para a guia Ambientes e clique em **[!UICONTROL Ambiente de produção]**.
1. Copie o cabeçalho de produção + código do rodapé e forneça aos proprietários do site. Solicite que eles implementem esse código no ambiente de produção do site.

## Valide a implementação de produção

Confirme se você está vendo os dados na versão ao vivo do site e comece a coleta de dados oficial do Adobe Analytics.

1. Depois de confirmar com os proprietários do site que eles enviaram o código da tag para produção, navegue até a página inicial do site no Chrome e abra o [!UICONTROL Adobe Experience Cloud Debugger].
2. Se tudo estiver funcionando, você verá dados semelhantes aos seus testes no ambiente de desenvolvimento. Neste ponto, você está coletando dados no site e agora pode começar a usar o Adobe Analytics para relatórios.

## Solução de problemas

**Nenhum dado é exibido no depurador**.

Enquanto estiver no site, abra o console de desenvolvedor do navegador (normalmente F12). Examine o código-fonte da página e verifique se os seguintes itens foram atendidos:

* Não há erros de JavaScript no console. Trabalhe com os proprietários do site da empresa para garantir que todos os erros de JS sejam resolvidos.
* O código do cabeçalho está implementado corretamente: verifique se o código do cabeçalho está dentro da tag `<head>` e se o arquivo existe.
* A biblioteca do AppMeasurement existe: navegue diretamente para a origem de JS para verificar se o arquivo de JS contém o código. Caso contrário, verifique se cada ambiente foi criado e se a biblioteca foi publicada no respectivo ambiente.
* Interferência de plug-ins: alguns plug-ins do Chrome podem impedir que as solicitações de imagem sejam acionadas. Desative todos os plug-ins que possam impedir o envio de dados para servidores da Adobe.

## Próximas etapas

Agora que uma implementação básica foi configurada, sua função na organização pode influenciar o caminho sobre o qual você deseja saber mais:

* [Criar um documento de design da solução](../prepare/solution-design.md): elabore um plano sobre como você deseja usar as variáveis personalizadas e, em seguida, inclua na implementação
* [Introdução ao uso do Analysis Workspace](/help/analyze/analysis-workspace/home.md): mergulhe diretamente no Adobe Analytics usando o recurso principal da ferramenta.
