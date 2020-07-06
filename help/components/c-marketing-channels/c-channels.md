---
description: Adicionar ou ativar canais de marketing ao Administrador dos Canais de marketing. Em conjuntos de relatórios sem canais de marketing, uma configuração automática permite criar diversos canais e suas regras. É possível editar os canais predefinidos para atender às suas necessidades ou criar seus próprios (até um total de 25).
subtopic: Marketing channels
title: Gerenciar canais de marketing
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 86%

---


# Gerenciar canais de marketing

Adicionar ou ativar canais de marketing ao Administrador dos Canais de marketing. Em conjuntos de relatórios sem canais de marketing, uma configuração automática permite criar diversos canais e suas regras. É possível editar os canais predefinidos para atender às suas necessidades ou criar seus próprios (até um total de 25).

A inclusão de [!UICONTROL Canais de marketing] é feita de forma independente da criação de regras na página [Regras de Processamento de Canal de marketing](/help/components/c-marketing-channels/c-rules.md). Ao criar regras, associe-as aos canais.

A seguir, as orientações para a criação de canais:

* Planeje com antecedência, fazendo uma lista de todos os canais, para que todas ocorrências de visitantes sejam categorizadas para o canal correto.
* Include channels for the categories of [Internal](/help/components/c-marketing-channels/c-rules.md) hits and [Direct](/help/components/c-marketing-channels/c-rules.md) hits.
* Incluir um canal &quot;Outras Campanhas&quot; catch-all, a ser colocado depois de canais pagos e antes de canais orgânicos.


## Pré-requisitos {#prereqs}

Se necessário, entre em contato com o Atendimento ao cliente para obter ajuda com esses pré-requisitos:

* No Admin Console (Configurações gerais da conta), ative a opção **[!UICONTROL Nível de conversão]** (comércio eletrônico) para o conjunto de relatórios.

   Consulte [Configurações gerais da conta](https://docs.adobe.com/content/help/pt-BR/analytics/admin/admin-tools/general-acct-settings-admin.html) na ajuda do Analytics para obter mais informações.

* Configure o acesso às dimensões do Canal de marketing.

   Consulte [Permissões de canais de marketing](/help/components/c-marketing-channels/c-channel-report-access.md).

* Confirme se seu gerente de conta ativou os **[!UICONTROL Relatórios de canal]** do seu conjunto de relatórios.

## Adição de canais de marketing {#add-mktg-channels}

Adicione canais de marketing ao Administrador dos Canais de marketing.

>[!NOTE]
>
>Não é possível excluir um canal. Se não quiser usar um canal, desative-o ou renomeie-o, e guarde-o para uso posterior.

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]**.
1. Na página do [!UICONTROL Gerenciador de conjunto de relatórios], selecione um conjunto de relatórios.

   Se você selecionar múltiplos conjuntos de ferramentas de relatório, será necessário selecionar um modelo que copie as configurações do modelo para os conjuntos de ferramentas de relatório selecionados.

   Consulte [Aplicar configurações do conjunto de relatório de modelo a múltiplos conjuntos de relatório](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Clique em **[!UICONTROL Editar configurações]** > **[!UICONTROL Canais de marketing]** > **[!UICONTROL Gerenciador de canal de marketing]**.

   Se seu conjunto de relatórios não tem canais definidos, a página [Configuração automática](/help/components/c-marketing-channels/c-getting-started-mchannel.md) é exibida.

1. Na página do [!UICONTROL Gerenciador de canal de marketing], clique em **[!UICONTROL Adicionar canal]**.

   Essa opção não está disponível quando são definidos 25 canais.

1. Clique em **[!UICONTROL Salvar.]**
1. Para configurar regras para o canal, clique em **[!UICONTROL Regras de processamento de canal de marketing]**.

   Consulte [Criar regras de processamento de canal de marketing](/help/components/c-marketing-channels/c-rules.md).

## Aplicar configurações de canal {#mktg-channel-mgr}

Há várias configurações que podem ser aplicadas a cada canal na página Gerenciador [!UICONTROL de Canais de] marketing.

| Campo | Definição |
|--- |--- |
| Ativado | Ativa ou desativa este canal de marketing. |
| ID de canal | O nome amigável do canal de marketing. |
| Substituir canal de último toque | É possível escolher substituir um canal existente e persistente de último toque pelo canal selecionado. Se você marcar esta caixa de seleção, qualquer canal (incluindo canal Direto e Interno) substituirá um canal de último contato existente. O resultado é uma conversão atribuída a um canal que pode não merecer o crédito. Por exemplo, esta opção pode garantir que o Canal direto não receba crédito pela conversão se o usuário for avisado por meio do canal de Pesquisa Natural. |
| Análise de canal | Permite analisar um canal de acordo com este valor. É possível adicionar possíveis detalhamentos de canal (subcanais) ao criar [classificações de canais de marketing](/help/components/c-marketing-channels/classifictions-mchannel.md). |
| Tipo | Especifica como o usuário chegou ao seu site. É possível selecionar online ou offline. É possível usar canais Online para visitantes que chegam por meio de um mecanismo de busca ou campanha por email. Os canais offline são aplicados a visitantes que localizam seu site por meio de cupons em jornais ou anúncios de revistas. Em geral, os canais offline incluem dados importados por meio de Origens de Dados de relatórios. Consulte [Origens de Dados](https://docs.adobe.com/content/help/pt-BR/analytics/import/data-sources/datasrc-home.html). Consulte [Adicionar dados offline](/help/components/c-marketing-channels/c-getting-started-mchannel.md). |
| Cor do canal | Somente Relatórios e Analytics: A cor associada a este canal de marketing. Essa cor representa o canal no relatório de Canal de marketing. |

### Substituir práticas recomendadas

É uma prática recomendada desmarcar a opção de substituição de último toque de canais Diretos e Internos, para que eles não possam receber crédito de outros canais de último toque persistentes (ou entre si).

![](assets/int-channel2.png)

## Definir regras de canal

Antes de ser possível exibir canais e dados de canal no relatório, é preciso criar os canais e as regras subjacentes que processam os dados. Você também pode especificar quanto tempo deseja que o período [de envolvimento do](/help/components/c-marketing-channels/visitor-engagement.md) visitante dure.

A Adobe fornece vários canais predefinidos durante uma configuração [](/help/components/c-marketing-channels/c-getting-started-mchannel.md) automática que você pode editar para atender às suas necessidades. Além disso, você pode modificar essa configuração e definir regras personalizadas nas regras [de processamento do](/help/components/c-marketing-channels/c-rules.md)Marketing Canal.

>[!NOTE]
>
>A Adobe recomenda configurar seu relatório em um conjunto de relatório que pode ser usado como modelo para fins de teste. É possível usar o modelo para aplicar globalmente as definições de canal e regras a um ou mais conjuntos de relatório de produção.
>
>Consulte [Aplicar configurações de conjuntos de relatório de modelo a múltiplos conjuntos de relatório](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

