---
title: Implantar o Adobe Analytics em um ambiente de desenvolvimento
description: Saiba como usar o Adobe Experience Platform Launch para implantar o Adobe Analytics no ambiente de desenvolvimento.
translation-type: ht
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# Validar uma implementação de desenvolvimento e publicar na produção

Assim que a biblioteca do Adobe Experience Platform Launch for enviada para produção, a empresa poderá começar a usar o Adobe Analytics para receber relatórios básicos.

## Pré-requisitos

[Implante a implementação do Analytics no ambiente de desenvolvimento](deploy-dev.md): uma implementação do Analytics deve ser publicada no ambiente de desenvolvimento para que esta página possa ser seguida.

## Valide a implementação de desenvolvimento usando o Experience Cloud Debugger

O Experience Cloud Debugger é um plug-in do Chrome que mostra todas as tags da Experience Cloud presentes em uma página.

1. Abra o [navegador da Web Chrome](https://www.google.com/intl/pt/chrome/) e acesse o [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) na Chrome Web Store para instalar a extensão.
2. Navegue até o site de desenvolvimento em que você implementou o Launch.
3. Clique no ícone do Adobe Experience Cloud Debugger na parte superior direita do Chrome.
4. Se estiver tudo implementado corretamente, você verá o conteúdo no Adobe Analytics, no Adobe Experience Platform Launch e no serviço de ID de visitante da Adobe Experience Cloud:

![depurador][assets/debugger.png]

## Implante a implementação de desenvolvimento para preparo/produção

Após a validação dos dados, você pode enviar a implementação para a versão ao vivo do site.

1. Vá para [Adobe Experience Platform Launch](https://launch.adobe.com) e faça logon, se solicitado.
2. Clique na propriedade do Launch que pretende implementar no site.
3. Clique na guia Publicação e localize a biblioteca na coluna de desenvolvimento.
4. Clique na lista suspensa da biblioteca e selecione Enviar para aprovação. Clique em Enviar na janela modal.
5. Clique na lista suspensa da biblioteca novamente (agora na coluna Enviado) e selecione Criar para preparo.
6. Após alguns instantes, a luz amarela na biblioteca fica verde, indicando uma criação bem-sucedida.
7. Clique na lista suspensa da biblioteca novamente e selecione Aprovar para publicação.
8. Clique na lista suspensa da biblioteca novamente (agora na coluna Aprovado) e selecione Criar e publicar na produção.
9. Vá para a guia Ambientes e clique em Ambiente de produção.
10. Copie o cabeçalho de produção + código do rodapé e forneça aos proprietários do site. Solicite que eles implementem esse código no ambiente de produção do site.

## Valide a implementação de produção

Confirme se você está vendo os dados na versão ao vivo do site e comece a coleta de dados oficial do Adobe Analytics.

1. Depois de confirmar com os proprietários do site que eles enviaram o código do Launch para a produção, navegue até a página inicial do site no Chrome e abra o Adobe Experience Cloud Debugger.
2. Se tudo estiver funcionando, você verá dados semelhantes aos seus testes no ambiente de desenvolvimento. Neste ponto, você está coletando dados no site e agora pode começar a usar o Adobe Analytics para relatórios.

## Solução de problemas

**Nenhum dado é exibido no depurador**.

Enquanto estiver no site, abra o console de desenvolvedor do navegador (normalmente F12). Examine o código-fonte da página e verifique se os seguintes itens foram atendidos:

* Não há erros de JavaScript no console. Trabalhe com os proprietários do site da empresa para garantir que todos os erros de JS sejam resolvidos.
* O código do cabeçalho está implementado corretamente: verifique se o código do cabeçalho está dentro da tag `<head>` e se o arquivo existe.
* A biblioteca do AppMeasurement existe: navegue diretamente para a origem de JS para verificar se o arquivo de JS contém o código. Caso contrário, verifique se cada ambiente foi criado e se a biblioteca foi publicada no respectivo ambiente.
* Interferência de plug-ins: alguns plug-ins do Chrome podem impedir que as solicitações de imagem sejam acionadas. Desative todos os plug-ins que possam impedir o envio de dados para servidores da Adobe.

## Próximas etapas

Agora que uma implementação básica foi configurada, sua função na empresa pode influenciar o caminho sobre o qual você deseja saber mais:

* [Criar um documento de design da solução](../prepare/solution-design.md): elabore um plano sobre como você deseja usar as variáveis personalizadas e, em seguida, inclua na implementação
* [Introdução ao uso do Analysis Workspace](/help/analyze/analysis-workspace/home.md): mergulhe diretamente no Adobe Analytics usando o recurso principal da ferramenta.
