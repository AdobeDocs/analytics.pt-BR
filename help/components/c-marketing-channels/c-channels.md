---
description: Adicionar ou ativar canais de marketing ao Administrador dos Canais de marketing. Em conjuntos de relatórios sem canais de marketing, uma configuração automática permite criar diversos canais e suas regras. É possível editar os canais predefinidos para atender às suas necessidades ou criar seus próprios (até um total de 25).
subtopic: Marketing channels
title: Gerenciar canais de marketing
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: c10a12781a8fe52b7b897cd337dc686aa0bbb240

---


# Gerenciar canais de marketing

Adicionar ou ativar canais de marketing ao Administrador dos Canais de marketing. Em conjuntos de relatórios sem canais de marketing, uma configuração automática permite criar diversos canais e suas regras. É possível editar os canais predefinidos para atender às suas necessidades ou criar seus próprios (até um total de 25).

A seguir, as orientações para a criação de canais:

* Planeje com antecedência, fazendo uma lista de todos os canais, para que todas ocorrências de visitantes sejam categorizadas para o canal correto.
* Sempre inclua canais para as categorias de ocorrências [Internas](/help/components/c-marketing-channels/c-faq.md) e [Diretas](/help/components/c-marketing-channels/c-faq.md).

Adding channels to the [!UICONTROL Marketing Channels] page is done independently of creating rules on the [Marketing Channel Processing Rules](/help/components/c-marketing-channels/c-rules.md) page. Ao criar regras, associe-as aos canais.

## Adição de canais de marketing {#add-mktg-channels}

Adicione canais de marketing ao Administrador dos Canais de marketing.

> [!NOTE] Não é possível excluir um canal. Se não quiser usar um canal, desative-o ou renomeie-o, e guarde-o para uso posterior.

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Na [!UICONTROL Report Suite Manager] página, selecione um conjunto de relatórios.

   Se você selecionar múltiplos conjuntos de ferramentas de relatório, será necessário selecionar um modelo que copie as configurações do modelo para os conjuntos de ferramentas de relatório selecionados.

   Consulte [Aplicar configurações do conjunto de relatório de modelo a múltiplos conjuntos de relatório](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Clique em **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   Se seu conjunto de relatórios não tem canais definidos, a página [Configuração automática](/help/components/c-marketing-channels/c-getting-started-mchannel.md) é exibida.

1. Na [!UICONTROL Marketing Channel Manager] página, clique em **[!UICONTROL Add Channel]**.

   Essa opção não está disponível quando são definidos 25 canais.

1. Clique em **[!UICONTROL Save.]**
1. Para configurar regras para o canal, clique em **[!UICONTROL Marketing Channel Processing Rules]**.

   Consulte [Criar regras de processamento de canal de marketing](/help/components/c-marketing-channels/c-rules.md).

## Gerenciador de canal de marketing - definições de interface {#mktg-channel-mgr}

Definições de campo para a [!UICONTROL Marketing Channel Manager] página.

| Campo | Definição |
|--- |--- |
| Ativado | Ativa ou desativa este canal de marketing. |
| ID de canal | O nome amigável do canal de marketing. |
| Substituir canal de último toque | É possível escolher substituir um canal existente e persistente de último toque pelo canal selecionado. Se você marcar esta caixa de seleção, qualquer canal (incluindo canal Direto e Interno) substituirá um canal de último contato existente. O resultado é uma conversão atribuída a um canal que pode não merecer o crédito. Por exemplo, esta opção pode garantir que o Canal direto não receba crédito pela conversão se o usuário for avisado por meio do canal de Pesquisa Natural. |
| Análise de canal | Permite analisar um canal de acordo com este valor. You can add possible channel breakdowns (subchannels) when creating [marketing channel classifications](/help/components/c-marketing-channels/classifictions-mchannel.md). |
| Tipo | Especifica como o usuário chegou ao seu site. É possível selecionar online ou offline. É possível usar canais Online para visitantes que chegam por meio de um mecanismo de busca ou campanha por email. Os canais offline são aplicados a visitantes que localizam seu site por meio de cupons em jornais ou anúncios de revistas. Em geral, os canais offline incluem dados importados por meio de Origens de Dados de relatórios. Consulte [Origens de Dados](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html). Consulte [Adicionar dados offline](/help/components/c-marketing-channels/c-getting-started-mchannel.md). |
| Cor do canal | A cor associada a este canal de marketing. Essa cor representa o canal no relatório de Canal de marketing. |

## Definir canais

Antes de ser possível exibir canais e dados de canal no relatório, é preciso criar os canais e as regras subjacentes que processam os dados. Você também pode criar valores de custo e orçamento para os canais associados no relatório, e especificar a duração desejada para o período de envolvimento do visitante. As tarefas de configuração do relatório são realizadas nas Ferramentas de administração.

Imagine um canal como um recipiente para as visitas. As regras atribuem as visitas ao recipiente apropriado.

![](assets/buckets_2.png)

A Adobe fornece diversos canais predefinidos durante uma  [configuração automática](/help/components/c-marketing-channels/c-getting-started-mchannel.md) que pode ser editada conforme seus requisitos.

>[!NOTE]
>
>A Adobe recomenda configurar seu relatório em um conjunto de relatório que pode ser usado como modelo para fins de teste. É possível usar o modelo para aplicar globalmente as definições de canal e regras a um ou mais conjuntos de relatório de produção.
>
>Consulte [Aplicar configurações de conjuntos de relatório de modelo a múltiplos conjuntos de relatório](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

### Pré-requisitos {#prereqs}

Se necessário, entre em contato com o Atendimento ao cliente para obter ajuda com esses pré-requisitos:

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

   Consulte [Configurações gerais da conta](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/general-acct-settings-admin.html) na ajuda do Analytics para obter mais informações.

* Configure o acesso às dimensões do Canal de marketing.

   See [Marketing Channels permissions](/help/components/c-marketing-channels/c-channel-report-access.md).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

### Observações importantes de processamento {#important-proc-rules}

* O sistema processa as regras na ordem especificada e, quando uma regra é atendida, o sistema para de processar as regras restantes.
* As regras podem acessar variáveis definidas pelo VISTA, mas não podem acessar dados excluídos pelo VISTA.
* Os canais só armazenam métricas de conversão. As métricas de tráfego não estão disponíveis.
* Dois canais de marketing nunca recebem crédito pelo mesmo evento (como compras ou cliques). Dessa forma, os canais de marketing diferem das eVars (já que duas eVars podem receber crédito pelo mesmo evento).
* O relatório pode processar até 25 canais simultaneamente.

