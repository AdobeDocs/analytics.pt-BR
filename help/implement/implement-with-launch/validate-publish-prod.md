---
title: Implantar o Adobe Analytics em um ambiente dev
seo-title: Implantar o Adobe Analytics em um ambiente dev
description: Saiba como usar o Adobe Experience Platform Launch para implantar o Adobe Analytics em seu ambiente de desenvolvimento.
seo-description: Saiba como usar o Adobe Experience Platform Launch para implantar o Adobe Analytics em seu ambiente de desenvolvimento.
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# Validar uma implementação de desenvolvimento e publicar na produção

Quando a biblioteca de lançamento da Adobe Experience Platform for enviada para produção, sua organização poderá começar a usar o Adobe Analytics para obter relatórios básicos.

## Pré-requisitos

[Implante sua implementação do Analytics no ambiente dev](deploy-dev.md): Uma implementação do Analytics deve ser publicada no ambiente de desenvolvimento para seguir esta página.

## Validar sua implementação dev usando o depurador da Experience Cloud

O depurador da Experience Cloud é um plug-plugin do Chrome que mostra todas as tags da Experience Cloud presentes em uma página.

1. Open [Chrome Web Browser](https://www.google.com/chrome/) and go to [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) on the Chrome Web Store to install the extension.
2. Navegue até o site de desenvolvimento que você implementou em Iniciar.
3. Clique no ícone de depurador da Adobe Experience Cloud na parte superior direita do Chrome
4. Se tudo estiver corretamente implementado, você deverá ver o conteúdo dentro do Adobe Analytics, Adobe Experience Platform Launch e o serviço de ID de visitante da Adobe Experience Cloud:

![depurador][assets/debugger.png]

## Implantar sua implementação dev em preparo/prod

Depois de validar os dados, você pode encaminhar sua implementação para a versão ativa do site.

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. Clique na propriedade Launch que pretende implementar em seu site.
3. Clique na guia Publicação e localize sua biblioteca na coluna de desenvolvimento.
4. Clique na lista suspensa na biblioteca e selecione Enviar para aprovação. Clique em Enviar na janela modal.
5. Clique novamente na lista suspensa da biblioteca (agora na coluna Enviado) e selecione Criar para armazenamento temporário.
6. Após alguns minutos, a luz amarela amarela na biblioteca fica verde, indicando uma criação bem-sucedida.
7. Clique novamente na lista suspensa da biblioteca e selecione Aprovar para publicação.
8. Clique novamente na lista suspensa da biblioteca (agora na coluna Aprovado) e selecione Criar e publicar na produção.
9. Vá até a guia Ambientes, o clique em Ambiente de produção.
10. Copie o código de cabeçalho + rodapé de produção e forneça-o para os proprietários do seu site. Solicite que implemente esse código no ambiente de produção do site.

## Validar a implementação da produção

Confirme que você está vendo dados na versão ativa do site e iniciando a coleta de dados oficial do Adobe Analytics.

1. Após confirmar que os proprietários de seu site enviaram o código de Lançamento para produção, navegue até a página inicial do seu site no Chrome e abra o depurador da Adobe Experience Cloud.
2. Se tudo estiver funcionando, você verá dados similares aos seus testes em seu ambiente de desenvolvimento. Nesse momento, você está coletando dados em seu site e agora pode começar a usar o Adobe Analytics para relatórios.

## Solução de problemas

**Nenhum dado aparece no depurador.**

Enquanto estiver no seu site, abra o console do desenvolvedor do navegador (geralmente F 12). Olhe o código fonte da página e certifique-se de que os seguintes itens sejam cumpridos:

* Não há erros de javascript no console. Trabalhe com os proprietários de site da sua organização para verificar se todos os erros JS foram resolvidos.
* Header code is properly implemented: Make sure the header code is inside the `<head>` tag, and that the file exists.
* A biblioteca appmeasurement existe: Navegue diretamente para a origem JS para verificar se o arquivo JS contém código. Caso contrário, verifique se cada ambiente foi criado e se a biblioteca foi publicada em seu respectivo ambiente.
* Plug-ins de interferência: Alguns plug-plugins do Chrome podem impedir que solicitações de imagens sejam acionadas. Desative qualquer plug-in que possa impedir que os dados sejam enviados para os servidores da Adobe.

## Próximas etapas

Agora que uma implementação básica foi configurada, sua função em sua organização pode influenciar qual caminho você deseja saber mais sobre:

* [Crie um documento de design de solução](../prepare/solution-design.md): Faça um plano para usar variáveis personalizadas e, em seguida, inclua-as na implementação
* [Comece a usar a Analysis Workspace](../../analyze/analysis-workspace/home.md): Mergulhe diretamente no Adobe Analytics usando o recurso principal da ferramenta.
