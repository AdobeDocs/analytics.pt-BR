---
title: Introdução aos Canais de marketing
description: Saiba mais sobre o fluxo de trabalho de Canais de marketing, a configuração automática e como aplicar configurações de conjunto de relatórios de modelo a vários conjuntos de relatórios.
feature: Marketing Channels
exl-id: 35938bf9-89ab-434f-9dc2-7a65251412ef
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: ht
source-wordcount: '810'
ht-degree: 100%

---

# Introdução aos canais de marketing

>[!NOTE]
>
>Para maximizar a eficácia dos canais de marketing para atribuição e análise da jornada do cliente, publicamos algumas [práticas recomendadas revisadas](/help/components/c-marketing-channels/mchannel-best-practices.md).
>
>Admins do Analytics podem gerenciar os canais de marketing de suas organizações, conforme descrito em [Gerenciar canais de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md).

Os Canais de marketing são usados para fornecer informações sobre como os visitantes chegam ao site. É possível personalizar as regras de processamento de canal de marketing com base nos canais que você deseja rastrear e na forma como deseja rastreá-los.

Os Canais de marketing giram em torno de métricas de Primeiro e último toque, que são componentes de métricas de conversão padrão.

## Fluxo de trabalho de Canais de marketing

![](assets/step1_icon.png) Definir cada canal com base nos requisitos da empresa.

Definir os canais que você usa é um dos componentes mais importantes dos Canais de marketing. A definição dos canais pode exigir a colaboração entre vários indivíduos em sua organização. Estas são algumas perguntas a serem consideradas:

* Você está usando uma pesquisa paga?
* Você está usando campanhas por email? Você está usando várias campanhas de email que gostaria de rastrear separadamente?
* Você possui afiliadas que direcionam o tráfego para seu site? Existem afiliadas que você deseja rastrear individualmente?
* Há campanhas externas que seria vantajoso acompanhar separadamente?
* Você deseja agregar todos os sites de redes sociais ou há algum que você deseja rastrear individualmente?
* Existem outros canais que podem afetar a conversão que você deseja rastrear?

Você pode encontar uma lista de canais recomendados em [Perguntas frequentes e exemplos](/help/components/c-marketing-channels/c-faq.md). Crie uma lista de canais que deseja usar para facilitar a habilitação e definição dos canais durante sua criação.

![](assets/step2_icon.png) Adicione canais de marketing na página [!UICONTROL Gerenciador de canal de marketing].

Após definir quais canais serão monitorados, habilite-os em **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de relatórios]**.

Consulte [Sobre os canais e regras](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md) para obter pré-requisitos importantes e informações conceituais.

Consulte [Adicionar canais de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md) para obter o procedimento.

>[!NOTE]
>
>Se os Canais de marketing não tiverem sido configurados anteriormente, a [configuração automática](/help/components/c-marketing-channels/c-getting-started-mchannel.md) será exibida. Esta configuração fornece vários canais pré-configurados que você pode personalizar. A Adobe recomenda usar essas regras como modelo. No entanto, se você já tiver definições de canal sólidas, ignore a configuração automática.

![](assets/step3_icon.png) Configure e refine todas as regras de canais na página [!UICONTROL Regras de processamento de Canal de marketing].

Após criar os canais na página [!UICONTROL Gerenciador de canais de marketing], configure as regras para que os canais possam recuperar e relatar dados.

Consulte [Regras de processamento de canais de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md).

Se os canais foram criados na configuração automática, as regras nesses canais já estão definidas. Você pode modificá-los para atender às suas necessidades.

## Configuração automática para canais de marketing {#run-auto-setup}

O Relatório de canal de marketing vem com uma página de configuração, que é utilizada uma única vez, como introdução. Ele fornece diversos canais de marketing que podem ser utilizados para acompanhamento. É possível ignorar essa configuração inicial se você não encontrar problemas em criar canais e regras. No entanto, a Adobe recomenda que você permita que o assistente crie os canais para você. A configuração automática permite visualizar como as regras são construídas, ou editá-las conforme necessário. Você pode desabilitar ou excluir os canais predefinidos a qualquer momento.

Como executar a configuração automática para os Canais de marketing.

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]**.
1. No [!UICONTROL Gerenciador de conjunto de relatórios], selecione um conjunto de relatórios.
1. Clique em **[!UICONTROL Editar configurações]** > **[!UICONTROL Canais de marketing]** > **[!UICONTROL Gerenciador de canal de marketing]**.

   ![Resultado da etapa](assets/wizard.png)

   >[!NOTE]
   >
   >A página [!UICONTROL Canais de marketing: configuração automática] é exibida automaticamente quando você acessa os aplicativos de configuração de canal nas Ferramentas de administração. (Consulte [Gerenciador de canal de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md).) Esta página não é exibida se o seu conjunto de relatórios tiver um ou mais canais de marketing. Não é possível acessar esta página novamente, a menos que você selecione outro conjunto de relatórios que não tenha canais de marketing.

1. Certifique-se de que os canais que deseja criar estejam selecionados.

   Quando selecionados, **[!UICONTROL Email]**, **[!UICONTROL Exibir]** e **[!UICONTROL Afiliado]** são campos obrigatórios.

1. Clique em **[!UICONTROL Salvar]**.

## Aplicar configurações do conjunto de relatório de modelo a múltiplos conjuntos de relatório

Como usar um conjunto de relatórios principal como modelo para testar a configuração do canal de marketing. Para economizar tempo, aplique esse modelo a um ou mais conjuntos de relatório de produção em uma atualização em massa. Execute essa tarefa para canais e conjuntos de regras separadamente.

>[!NOTE]
>
>Aplique canais a partir de um modelo antes de aplicar os conjuntos de regras. Seus canais devem ser os mesmos em todos os conjuntos de relatórios ao executar esse procedimento.

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]**.
1. Na página do **[!UICONTROL Gerenciador de conjunto de relatórios]**, selecione o conjunto de relatórios modelo, bem como um ou mais conjuntos de relatórios de destino.
1. Clique em **[!UICONTROL Editar configurações]** > **[!UICONTROL Canais de marketing]** > **[!UICONTROL Gerenciador de canal de marketing]**.
1. Na página **[!UICONTROL Selecionar os principais conjuntos de relatórios]**, selecione um conjunto de relatórios modelo.
1. Clique em **[!UICONTROL Salvar tudo]**.
1. Aplicar regras de um modelo a vários conjuntos de relatórios:
   1. Retorne à página do [!UICONTROL Gerenciador de conjuntos de relatórios].
   1. Selecione o conjunto de relatórios modelo, bem como um ou mais conjuntos de relatórios de destino.
   1. Clique em **[!UICONTROL Editar configurações]** > **[!UICONTROL Canais de marketing]** > **[!UICONTROL Regras de processamento de canal de marketing]**.
   1. Clique em **[!UICONTROL Salvar]**. Se o botão Salvar estiver desabilitado nessa etapa, habilite-o expandindo uma das regras.
