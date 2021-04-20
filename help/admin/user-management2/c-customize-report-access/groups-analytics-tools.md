---
description: Habilite permissões do usuário para obter integração a itens Gerais (faturas, logs etc.), Gerenciamento da empresa, Ferramentas, Acesso a serviços da Web, Report Builder e Data Connectors.
keywords: groups;permissions
subtopic: Users and groups
title: Personalizar permissões de ferramentas do Analytics
feature: Admin Tools
uuid: 8e86bc17-46d3-4c5e-ac25-9f3bfc29b8fa
exl-id: fe3a9f65-f121-438f-91d0-45cfaea94416
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 100%

---

# Personalizar permissões de ferramentas do Analytics

>[!IMPORTANT]
>
>O gerenciamento de usuários e produtos foi movido para o [Admin Console](https://helpx.adobe.com/br/enterprise/using/admin-console.html). A Adobe enviará uma notificação quando for a sua vez de migrar os usuários. Depois que todos os clientes tiverem migrado, o conteúdo da ajuda em **[!UICONTROL Analytics]** > **[!UICONTROL Administração]** > **[!UICONTROL Gerenciamento de usuários]** será removido.

Habilite permissões do usuário para obter integração a itens Gerais (faturas, logs etc.), Gerenciamento da empresa, Ferramentas, Acesso a serviços da Web, Report Builder e Data Connectors.

**[!UICONTROL Gerenciamento de usuários]** > **[!UICONTROL Grupos]** > **[!UICONTROL Acesso a todos os relatórios]** > **[!UICONTROL Ferramentas do Analytics]** > **[!UICONTROL Personalizar]**

>[!NOTE]
>
>A versão lançada no último trimestre de 2016 (20 de outubro) trouxe mudanças para o gerenciamento de grupos. Consulte [Mudanças administrativas - Último trimestre de 2016](/help/admin/user-management2/c-user-management/permissions-changes.md) para ver um resumo das mudanças.

## Acesso ao Relatório - Ferramentas do Analytics

![](assets/report-access-analytics-tools.png)

Clique em **[!UICONTROL Personalizar]** para selecionar itens aos quais este grupo terá acesso.

## Descrições de campo

As configurações desta página pertencem aos conjuntos de relatórios selecionados na página [!UICONTROL Definir grupos de usuários].

| Elemento | Descrição |
|--- |--- |
| **Geral** |  |
| [Gerenciador de código](/help/admin/admin/code-manager-admin.md) | Ativa a permissão para download do código da coleção de dados para plataformas móveis e da Web. |
| Gerenciador de código - Serviços da Web | Permite que um usuário não administrativo acesse o Gerenciador de código por meio dos Serviços da Web. |
| [Logs](/help/admin/admin/logs.md) | Ativa a permissão para arquivos de log, que ajudam a identificar quando um usuário faz logon, sua atividade, seu acesso, conjuntos de dados e alterações de Administração. |
| Logs - Serviços da Web | Permite que um usuário não administrativo acesse os logs das Ferramentas administrativas por meio dos Serviços da Web. |
| [Gerenciamento de tráfego](/help/admin/c-traffic-management/traffic-management.md) | A página Gerenciamento de tráfego permite especificar as alterações no volume de tráfego esperado. |
| Gerenciamento de permissões | Concede a usuários não administrativos acesso às páginas de Gerenciamento de usuários nas Ferramentas administrativas. Esses usuários têm permissão de Leitura, mas não de Gravação. |
| Permissões (Gravação) - Serviços da Web | Concede aos usuários não-administrativos configurações de permissão de leitura e gravação em Gerenciamento de usuários nos Serviços da Web.<br>Essa configuração se refere especificamente às ações de permissões indicadas na API de Administração. |
| Permissões (Leitura) - Serviços da Web | Permite que usuários não administrativos exibam configurações das permissões no Gerenciamento de usuários nos Serviços da Web.<br>Essa configuração se refere especificamente às ações de permissões indicadas na API de Administração. |
| **Gerenciamento da Empresa** |  |
| [Segurança](/help/admin/company/security-manager.md) | Concede permissão para que a página Gerenciador de segurança controle o acesso a dados dos relatórios. As opções incluem senhas fortes, expiração de senha, restrições de logon de IP e restrições de domínio de email. |
| Informações de suporte | Concede permissão para as Informações de suporte em Configurações da empresa. |
| [Serviços Web](/help/admin/company/web-services-admin.md) | Permite o acesso à página Serviços da Web na interface das Ferramentas Administrativas ([!UICONTROL Configurações da empresa] > [!UICONTROL Serviços da Web]).<br>A API de Serviços da Web fornece acesso programático a serviços do Adobe Analytics que permitem duplicar e aumentar a funcionalidade disponível por meio da interface do usuário. |
| Logon único (Herdado) | Concede acesso à página de logon único nas Ferramentas administrativas.<br>**Observação:** o Logon único na Adobe Experience Cloud é implementado com o uso da [vinculação de contas](https://docs.adobe.com/content/help/pt-BR/core-services/interface/manage-users-and-products/organizations.html) entre a Experience Cloud e as demais soluções. |
| [Ações pendentes](/help/admin/company/pending-actions-admin.md) | Concede permissão para o gerenciamento de ações pendentes em [!UICONTROL Configurações da empresa]. |
| [Compartilhamento de marcas](/help/admin/company/co-branding-admin.md) | Concede permissão para o compartilhamento de marcas no Analytics. |
| [Preferências](/help/admin/admin/preferences-manager.md) | Concede permissão para o [!UICONTROL Gerenciador de preferências]. |
| [Ocultar conjuntos de relatórios](/help/admin/company/c-hide-report-suites.md) | Concede permissão para ocultar conjuntos de relatórios na interface do usuário do Adobe Analytics. |
| **Ferramentas** | Essas configurações concedem acesso a ferramentas do Analytics (interfaces e aplicativos) e a recursos avançados, como segmentação e métricas calculadas. |
| [Dados atuais](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/reports-analytics/current-data.html) | Concede permissão para uso do recurso Dados atuais nos relatórios. |
| Acesso aos serviços da Web | Permite o acesso aos Serviços da Web para usuários não administradores. Gera credenciais de Serviços da Web. |
| [Report Builder](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/report-builder/report-builder-setup/t-install-arb.html) | Concede aos membros deste grupo acesso a licenças do [!UICONTROL Report Builder]. |
| Acesso à [Analysis Workspace](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html) | Concede aos usuários acesso à Analysis Workspace, a interface de relatórios recomendada para o [!DNL Adobe Analytics]. |
| [Reports &amp; Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/landing/an-key-concepts.html) | Concede aos usuários acesso ao Reports &amp; Analytics. |
| [Criação de métricas calculadas](https://docs.adobe.com/content/help/pt-BR/analytics/components/calculated-metrics/cm-overview.html) | Concede aos usuários permissão para criar métricas calculadas. |
| [Criação de segmentos](https://docs.adobe.com/content/help/pt-BR/analytics/components/segmentation/seg-home.html) | Concede aos usuários permissão para criar segmentos. |
| **Data Connectors** |  |
| Integrações (Criar, Atualizar ou Excluir) | Concede permissão para criar, atualizar e excluir integrações do Conector de dados. |
