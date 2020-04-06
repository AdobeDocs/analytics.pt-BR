---
title: Introdução aos Canais de marketing
description: Saiba mais sobre o fluxo de trabalho dos Canais de marketing, a configuração automática e como aplicar configurações de conjunto de relatórios de modelo a vários conjuntos de relatórios.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Introdução aos Canais de marketing

Os Canais de marketing são normalmente usados para fornecer informações sobre como os visitantes chegam ao seu site. Você pode personalizar suas Regras de processamento de Canais de marketing com base nos canais que deseja rastrear e em como deseja acompanhá-los.

Os Canais de marketing giram em torno de métricas de Primeiro e último toque, que são componentes de métricas de conversão padrão.

## Fluxo de trabalho dos Canais de marketing

![](assets/step1_icon.png) Definir cada canal com base nos requisitos da empresa.

Definir os canais que você usa é um dos componentes mais importantes dos Canais de Marketing. A definição dos canais pode exigir a colaboração entre vários indivíduos em sua organização. Estas são algumas perguntas a serem consideradas:

* Você está usando uma busca paga?
* Você está usando campanhas por email? Você está usando várias campanhas de email que deseja rastrear separadamente?
* Você tem afiliados que direcionam o tráfego para o seu site? Há afiliados que você deseja rastrear individualmente?
* Há campanhas externas que seriam vantajosas para o rastreamento separado?
* Deseja agregação em todos os sites de redes sociais ou há algum que você queira rastrear individualmente?
* Há outros canais que podem afetar a conversão que você deseja rastrear?

Há uma lista de canais recomendados em  [Perguntas mais frequentes e exemplos](/help/components/c-marketing-channels/c-faq.md). Crie uma lista de canais que deseja usar para facilitar a ativação e definição dos canais durante sua criação.

![](assets/step2_icon.png) Adicione canais de marketing na [!UICONTROL Marketing Channel Manager] página.

After defining what channels to track, you enable them in **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

Consulte [Sobre os canais e regras](/help/components/c-marketing-channels/c-channels.md) para obter pré-requisitos importantes e informações conceituais.

Consulte [Adicionar canais de marketing](/help/components/c-marketing-channels/c-channels.md) para obter o procedimento.

>[!NOTE]
>
>Se os Canais de marketing não tiverem sido configurados anteriormente, a [configuração automática](/help/components/c-marketing-channels/c-getting-started-mchannel.md) será exibida. Esta configuração fornece vários canais pré-configurados que podem ser personalizados. A Adobe recomenda usar essas regras como modelo. No entanto, se você já tiver definições sólidas de canal, poderá ignorar a configuração automática.

![](assets/step3_icon.png) Configure ou refine cada regra de canal na [!UICONTROL Marketing Channel Processing Rules] página.

Depois de criar canais na [!UICONTROL Marketing Channel Manager] página, configure as regras para que os canais possam recuperar e relatar dados.

See [Marketing Channel Processing Rules](/help/components/c-marketing-channels/c-rules.md).

Se canais tiverem sido criados na configuração automática, as regras desses canais serão definidas. Você pode modificá-las de acordo com suas necessidades.

## Configuração automática para Canais de marketing {#run-auto-setup}

O Relatório de canal de marketing vem com uma página de configuração, que é utilizada uma única vez, como introdução. Ele fornece diversos canais de marketing que podem ser utilizados para acompanhamento. É possível ignorar essa configuração inicial se você não encontrar problemas em criar canais e regras. No entanto, a Adobe recomenda que você permita que o assistente crie os canais para você. A configuração automática permite visualizar como as regras são construídas, ou editá-las conforme necessário. Você pode desativar ou excluir os canais predefinidos a qualquer momento.

Como executar a configuração automática para os Canais de marketing.

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Na página [!UICONTROL Report Suite Manager], selecione um conjunto de relatórios.
1. Clique em **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   ![Resultado da etapa](assets/wizard.png)

   >[!NOTE]
   >
   >The [!UICONTROL Marketing Channels: Auto Setup] page displays automatically when you access channel configuration applications in Admin Tools. (Consulte [Gerenciador de canal de marketing](/help/components/c-marketing-channels/c-channels.md).) Essa página não será exibida se seu conjunto de ferramentas de relatório contiver um ou mais canais de marketing. Não é possível acessar essa página novamente a menos que você selecione outro conjunto de relatórios que não contenha canais de marketing.

1. Certifique-se de que os canais que deseja criar estejam selecionados.

   Quando selecionados, **[!UICONTROL Email]**, **[!UICONTROL Display]** e **[!UICONTROL Affiliate]** forem campos obrigatórios.

1. Clique em **[!UICONTROL Save]**.

## Aplicar configurações do conjunto de relatório de modelo a múltiplos conjuntos de relatório

Como usar um conjunto de relatórios mestre como modelo para testar sua configuração de canal de marketing. Para economizar tempo, aplique esse modelo a um ou mais conjuntos de relatório de produção em uma atualização em massa. Você executa essa tarefa para canais e conjuntos de regras separadamente.

>[!NOTE] Aplique canais a partir de um modelo antes de aplicar os conjuntos de regras. Seus canais devem ser os mesmos em todos os conjuntos de ferramentas de relatório ao executar esse procedimento.

1. Certifique-se de que o Relatório de canal de marketing esteja ativado para os conjuntos de relatórios selecionados. Seu Gerente de contas deve executar essa etapa.
1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. On the **[!UICONTROL Report Suite Manager]** page, select the template report suite, as well as one or more target report suites.
1. Clique em **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.
1. Na **[!UICONTROL Select Master Report Suites]** página, selecione um conjunto de relatórios modelo.
1. Clique em **[!UICONTROL Save All]**.
1. Aplicar regras de um modelo a vários conjuntos de relatórios:
   1. Volte para a [!UICONTROL Report Suite Manager] página.
   1. Selecione o conjunto de relatórios modelo, bem como um ou mais conjuntos de relatórios de destino.
   1. Clique em **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.
   1. Clique em **[!UICONTROL Save]**. Se o botão Salvar estiver desativado nessa etapa, ative-o expandindo uma das regras.

