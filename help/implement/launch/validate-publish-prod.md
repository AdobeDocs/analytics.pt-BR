---
title: Validar uma implementação de desenvolvimento e publicar na produção
description: Saiba como usar tags da Adobe Experience Platform para implantar o Adobe Analytics no ambiente de produção.
feature: Tags
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
role: Admin, Developer
source-git-commit: e35210582e94037cf286b98e7e0a6b06040a8c6f
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 72%

---

# Validar uma implementação de desenvolvimento e publicar na produção

Assim que a biblioteca de tags for enviada para produção, a empresa poderá começar a usar o Adobe Analytics para receber relatórios básicos.

## Pré-requisitos

[Implante a implementação do Analytics no ambiente de desenvolvimento](deploy-dev.md): uma implementação do Analytics deve ser publicada no ambiente de desenvolvimento para que esta página possa ser seguida.

## Valide a implementação de desenvolvimento usando o Experience Cloud Debugger

O depurador de Experience Cloud é uma extensão que mostra todas as tags de Experience Cloud presentes em uma página.

1. Instale a extensão do [Chrome](https://chromewebstore.google.com/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob) ou do Firefox.
2. Navegue até o site de desenvolvimento em que você implementou as tags.
3. Clique no ícone do Adobe Experience Cloud Debugger no navegador.
4. Se estiver tudo implementado corretamente, você verá o conteúdo no Adobe Analytics, nas tags e no serviço de ID de visitante da Adobe Experience Cloud.

## Implante a implementação de desenvolvimento para preparo/produção

Depois de validar que os dados estão sendo exibidos, você pode enviar a implementação para a versão ao vivo do site.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade da tag que pretende implementar no site.
1. Clique na guia **[!UICONTROL Publicação]** e localize a biblioteca na coluna de desenvolvimento.
1. Clique na lista suspensa da biblioteca e selecione **[!UICONTROL Enviar para aprovação]**. Clique em **[!UICONTROL Enviar]** na janela modal.
1. Clique na lista suspensa da biblioteca novamente (agora na coluna Enviado) e selecione **[!UICONTROL Build para Preparo]**.
1. Após alguns instantes, a luz amarela na biblioteca fica verde, indicando uma criação bem-sucedida.
1. Clique na lista suspensa da biblioteca novamente e selecione **[!UICONTROL Aprovar para publicação]**.
1. Clique na lista suspensa da biblioteca novamente (agora na coluna [!UICONTROL Aprovado]) e selecione **[!UICONTROL Criar e Publish para produção]**.
1. Vá para a guia Ambientes e clique em **[!UICONTROL Ambiente de produção]**.
1. Copie o código de instalação da produção e forneça-o aos proprietários do site. Solicite que eles implementem esse código no ambiente de produção do site.

## Valide a implementação de produção

Confirme se você está vendo os dados na versão ao vivo do site e comece a coleta de dados oficial do Adobe Analytics.

1. Depois de confirmar com os proprietários do site que eles enviaram o código da tag para produção, navegue até a página inicial do site no Chrome e abra o [!UICONTROL Depurador da Adobe Experience Cloud].
2. Se tudo estiver funcionando, você verá dados semelhantes aos seus testes no ambiente de desenvolvimento. Neste ponto, você está coletando dados no site e agora pode começar a usar o Adobe Analytics para relatórios.

## Solução de problemas

**Nenhum dado é exibido no depurador**.

Enquanto estiver no site, abra o console de desenvolvedor do navegador (normalmente F12). Examine o código-fonte da página e verifique se os seguintes itens foram atendidos:

* Não há erros de JavaScript no console. Trabalhe com os proprietários do site da empresa para garantir que todos os erros de JS sejam resolvidos.
* O código do cabeçalho está implementado corretamente: verifique se o código do cabeçalho está dentro da tag `<head>` e se o arquivo existe.
* A biblioteca do AppMeasurement existe: navegue diretamente para a origem de JS para verificar se o arquivo de JS contém o código. Caso contrário, verifique se cada ambiente foi criado e se a biblioteca foi publicada no respectivo ambiente.
* Extensões que interferem: algumas extensões, como bloqueadores de anúncios, podem impedir que as solicitações de imagem sejam acionadas. Desative todas as extensões que possam impedir o envio de dados para o Adobe.

## Próximas etapas

Agora que uma implementação básica foi configurada, sua função na organização pode influenciar o caminho sobre o qual você deseja saber mais:

* [Criar um documento de design da solução](../prepare/solution-design.md): elabore um plano sobre como você deseja usar as variáveis personalizadas e, em seguida, inclua na implementação
* [Introdução ao uso do Analysis Workspace](/help/analyze/analysis-workspace/home.md): mergulhe diretamente no Adobe Analytics usando o recurso principal da ferramenta.
