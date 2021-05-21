---
description: A interface do usuário do Adobe Mobile Services combina dados de aplicativos móveis dos seus conjuntos de relatórios do Adobe Analytics com recursos para enviar notificações por mensagens de push e gerar mensagens no aplicativo.
title: Suporte a VRS no Mobile Services
uuid: 1b11279e-d0d8-48c5-a5b5-8020d5ed39da
exl-id: 3082333a-514d-45c6-9432-da32bd27a2eb
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '221'
ht-degree: 100%

---

# Suporte a VRS no Mobile Services

A interface do usuário do Adobe Mobile Services combina dados de aplicativos móveis dos seus conjuntos de relatórios do Adobe Analytics com recursos para enviar notificações por mensagens de push e gerar mensagens no aplicativo.

## Suporte a VRS no Mobile Services {#topic_1D0BABFA64EF42DE9C09B7AA37CACEC5}

A interface do usuário do Adobe Mobile Services combina dados de aplicativos móveis dos seus conjuntos de relatórios do Adobe Analytics com recursos para enviar notificações por mensagens de push e gerar mensagens no aplicativo.

O Adobe Mobile Services oferece suporte a conjuntos de relatórios virtuais. No entanto, se planeja criar um conjunto de relatórios virtual com vários aplicativos e realizar uma atividade com mensagens, será necessário especificar a ID do aplicativo individual como parâmetro. Se estiver criando uma mensagem de push, a ID do aplicativo precisa ser um dos parâmetros do segmento que você está usando. Se estiver criando uma mensagem dentro do aplicativo, a ID do aplicativo precisa ser um dos parâmetros das características que você estabelece para a mensagem. Se isto não for feito, a mensagem será enviada/acionada para todos os usuários de todos os aplicativos que atenderem aos critérios do segmento/disparador.

Para obter mais detalhes, consulte [Conjuntos de relatórios virtuais](https://docs.adobe.com/content/help/pt-BR/mobile-services/using/manage-apps-ug/c-mob-vrs.html) na documentação do Adobe Mobile Services.
