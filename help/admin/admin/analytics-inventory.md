---
description: Usar o inventário do Analytics
title: Inventário do Analytics
feature: Admin Tools
role: Admin
hide: true
hidefromtoc: true
exl-id: 9fc985c8-93d7-4838-9342-72a6268ef96f
source-git-commit: fceb28b7af480e6d87abf09c26f45a7afb2d3270
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 13%

---

# Inventário do Analytics {#analytics-inventory}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory"
>title="Inventário do Analytics"
>abstract="Esta página fornece uma visão geral abrangente do seu ambiente do Adobe Analytics, incluindo o número de projetos e componentes, conjuntos de relatórios, usuários e muito mais. Essas informações são especialmente valiosas quando você inicia os preparativos para atualizar para o Customer Journey Analytics."

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

## Acessar inventário do Analytics

1. Clique em **[!UICONTROL Inventário do Analytics]** no menu **[!UICONTROL Admin]**. Ou vá para **[!UICONTROL Todos os administradores]** > **[!UICONTROL Inventário do Analytics]**.

![Menu-inventário-do-Analytics](assets/an-inventory-menu.png)

1. A tela principal mostra um inventário abrangente do seu ambiente do Adobe Analytics:

   ![Tela principal do inventário](assets/an_inventory.png)

>[!IMPORTANT]
>
>   Nesta versão inicial, você pode ver números de resumo para projetos da Workspace, segmentos, métricas calculadas, dados avançados (Media Analytics) e usuários. Atualmente, os únicos itens acionáveis são Conjuntos de relatórios.


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

### Analisar conjuntos de relatórios

1. Para analisar os conjuntos de relatórios e decidir quais serão migrados, navegue até **[!UICONTROL Configuração e coleção de dados]** > **[!UICONTROL Conjuntos de relatórios]** e clique em **[!UICONTROL Analisar]**.

   ![Lista de conjuntos de relatórios](assets/an_inv_rs.png)

   | Elemento | Descrição |
   | --- | --- |
   | Nome | O nome do conjunto de relatórios |
   | ID | A ID do conjunto de relatórios (rsid). Especifica uma ID única que pode conter somente caracteres alfanuméricos. Essa ID não pode ser alterada depois de criada. A Adobe define o prefixo da ID necessário e ele não pode ser alterado. |
   | Ocorrências (últimos 90 dias) |  |
   | Métricas | How |
   | Dimensões |  |
   | Analytics for Target (A4T) habilitado |  |
   | Canais de marketing habilitados |  |
   | Conector Source habilitado | Para seguir |
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