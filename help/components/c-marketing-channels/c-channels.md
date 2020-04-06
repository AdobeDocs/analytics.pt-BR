---
description: Adicionar ou ativar canais de marketing ao Administrador dos Canais de marketing. Para conjuntos de relatórios sem canais de marketing, uma configuração automática permite criar vários canais para você, juntamente com suas regras. Você pode editar canais predefinidos para atender às suas necessidades ou criar seus próprios (até um total de 25).
subtopic: Marketing channels
title: Gerenciar canais de marketing
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Gerenciar canais de marketing

Adicionar ou ativar canais de marketing ao Administrador dos Canais de marketing. Para conjuntos de relatórios sem canais de marketing, uma configuração automática permite criar vários canais para você, juntamente com suas regras. Você pode editar canais predefinidos para atender às suas necessidades ou criar seus próprios (até um total de 25).

Estas são as diretrizes para a criação de canais:

* Planeje com antecedência, fazendo uma lista de todos os seus canais, para que todas as ocorrências de visitantes sejam categorizadas para o canal correto.
* Sempre inclua canais para as categorias de ocorrências [internas](/help/components/c-marketing-channels/c-faq.md) e ocorrências [diretas](/help/components/c-marketing-channels/c-faq.md) .

A adição de canais à página é feita independentemente da criação de regras na página Regras [!UICONTROL Marketing Channels] de processamento de Canais [](/help/components/c-marketing-channels/c-rules.md) de marketing. Você associa regras a canais ao criar a regra.

## Adição de canais de marketing {#add-mktg-channels}

Adicione canais de marketing ao Administrador dos Canais de marketing.

>[!NOTE] Não é possível excluir um canal. Se não quiser usar um canal, desative-o ou renomeie-o, e guarde-o para uso posterior.

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Na [!UICONTROL Report Suite Manager] página, selecione um conjunto de relatórios.

   Se você selecionar vários conjuntos de relatórios, selecione um modelo que copie as configurações do modelo para os conjuntos de relatórios selecionados.

   See [Apply template report suite settings to multiple report suites](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

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
| Habilitado | Ativa ou desativa este canal de marketing. |
| Nome do Canal | O nome amigável do canal de marketing. |
| Substituir Canal de Último Toque | Permite que você escolha se deseja substituir um canal existente e persistente de último toque pelo canal selecionado. Se você marcar essa caixa de seleção, qualquer canal (incluindo Direto e Interno) substituirá um canal de último toque existente. O resultado é uma conversão atribuída a um canal que pode não merecer o crédito. Por exemplo, essa opção pode garantir que o canal Direto não receba crédito pela conversão se o usuário tiver sido adquirido anteriormente por meio do canal de Pesquisa Natural. |
| Análise de detalhamento | Permite detalhar um canal por esse valor. Você pode adicionar possíveis detalhamentos de canal (subcanais) ao criar classificações [de canais de](/help/components/c-marketing-channels/classifictions-mchannel.md)marketing. |
| Tipo | Especifica como o usuário chegou ao site. É possível selecionar online ou offline. Use canais on-line para visitantes que vêm através de um mecanismo de pesquisa ou campanha de e-mail. canais offline se aplicam a visitantes que encontraram seu site por meio de cupons de jornais ou anúncios de revistas. Os canais offline geralmente incluem dados importados por meio das Fontes de Dados do relatórios. Consulte [Origens de Dados](https://docs.adobe.com/content/help/pt-BR/analytics/import/data-sources/datasrc-home.html). Consulte [Adicionar dados offline](/help/components/c-marketing-channels/c-getting-started-mchannel.md). |
| Cor | A cor associada a este canal de marketing. Essa cor representa o canal no relatório de Canal de marketing. |

## Definir canais

Antes que os dados de canais e canais possam ser exibidos no relatório, crie os canais e as regras subjacentes que processam os dados. Você também pode criar quantias de custo e orçamento para canais associados e especificar quanto tempo deseja que o período de envolvimento do visitante dure. Você executa tarefas de configuração de relatório nas Ferramentas administrativas.

Pense em um canal como um container para visitas. As regras atribuem visitas ao container adequado.

![](assets/buckets_2.png)

A Adobe fornece diversos canais predefinidos durante uma  [configuração automática](/help/components/c-marketing-channels/c-getting-started-mchannel.md) que pode ser editada conforme seus requisitos.

>[!NOTE]
>
>A Adobe recomenda configurar seu relatório em um conjunto de relatório que pode ser usado como modelo para fins de teste. Você pode usar o modelo para aplicar o canal e os conjuntos de regras globalmente a um ou mais conjuntos de relatórios de produção.
>
>See [Apply Template Report Suite Settings to Multiple Report Suites](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

### Pré-requisitos {#prereqs}

Se necessário, entre em contato com o Atendimento ao cliente para obter ajuda com esses pré-requisitos:

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

   Consulte [Configurações gerais da conta](https://docs.adobe.com/content/help/pt-BR/analytics/admin/admin-tools/general-acct-settings-admin.html) na ajuda do Analytics para obter mais informações.

* Configure o acesso às dimensões do Canal de marketing.

   See [Marketing Channels permissions](/help/components/c-marketing-channels/c-channel-report-access.md).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

### Observações importantes de processamento {#important-proc-rules}

* O sistema processa as regras na ordem especificada e, quando uma regra é atendida, o sistema para de processar as regras restantes.
* As regras podem acessar variáveis que o VISTA definiu, mas não podem acessar dados que o VISTA excluiu.
* Os Canais armazenam somente métricas de conversão. As métricas de tráfego não estão disponíveis.
* Dois canais de marketing nunca recebem crédito pelo mesmo evento (como compras ou cliques). Dessa forma, os canais de marketing diferem das eVars (onde duas eVars podem receber crédito pelo mesmo evento).
* O relatório pode processar até 25 canais de cada vez.

