---
description: Usar o inventário do Analytics
title: Inventário do Analytics
feature: Admin Tools
role: Admin
hide: true
hidefromtoc: true
exl-id: 9fc985c8-93d7-4838-9342-72a6268ef96f
source-git-commit: ba96acbae989b653e4e63f2266511abed6b25b62
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 8%

---

# Inventário do Analytics {#analytics-inventory}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory"
>title="Inventário do Analytics"
>abstract="Esta página fornece uma visão geral abrangente do seu ambiente do Adobe Analytics, incluindo o número de projetos e componentes, conjuntos de relatórios, usuários e muito mais. Essas informações são especialmente valiosas quando você inicia os preparativos para atualizar para o Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

O Inventário do Analytics fornece uma visão geral abrangente do seu ambiente do Adobe Analytics, incluindo o número de projetos e componentes, conjuntos de relatórios, usuários e muito mais. Essas informações são especialmente valiosas quando você inicia os preparativos para atualizar para o Customer Journey Analytics.

O objetivo do inventário do Analytics é ajudá-lo a responder às seguintes perguntas:

* Para sua organização, quais ativos (como conjuntos de relatórios, segmentos, usuários, projetos do Workspace e assim por diante) você precisa migrar e quais ativos pode deixar para trás?

* Depois de determinar qual ativo precisa ser migrado:

   * Você deve realizar alguma limpeza de ativos antes desta atualização?

   * Você deve fazer alguma consolidação de ativos como parte do processo?

   * Qual deve ser a sequência de atualização para seus ativos?

   * Quais conjuntos de relatórios você deve atualizar primeiro ou último?

## Permissões

O Inventário do Analytics está disponível para usuários com privilégios de Administrador de produto do Adobe Analytics no [Adobe Admin Console](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-console/admin-roles-in-analytics).

## Acessar inventário do Analytics

1. Clique em **[!UICONTROL Inventário do Analytics]** no menu **[!UICONTROL Admin]**. Ou vá para **[!UICONTROL Todos os administradores]** > **[!UICONTROL Inventário do Analytics]**.

![Menu-inventário-do-Analytics](assets/an-inventory-menu.png)

1. A tela principal mostra um inventário abrangente do seu ambiente do Adobe Analytics:

   ![Tela principal do inventário](assets/an_inventory.png)

   Especificamente, essa tela mostra:

   * O número total de projetos do Analysis Workspace e do Scorecard para dispositivos móveis ativos nesta organização, em todos os usuários.
   * O número total de segmentos e métricas calculadas que estão ativos nesta organização, em todos os usuários.
   * O número total de conjuntos de relatórios base que foram definidos. Os conjuntos de relatórios virtuais não estão incluídos.
   * Se o recurso do Media Analytics estiver ativo e, nesse caso, em que modo.
   * O número total de usuários definidos nesta organização.


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

* Quais conjuntos de relatórios receberam mais ocorrências nos últimos 90 dias?
* Quais conjuntos de relatórios não receberam visitas nos últimos 90 dias?
* Quais conjuntos de relatórios têm o maior número de dimensões definidas?
* Quais conjuntos de relatórios têm o maior número de métricas definidas?

As respostas dessas perguntas fornecerão uma boa ideia sobre quais conjuntos de relatórios são os melhores candidatos para a migração.

>[!NOTE]
>
>Essa tabela é preenchida lentamente, com um valor de célula por vez.


1. Para analisar conjuntos de relatórios, navegue até **[!UICONTROL Configuração e coleção de dados]** > **[!UICONTROL Conjuntos de relatórios]** e clique em **[!UICONTROL Analisar]**.

   ![Lista de conjuntos de relatórios](assets/an_inv_rs.png)

   | Elemento | Descrição |
   | --- | --- |
   | Nome | O nome do conjunto de relatórios |
   | ID | A ID do conjunto de relatórios (rsid). Especifica uma ID única que pode conter somente caracteres alfanuméricos. Essa ID não pode ser alterada depois de criada. A Adobe define o prefixo da ID necessário e ele não pode ser alterado. |
   | Ocorrências (últimos 90 dias) | A métrica “Ocorrências” exibe o número de ocorrências em que uma determinada dimensão foi definida ou mantida. Quantas ocorrências esse conjunto de relatórios recebeu nos últimos 90 dias? |
   | Métricas | Quantas métricas estão definidas neste conjunto de relatórios? |
   | Dimensões | Quantas dimensões estão definidas neste conjunto de relatórios? |
   | Analytics for Target (A4T) habilitado | [Oculto por padrão] Este conjunto de relatórios está habilitado para o [Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t)? |
   | Canais de marketing habilitados | [Oculto por padrão] Este conjunto de relatórios está habilitado para [Canais de marketing](https://experienceleague.adobe.com/en/docs/analytics/components/marketing-channels/c-getting-started-mchannel)? |
   | Conector Source habilitado | Este conjunto de relatórios está habilitado para o [Adobe Analytics Source Connector para dados do conjunto de relatórios](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics) no Adobe Experience Platform? Em outras palavras, esse conjunto de relatórios pode ser migrado para o Customer Journey Analytics usando o Analytics Source Connector? |
   | Tipo de calendário | [Oculto por padrão] Para obter mais informações, consulte [Calendários Personalizados](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/custom-calendar#) |

#### Analisar dimensões

Essa tela fornece uma exibição detalhada de todas as dimensões definidas para um conjunto de relatórios específico. Nessa visualização, você pode responder às seguintes perguntas:

* Quais dimensões estão ativadas para este conjunto de relatórios?
* Quais são os dez principais itens de dimensão dos últimos 90 dias para esta dimensão?

1. Clique no link **[!UICONTROL Dimensões]** na página Conjunto de relatórios.

   | Elemento | Descrição |
   | --- | --- |
   | Nome | O nome da dimensão |
   | ID | A ID da dimensão. |
   | Tipo | O tipo de dimensão. Os valores possíveis incluem Conversão, Tráfego, Navegação, Fontes de tráfego, Clientes, Data ou dimensões específicas do produto Adobe, como AEM, Público-alvo, Adobe Campaign, Aplicativo móvel etc. |
   | Descrição | Nem todas as dimensões têm descrições. |
   | Conector Source habilitado | Essa dimensão está habilitada para o [Adobe Analytics Source Connector para dados do conjunto de relatórios](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics) no Adobe Experience Platform? Em outras palavras, essa dimensão pode ser migrada para o Customer Journey Analytics usando o Analytics Source Connector? |

1. Determine quais dimensões fazem sentido migrar para o CJA.


#### Analisar métricas

Essa tela fornece uma exibição detalhada de todas as métricas definidas para um conjunto de relatórios específico. Nessa visualização, você pode responder às seguintes perguntas:

* Quais métricas estão ativadas para este conjunto de relatórios?
* Quais são as dez principais métricas dos últimos 90 dias?

1. Clique no link **[!UICONTROL Métricas]** na página Conjunto de relatórios.


   | Elemento | Descrição |
   | --- | --- |
   | Nome | O nome da métrica |
   | ID | A ID da métrica. |
   | Tipo | O tipo de métrica. Os valores possíveis incluem Conversão, Tráfego, Navegação, Fontes de tráfego, Clientes, Data ou dimensões específicas do produto Adobe, como AEM, Público-alvo, Adobe Campaign, Aplicativo móvel etc. |
   | Descrição | Nem todas as dimensões têm descrições. |
   | Conector Source habilitado | Essa métrica está habilitada para o [Adobe Analytics Source Connector para dados do conjunto de relatórios](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics) no Adobe Experience Platform? Em outras palavras, essa métrica pode ser migrada para o Customer Journey Analytics usando o Analytics Source Connector? |

1. Determine quais métricas fazem sentido migrar para o CJA.

#### Exportar para CSV

1. Para exportar a lista de conjuntos de relatórios, dimensões ou métricas para um arquivo .csv, clique em **[!UICONTROL Exportar para CSV]**.

1. O arquivo .csv aparecerá na pasta Downloads.

1. Abra-o e salve-o com um aplicativo de planilha em seu dispositivo.

>[!NOTE]
>
>Os itens e as colunas filtrados não são exportados para o arquivo .csv.


#### Filtrar, pesquisar, ordenar e navegar

* Você pode pesquisar a tabela.
* No painel à esquerda, clique no ícone Filtro para filtrar por &quot;Tipo&quot;. Ou clique em **[!UICONTROL Ocultar Filtro]**.
* Você pode ordenar todas as colunas em ordem crescente/decrescente (ordem de coluna única somente).
* Você pode clicar em itens na navegação estrutural para navegar para outra tela.

## Gerenciamento do usuário {#user-management}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-user-management"
>title="Gerenciamento do usuário"
>abstract="Esta seção mostra o número de usuários em seu ambiente do Adobe Analytics."

<!-- markdownlint-enable MD034 -->

O gerenciamento de usuários estará disponível em uma versão posterior do inventário do Analytics.