---
description: Adicionar ou habilitar canais de marketing ao Administrador dos Canais de marketing. Para conjuntos de relatórios que não têm canais de marketing, uma configuração automática permite criar vários canais para você, juntamente com suas regras. É possível editar canais predefinidos de acordo com as suas necessidades ou criar os seus próprios (até um total de 25).
subtopic: Marketing channels
title: Gerenciar canais de marketing
feature: Marketing Channels
exl-id: a768a4c2-f922-4d96-a9fb-78a1dfac04d8
role: Admin
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 64%

---

# Gerenciar canais de marketing

>[!NOTE]
>
> Para obter informações gerais sobre canais de marketing, consulte [Introdução aos canais de marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md).
>
> Para maximizar a eficácia dos canais de marketing para a atribuição e o Customer Journey Analytics, publicamos algumas [práticas recomendadas revisadas](/help/components/c-marketing-channels/mchannel-best-practices.md).

**[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]** > **[!UICONTROL Editar configurações]** > **[!UICONTROL Canais de marketing]** > **[!UICONTROL Gerente de canal de marketing]**.

Adicionar ou habilitar canais de marketing ao Administrador dos Canais de marketing. Para conjuntos de relatórios que não têm canais de marketing, uma configuração automática permite criar vários canais para você, juntamente com suas regras. É possível editar canais predefinidos de acordo com as suas necessidades ou criar os seus próprios (até um total de 25).

A adição de canais à página [!UICONTROL Canais de marketing] é feita independentemente da criação de regras na página [Regras de processamento de canal de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md). Associe regras a canais ao criar a regra.

Estas são as diretrizes para a criação de canais:

* Planeje com antecedência fazendo uma lista de todos os canais, para que todas as ocorrências do visitante sejam categorizadas no canal correto.
* Inclua canais para as categorias de ocorrências [internas](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md).
* Inclua um canal “Outras Campanhas” abrangente que será colocado depois de canais pagos e antes de canais orgânicos.


## Pré-requisitos {#prereqs}

* Configure o acesso às dimensões do Canal de marketing.

  Consulte [Permissões de canais de marketing](/help/components/c-marketing-channels/c-channel-report-access.md).

## Adição de canais de marketing {#add-mktg-channels}

Adicione canais de marketing ao Administrador dos Canais de marketing.

>[!NOTE]
>
>Não é possível excluir um canal. Se não quiser usar um canal, desative-o ou renomeie-o, e guarde-o para uso posterior.

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Conjuntos de relatórios]**.
1. Na página do [!UICONTROL Gerenciador de conjunto de relatórios], selecione um conjunto de relatórios.

   Se você selecionar múltiplos conjuntos de relatório, será necessário selecionar um modelo que copie as configurações do modelo para os conjuntos de relatório selecionados.

   Consulte [Aplicar configurações do modelo de conjunto de relatórios a múltiplos conjuntos de relatórios](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Clique em **[!UICONTROL Editar configurações]** > **[!UICONTROL Canais de marketing]** > **[!UICONTROL Gerenciador de canal de marketing]**.

   Se seu conjunto de relatórios não tem canais definidos, a página [Configuração automática](/help/components/c-marketing-channels/c-getting-started-mchannel.md) é exibida.

1. Na página do [!UICONTROL Gerenciador de canal de marketing], clique em **[!UICONTROL Adicionar canal]**.

   Essa opção não está disponível quando são definidos 25 canais.

1. Clique em **[!UICONTROL Salvar.]**
1. Para configurar regras para o canal, clique em **[!UICONTROL Regras de processamento de canal de marketing]**.

   Consulte [Criar regras de processamento de canal de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md).

## Aplicar configurações de canal {#mktg-channel-mgr}

Há várias configurações que podem ser aplicadas a cada canal na página [!UICONTROL Gerenciador de canais de marketing].

| Campo | Definição |
|--- |--- |
| Habilitado | Ativa ou desativa esse canal de marketing. |
| Nome do canal | O nome amigável do canal de marketing. |
| Substituir canal de último contato | Permite escolher se deseja substituir um canal de último contato persistente existente pelo canal selecionado. Se você marcar essa caixa de seleção, qualquer canal (incluindo Direto e Interno) substituirá um canal de último toque existente. O resultado é uma conversão atribuída a um canal que pode não merecer o crédito. Por exemplo, essa opção pode garantir que o canal Direto não receba crédito pela conversão se o usuário tiver sido adquirido anteriormente por meio do canal de Pesquisa natural. |
| Detalhamento de canal | Permite dividir um canal por esse valor. É possível adicionar possíveis detalhamentos de canal (subcanais) ao criar [classificações de canais de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/classifications-mchannel.md). |
| Tipo | Especifica como o usuário veio ao site. É possível selecionar online ou offline. Use os canais online para visitantes que acessam um mecanismo de pesquisa ou campanha por email. Os canais offline se aplicam a visitantes que encontraram seu site por meio de cupons de jornais ou anúncios de revistas. Em geral, os canais offline incluem dados importados por meio de Origens de Dados de relatórios. Consulte [Origens de Dados](/help/import/data-sources/overview.md). Consulte [Adicionar dados offline](/help/components/c-marketing-channels/c-getting-started-mchannel.md). |

### Práticas recomendadas de substituição

É uma prática recomendada desmarcar a opção de substituição de último toque de canais diretos e internos, para que eles não possam receber crédito de outros canais de último toque persistentes (ou entre si).

![](assets/int-channel2.png)

## Definir regras de canal

Antes de ser possível exibir canais e dados de canal no relatório, é preciso criar os canais e as regras subjacentes que processam os dados. Você também pode especificar quanto tempo você deseja que o [período de envolvimento do visitante](/help/admin/tools/manage-rs/edit-settings/marketing-channels/visitor-engagement.md) dure.

A Adobe fornece vários canais predefinidos durante uma [configuração automática](/help/components/c-marketing-channels/c-getting-started-mchannel.md) que você pode editar para atender às suas necessidades. Além disso, você pode modificar essa configuração e definir regras personalizadas nas [Regras de processamento de canal de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md).

>[!NOTE]
>
>A Adobe recomenda configurar seu relatório em um conjunto de relatório que pode ser usado como modelo para fins de teste. É possível usar o modelo para aplicar globalmente as definições de canal e regras a um ou mais conjuntos de relatório de produção.
>
>Consulte [Aplicar configurações do modelo de conjunto de relatórios a múltiplos conjuntos de relatórios](/help/components/c-marketing-channels/c-getting-started-mchannel.md).
