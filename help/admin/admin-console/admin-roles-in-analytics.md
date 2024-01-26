---
title: Funções de administrador no Adobe Analytics
description: Saiba como começar a usar o Adobe Analytics, os tipos de função gerais e como fazer logon na interface do usuário.
feature: Admin Tools
exl-id: 9d10716f-5b66-42dc-b288-af34da203c35
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '1122'
ht-degree: 100%

---

# Funções de administrador no Adobe Analytics

O Adobe Analytics é compatível com vários tipos de administradores. Os administradores completos do Adobe Analytics têm acesso a tudo no Adobe Analytics, enquanto outros administradores e usuários podem realizar tarefas mais especializadas.

>[!NOTE]
>
>Antes que qualquer usuário possa receber funções no Adobe Analytics, ele deve ser atribuído como primeiro administrador na Experience Cloud. O primeiro administrador pode, então, provisionar usuários na organização com outras funções principais, conforme descrito neste artigo. Para obter mais informações sobre o primeiro administrador, consulte [Guia do primeiro administrador do Adobe Analytics](/help/admin/admin-console/first-admin-guide.md).


## Principais funções na Experience Cloud e no Adobe Analytics

Considere as seguintes funções principais ao usar o Adobe Analytics:

* **Administradores completos do Adobe Analytics:** esses usuários têm acesso total a tudo no Adobe Analytics, incluindo configurações de conjunto de relatórios e permissões de usuário. Dependendo de como sua organização está estruturada, pessoas ou equipes diferentes podem ser responsáveis por diversos aspectos da administração do Analytics. Por exemplo, uma pessoa é responsável por designar quais variáveis usar em uma implementação. Outra pessoa pode ser responsável por permitir que os usuários extraiam os relatórios corretamente, garantindo que todos tenham as permissões corretas. Identifique pelo menos um usuário que possa ser responsável pelas configurações do conjunto de relatórios e pelas permissões de usuário do Analytics, e que possa convidar outros administradores do Analytics a partir daí.
* **Administradores da coleção de dados:** esses usuários têm acesso total a tudo na Coleção de dados da Adobe Experience Platform, incluindo permissões de publicação, criação de containers e permissões de usuário. Esses usuários não são necessariamente programadores, mas é útil ter pelo menos um conhecimento iniciante de HTML, CSS e JavaScript. Eles são responsáveis por trabalhar com os proprietários de sites de sua organização para que as tags sejam implementadas no site. Identifique pelo menos um usuário responsável pela implementação de sua organização que possa convidar outros administradores de coleção de dados.
* **Administradores do Perfil do produto:** esses usuários podem adicionar ou remover usuários a um perfil de produto, ajustar itens de permissões em seu perfil de produto e atribuir ou remover perfis de produto a grupos de usuários. Os administradores de perfil de produto não têm acesso total ao Adobe Analytics. No entanto, eles são ideais para líderes ou gerentes de equipes que precisam apenas conceder e gerenciar acesso ao Adobe Analytics para sua equipe. Para obter mais informações sobre perfis de produtos, consulte [Perfis de produto para o Adobe Analytics](/help/admin/admin-console/permissions/product-profile.md).
* **Delegados de suporte**: também conhecidos como usuários aceitos, eles não têm privilégios adicionais na interface do Analytics. Em vez disso, recebem privilégios adicionais ao se comunicarem com o Atendimento ao cliente da Adobe. Esses usuários também são quase sempre administradores do Analytics, pois ajudam o Atendimento ao cliente a solucionar problemas com eles. Identifique pelo menos um administrador do Analytics responsável por facilitar as interações entre os usuários finais e o Atendimento ao cliente da Adobe.
* **Proprietários do site:** esses indivíduos ou equipes são responsáveis pela codificação e desenvolvimento do site. Eles não exigem contas, mas querem trabalhar com os administradores de coleção de dados para obter o código da tag e implementá-lo em seu site.
* **Usuários finais:** esses usuários normalmente visualizam relatórios e procuram respostas para perguntas comerciais. Os administradores do Analytics concedem a esses usuários permissões para trabalhar no produto.

## Conceder acesso completo ao administrador do produto para o Analytics

Os administradores de nível de sistema não têm acesso direto aos produtos. No entanto, eles podem dar acesso a si mesmos adicionando-se como um administrador de nível de produto.

Para conceder acesso ao Adobe Analytics a você mesmo ou a outros:

1. Faça logon no [Admin Console](https://adminconsole.adobe.com/) com as credenciais da Adobe ID.
1. Clique na guia **[!UICONTROL Produtos]** na parte superior. Todos os produtos comprados pela sua organização estão à esquerda. Clique em **[!UICONTROL Adobe Analytics]** e depois no botão **[!UICONTROL Novo botão]**.
1. Nomeie esse perfil como “Acesso total de administrador do Analytics” e clique em **[!UICONTROL Próximo]** > **[!UICONTROL Salvar]**.
1. Na página Perfis de produto, clique no perfil recém-criado e depois clique na guia **[!UICONTROL Permissões]**.
1. Clique em um dos itens de linha de permissão. Se a **[!UICONTROL Inclusão automática]** estiver disponível, ative-a. Se a **[!UICONTROL Inclusão automática]** não estiver disponível, clique em **[!UICONTROL Adicionar tudo]**. Ambas as opções movem todos os itens de permissão para a coluna direita.
1. Clique em **[!UICONTROL Salvar]**.
Repita a etapa acima para todas as categorias de permissão.
1. Depois que todas as categorias de permissão forem concedidas ao perfil, volte para a página Produtos clicando em **[!UICONTROL Produto]** na parte superior.
1. Abaixo do bloco do Adobe Analytics, clique em **[!UICONTROL Atribuir usuários]**.
1. Digite o endereço de email ao qual você deseja conceder acesso total ao Analytics e atribua a ele o perfil de acesso completo do administrador recém-criado. Clique em **[!UICONTROL Salvar]**.

O usuário agora tem acesso total ao Adobe Analytics.

## Conceder acesso de administrador de produto para a Coleção de dados na Experience Platform

O acesso de administrador de produto para Coleção de dados na Experience Platform é quase idêntico a conceder acesso de administrador de produto para o Analytics.

1. Faça logon no [Adobe Admin Console](https://adminconsole.adobe.com) com suas credenciais da Adobe ID.
1. Clique na guia **[!UICONTROL Produtos]** na parte superior. Todos os produtos comprados pela sua organização estão à esquerda. Clique em **[!UICONTROL Experience Platform Launch]** e em **[!UICONTROL Novo perfil]**.
1. Nomeie esse perfil como &quot;Acesso completo de administrador à coleção de dados&quot; e clique em **[!UICONTROL Concluído]**.
1. Na página **[!UICONTROL Perfis de produto]**, clique no perfil recém-criado e depois clique na guia **[!UICONTROL Permissões]**.
1. Clique em um dos itens de linha de permissão. Se a **[!UICONTROL Inclusão automática]** estiver disponível, ative-a. Se a Inclusão automática não estiver disponível, clique em **[!UICONTROL Adicionar tudo]**. Ambas as opções movem todos os itens de permissão para a coluna direita.
1. Clique em **[!UICONTROL Salvar]**. Repita a etapa acima para todas as categorias de permissão.
1. Quando todas as categorias de permissão forem concedidas ao perfil, volte para a página Visão geral clicando em **[!UICONTROL Visão geral]** na parte superior.
1. No bloco [!UICONTROL Experience Platform Launch], clique em **[!UICONTROL Atribuir usuários]**.
1. Digite o endereço de email ao qual você deseja conceder acesso total ao Analytics e atribua a ele o perfil de acesso completo do administrador recém-criado. Clique em **[!UICONTROL Salvar]**.
1. O usuário agora tem acesso total à Coleção de dados da Experience Platform.

## Conceder acesso de administrador de produto para perfis de produto

Para obter informações sobre como atribuir usuários como administradores de perfil de produto, consulte a seção “Gerenciar administradores de perfil de produto” no artigo, [Gerenciar perfis de produto para usuários corporativos](https://helpx.adobe.com/br/enterprise/using/manage-product-profiles.html) no guia do usuário Enterprise.

## Próximas etapas

[Criar um conjunto de relatórios](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): faça com que o administrador do Analytics faça logon na ferramenta e crie um conjunto de relatórios para a coleção de dados

[Criar uma propriedade de tag do Analytics](/help/implement/launch/create-analytics-property.md): peça ao administrador da Coleção de dados que faça logon na ferramenta e crie uma propriedade para implementar no site

Antes que qualquer usuário possa receber funções no Adobe Analytics, ele deve ser atribuído como primeiro administrador na Experience Cloud. O primeiro administrador pode, então, provisionar usuários na organização com outras funções principais, conforme descrito neste artigo.

Um primeiro administrador é o ponto de partida para permitir que o restante da organização use cada solução da Experience Cloud.

Após a assinatura de um contrato

1. A equipe de provisionamento da Adobe prepara-se para a criação da conta.

1. O primeiro administrador recebe um email com credenciais de logon antes da data de início do contrato.

>[!IMPORTANT]
>
>   É altamente recomendado garantir que as informações de contato do primeiro administrador sejam precisas e fornecidas à Adobe antes da assinatura do contrato.
