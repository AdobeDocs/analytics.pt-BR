---
title: Validar uma implementação de desenvolvimento e publicar na produção
description: Saiba como usar tags da Adobe Experience Platform para implantar o Adobe Analytics no ambiente de produção.
feature: Tags
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/FpJRwRs9GXGTzUY52vWqC5Ddej-I3mh2ASC6YKphNRI'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: df312454-73c4-43f6-a90e-18f5043f074c
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 635
ht-degree: 65%

---

# Validar uma implementação de desenvolvimento e publicar na produção

Assim que a biblioteca de tags for enviada para produção, a empresa poderá começar a usar o Adobe Analytics para receber relatórios básicos.

## Pré-requisitos

[Implante a implementação do Analytics no ambiente de desenvolvimento](deploy-dev.md): uma implementação do Analytics deve ser publicada no ambiente de desenvolvimento para que esta página possa ser seguida.

## Valide sua implementação de desenvolvimento usando o CX Enterprise Debugger

O CX Enterprise Debugger é uma extensão que mostra todas as tags do CX Enterprise presentes em uma página.

1. Instale a extensão do [Chrome](https://chromewebstore.google.com/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob) ou do Firefox.
2. Navegue até o site de desenvolvimento em que você implementou as tags.
3. Clique no ícone do Adobe CX Enterprise Debugger no navegador.
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
1. Clique na lista suspensa da biblioteca novamente (agora na coluna [!UICONTROL Aprovado]) e selecione **[!UICONTROL Criar e publicar para produção]**.
1. Vá para a guia Ambientes e clique em **[!UICONTROL Ambiente de produção]**.
1. Copie o código de instalação da produção e forneça-o aos proprietários do site. Solicite que eles implementem esse código no ambiente de produção do site.

## Valide a implementação de produção

Confirme se você está vendo os dados na versão ao vivo do site e comece a coleta de dados oficial do Adobe Analytics.

1. Depois de confirmar com os proprietários do site que eles enviaram o código da tag para produção, navegue até a página inicial do site no Chrome e abra o Adobe CX Enterprise Debugger.
2. Se tudo estiver funcionando, você verá dados semelhantes aos seus testes no ambiente de desenvolvimento. Neste ponto, você está coletando dados no site e agora pode começar a usar o Adobe Analytics para relatórios.

## Solução de problemas

**Nenhum dado é exibido no depurador**.

Enquanto estiver no site, abra o console de desenvolvedor do navegador (normalmente F12). Examine o código-fonte da página e verifique se os seguintes itens foram atendidos:

* Não há erros de JavaScript no console. Trabalhe com os proprietários do site da empresa para garantir que todos os erros de JS sejam resolvidos.
* O código do cabeçalho está implementado corretamente: verifique se o código do cabeçalho está dentro da tag `<head>` e se o arquivo existe.
* A biblioteca do AppMeasurement existe: navegue diretamente para a origem de JS para verificar se o arquivo de JS contém o código. Caso contrário, verifique se cada ambiente foi criado e se a biblioteca foi publicada no respectivo ambiente.
* Extensões que interferem: algumas extensões, como bloqueadores de anúncios, podem impedir que as solicitações de imagem sejam acionadas. Desative todas as extensões que possam impedir o envio de dados para a Adobe.

## Próximas etapas

Agora que uma implementação básica foi configurada, sua função na organização pode influenciar o caminho sobre o qual você deseja saber mais:

* [Criar um documento de design da solução](../prepare/solution-design.md): elabore um plano sobre como você deseja usar as variáveis personalizadas e, em seguida, inclua na implementação
* [Introdução ao uso do Analysis Workspace](/help/analyze/analysis-workspace/home.md): mergulhe diretamente no Adobe Analytics usando o recurso principal da ferramenta.
