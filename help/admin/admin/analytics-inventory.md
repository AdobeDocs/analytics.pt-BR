---
description: Usar o inventário Analytics
title: Inventário do Analytics
feature: Admin Tools
role: Admin
hide: true
hidefromtoc: true
exl-id: 9fc985c8-93d7-4838-9342-72a6268ef96f
source-git-commit: 1e52aecdbb26dce0875b2df685ed2fa860eaba85
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 9%

---

# Inventário do Analytics {#analytics-inventory}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory"
>title="Inventário do Analytics"
>abstract="Esta página fornece uma visão geral abrangente das Adobe Analytics ambiente, incluindo o número de projetos e componentes, conjuntos de relatórios, usuários e muito mais. Essas informações são especialmente valiosas à medida que você inicia os preparativos para atualizar para o Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

O Inventário do Analytics fornece uma visão geral abrangente do seu ambiente do Adobe Analytics, incluindo o número de projetos e componentes, conjuntos de relatórios, usuários e muito mais. Essas informações são especialmente valiosas quando você inicia os preparativos para atualizar para o Customer Journey Analytics.

O objetivo deste aplicativo é ajudá-lo a responder às seguintes perguntas:

* Para sua organização, quais ativos (como conjuntos de relatórios, segmentos, usuários, projetos do espaço de trabalho, feeds de dados e assim por diante) você precisa atualizar e quais ativos pode deixar para trás?

* Depois de determinar qual ativo precisa ser migrado:

   * Você deve realizar alguma limpeza de ativos antes desta atualização?

   * Você deve fazer alguma consolidação de ativos como parte do processo?

   * Qual deve ser a sequência de atualização para seus ativos?

   * Qual grupo de conjuntos de relatórios você deve atualizar primeiro? último?

## Permissões

O Inventário do Analytics está disponível para usuários com privilégios de Administrador de produto do Adobe Analytics no [Adobe Admin Console](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-console/admin-roles-in-analytics).

## Acesso Analytics inventário

1. Clique **[!UICONTROL Analytics Inventário]** no **[!UICONTROL menu Admin]** . Ou vá para **[!UICONTROL Todos os administrador]** > **[!UICONTROL Analytics Inventário]**.

![Analytics-Menu de inventário](assets/an-inventory-menu.png)

1. A tela principal mostra uma inventário abrangente das Adobe Analytics ambiente:

   ![Tela principal do inventário](assets/an_inventory.png)

   Especificamente, essa tela é exibida

   * O número total de projetos do Analysis Workspace e Publicação de conteúdo para dispositivos móveis do Scorecard que estão ativos nessa organização em todos os usuários.
   * O número total de segmentos e métricas calculadas que estão ativas nessa organização por todos os usuários.
   * O número total de conjuntos de relatórios base que foram definidos (os conjuntos de relatórios virtuais não estão incluídos).
   * Se o recurso Mídia Analytics estiver ativo e, nesse caso, em qual modo.
   * O número total de usuários definidos nessa organização.


## Componentes {#components}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-components"
>title="Componentes"
>abstract="Esta seção mostra o número de projetos, segmentos e métricas calculadas existentes no seu ambiente do Adobe Analytics. Projetos e componentes podem ser migrados para o Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

Nesta versão inicial, você pode ver números resumidos do inventário para projetos, segmentos e métricas calculadas do Workspace. As versões subsequentes permitirão analisar esses componentes.

## Configuração e coleção de dados {#data-config}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-data-config"
>title="Configuração e coleção de dados"
>abstract="Esta seção mostra o número de conjuntos de relatórios no ambiente do Adobe Analytics, bem como seu acesso à mídia de streaming. "

<!-- markdownlint-enable MD034 -->

### Conjuntos de relatórios

A exibição de conjuntos de relatórios mostra todos os conjuntos de relatórios definidos em uma organização. Ele permite responder às seguintes perguntas:

* Quais conjuntos de relatórios receberam mais hit nos últimos 90 dias?
* Quais conjuntos de relatórios não receberam hit nos últimos 90 dias?
* Quais conjuntos de relatórios têm o maior número de dimensão definidos?
* Quais conjuntos de relatórios têm o maior número de métricas definido?

As respostas dessas perguntas fornecerão uma boa ideia sobre quais conjuntos de relatórios são os melhores candidatos para a migração.

1. Para analisar conjuntos de relatórios, navegue até a **[!UICONTROL configuração de Dados e coleção]** > **[!UICONTROL conjuntos de relatórios]** e clique **[!UICONTROL em Analisar]**.

   ![Lista de conjuntos de relatórios](assets/an_inv_rs.png)

   | Elemento | Descrição |
   | --- | --- |
   | Nome | O nome do conjunto de relatórios |
   | ID | A ID do conjunto de relatórios (rsid). Especifica uma ID única que pode conter somente caracteres alfanuméricos. Essa ID não pode ser alterada depois de criada. A Adobe define o prefixo da ID necessário e ele não pode ser alterado. |
   | Ocorrências (últimos 90 dias) | Quantas ocorrências esse conjunto de relatórios recebeu nos últimos 90 dias? |
   | Métricas | Quantas métricas são definidas nesta conjunto de relatórios? |
   | Dimensões | Quantas dimensões são definidas nesta conjunto de relatórios? |
   | Analytics for Target (A4T) habilitado | Essa conjunto de relatórios está ativada para [Analytics para Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t)? |
   | Canais de marketing habilitados | Essa conjunto de relatórios está ativada para [os Canais de marketing](https://experienceleague.adobe.com/en/docs/analytics/components/marketing-channels/c-getting-started-mchannel)? |
   | Conector Origem habilitado | [No desenvolvimento] Esta conjunto de relatórios está ativada para a [Adobe Analytics Conector Origem para dados](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics) conjunto de relatórios no Adobe Experience Platform? Em outras palavras, isso conjunto de relatórios pode ser migrado para Customer Journey Analytics usando o Conector Analytics Origem? |
   | Tipo de calendário | Para obter mais informações, consulte [Calendários personalizados](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/custom-calendar#) |

1. Observe que...

### Exportar para CSV

1. Para exportar a lista de conjuntos de relatórios para um arquivo .csv, clique em **[!UICONTROL Exportar para CSV]**.

1. O arquivo .csv aparecerá na pasta Downloads.

1. Abra-o e salve-o com um aplicativo de planilha em seu dispositivo.


## Gerenciamento do usuário {#user-management}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-user-management"
>title="Gerenciamento do usuário"
>abstract="Esta seção mostra o número de usuários em seu ambiente do Adobe Analytics."

<!-- markdownlint-enable MD034 -->

O gerenciamento de usuários estará disponível em uma versão posterior do inventário do Analytics.