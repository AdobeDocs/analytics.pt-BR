---
description: A interface do usuário do Adobe Mobile Services combina dados de aplicativos móveis dos seus conjuntos de relatórios do Adobe Analytics com recursos para enviar notificações por mensagens de push e gerar mensagens no aplicativo.
title: Suporte a VRS no Mobile Services
uuid: 1b11279e-d0d8-48c5-a5b5-8020d5ed39da
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Suporte a VRS no Mobile Services

A interface do usuário do Adobe Mobile Services combina dados de aplicativos móveis dos seus conjuntos de relatórios do Adobe Analytics com recursos para enviar notificações por mensagens de push e gerar mensagens no aplicativo.

## Suporte a VRS no Mobile Services {#topic_1D0BABFA64EF42DE9C09B7AA37CACEC5}

A interface do usuário do Adobe Mobile Services combina dados de aplicativos móveis dos seus conjuntos de relatórios do Adobe Analytics com recursos para enviar notificações por mensagens de push e gerar mensagens no aplicativo.

O Adobe Mobile Services oferece suporte a conjuntos de relatórios virtuais. No entanto, se planeja criar um conjunto de relatórios virtual com vários aplicativos e realizar uma atividade com mensagens, será necessário especificar a ID do aplicativo individual como parâmetro. Se estiver criando uma mensagem de push, a ID do aplicativo precisa ser um dos parâmetros do segmento que você está usando. Se estiver criando uma mensagem dentro do aplicativo, a ID do aplicativo precisa ser um dos parâmetros das características que você estabelece para a mensagem. Se isto não for feito, a mensagem será enviada/acionada para todos os usuários de todos os aplicativos que atenderem aos critérios do segmento/disparador.

Para obter mais detalhes, consulte [Conjuntos de relatórios virtuais](https://marketing.adobe.com/resources/help/pt_BR/mobile/c_mob_vrs.html) na documentação do Adobe Mobile Services.
