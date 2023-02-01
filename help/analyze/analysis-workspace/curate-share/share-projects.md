---
description: Compartilhamento de projetos e funções de projeto no Espaço de trabalho
keywords: Compartilhamento no Analysis Workspace
title: Compartilhar projetos
feature: Curate and Share
role: User, Admin
exl-id: da106eb1-7f5c-469a-a8aa-8497fc3706dc
source-git-commit: 4b11a7057177bec9d2e9d7c435ad0d5476a46602
workflow-type: tm+mt
source-wordcount: '1631'
ht-degree: 34%

---

# Compartilhar projetos

Você pode compartilhar um projeto do Analysis Workspace com os seguintes tipos de pessoas:

* Usuários e grupos da sua organização que têm acesso ao Adobe Analytics

* Usuários e grupos da organização que não têm acesso ao Adobe Analytics

* Pessoas fora da sua organização

Qualquer [preparação](curate.md) aplicar antes do compartilhamento é refletido quando os recipients abrem o projeto.

Veja um vídeo com uma visão geral do compartilhamento de projetos:

>[!VIDEO](https://video.tv.adobe.com/v/36207/?quality=12)


## Compartilhar com usuários e grupos da Adobe Analytics em sua organização {#Add}

Você pode compartilhar um projeto com usuários ou grupos existentes da Adobe Analytics em sua organização. Ao compartilhar um projeto conforme descrito nesta seção, os usuários com os quais você compartilha já devem ter uma conta do Adobe Analytics.

Você pode compartilhar uma função específica com usuários ou grupos, ou pode compartilhar um link.

* [Compartilhar uma função de projeto específica](#share-a-specific-project-role)

* [Compartilhar um link em um projeto](#share-a-link-to-a-project)

### Compartilhar uma função de projeto específica

Ao compartilhar uma função de projeto específica com usuários e grupos em sua organização, considere o seguinte:

* Funções do projeto (**[!UICONTROL Pode editar]**, **[!UICONTROL Pode duplicar]** e **[!UICONTROL Pode visualizar]**) são vinculadas ao usuário e à ID de projeto específica. As funções do projeto são independentes das permissões de usuário gerenciadas no [Admin Console da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=pt-BR).

* No Adobe Analytics, os grupos são definidos por perfis de produtos no [Admin Console da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=pt-BR). Os administradores podem compartilhar com qualquer grupo, incluindo &quot;Todos&quot;. Os não administradores podem compartilhar com qualquer grupo do qual sejam membros, com exceção de &quot;Todos&quot;.

* Um usuário que é colocado em várias funções sempre obtém a maior experiência. Isso pode ocorrer se um usuário for adicionado como um indivíduo e como parte de um grupo. Por exemplo, se um usuário receber a variável **[!UICONTROL Pode editar]** como um indivíduo e **[!UICONTROL Pode visualizar]** como membro de um grupo, eles receberão uma **[!UICONTROL Pode editar]** experiência do projeto.

* Administradores colocados na **[!UICONTROL Pode duplicar]** ou **[!UICONTROL Pode visualizar]** recebem essas experiências limitadas quando abrem um projeto. Se desejar, um Administrador pode aumentar sua função para **[!UICONTROL Pode editar]** a qualquer momento por meio de **[!UICONTROL Componentes] > [!UICONTROL Projetos]**.

Para compartilhar uma função de projeto específica com usuários ou grupos na organização:

1. Vá para o projeto que deseja compartilhar e clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar projeto]**. <!-- recommned changing "Share project" to "Share project internally" or something like that -->
Se houver alterações não salvas, você será solicitado a salvar o projeto primeiro.

   ![](assets/share-proj-modal.png)

   Para obter informações sobre como compartilhar vários projetos simultaneamente, consulte [Compartilhar projetos no Gerenciador de projetos](#share-projects-in-the-project-manager).

1. Adicione recipients ou grupos de recipients em um dos campos de função fornecidos:

   **Pode editar:** Os recipients podem **[!UICONTROL Salvar]** Alterações a um projeto e funções de coproprietários. Esta função é útil se você quiser cogerenciar um projeto com outros colegas; isso inclui edição, exclusão e modificação de listas de recipients para um projeto compartilhado. <br>Observação: no momento, o Analysis Workspace não oferece suporte à colaboração ao vivo, portanto, recomenda-se que somente um usuário edite um projeto em um determinado momento. Se os projetos forem salvos ao mesmo tempo, a última versão será mantida.

   **Pode duplicar:** Os recipients podem **[!UICONTROL Salvar como]** e ter acesso ao painel esquerdo. As interações entre projetos não são limitadas nesta função. Essa função é útil se você quiser compartilhar um projeto com usuários que entendem os dados de sua organização e como usar o Analysis Workspace, mas não deseja alterar seu projeto.

   **Pode visualizar:** Os recipients não podem **[!UICONTROL Salvar]** ou **[!UICONTROL Salvar como]** e não têm acesso ao painel esquerdo. As interações do projeto também são limitadas. Essa função é útil se você quiser compartilhar um projeto com usuários menos familiarizados com a estrutura de dados de sua organização, o Analysis Workspace ou o Adobe Analytics em geral. No entanto, você ainda deseja que eles consumam dados e insights em um ambiente seguro. Saiba mais sobre a [experiência de projeto Pode visualizar](/help/analyze/analysis-workspace/curate-share/view-only-projects.md).

1. Escolha se deseja ativar as seguintes opções ao compartilhar o projeto:

   * **Compartilhar componentes de projeto incorporados:** Compartilha segmentos, métricas calculadas e intervalos de datas com todos os destinatários. Após compartilhados, esses componentes aparecem no menu suspenso de componentes do Espaço de trabalho do recipient. Essa configuração não persiste - é uma ação única no momento do compartilhamento.

   * **Definir como página de aterrissagem para destinatários:** Define esta página como página inicial para destinatários. Essa configuração não persiste - é uma ação única no momento do compartilhamento.

1. Clique em **[!UICONTROL Compartilhar]**.
Você também pode clicar em **[!UICONTROL Preparar e compartilhar]** para aplicar automaticamente a preparação do projeto. Se um projeto já tiver sido compartilhado, esses botões dirão **[!UICONTROL Atualizar]** e **[!UICONTROL Preparar e atualizar]**. Saiba mais sobre [Preparação de projeto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=pt-BR).

### Compartilhar um link em um projeto

Ao compartilhar um link conforme descrito nesta seção, considere o seguinte:

* Os recipients que usam o link precisam fazer logon no Adobe Analytics antes de obter acesso ao projeto.

* Se um recipient não tiver uma função atribuída e receber uma [link](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=pt-BR) ao projeto (**[!UICONTROL Compartilhar] > [!UICONTROL Obter link do projeto]**), elas recebem uma função por padrão. Os administradores recebem a função **[!UICONTROL Pode editar]** e os não administradores recebem a função **[!UICONTROL Pode duplicar]**.

Para compartilhar o link do projeto com os usuários em sua organização:

1. Clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar projeto]**. <!-- recommned changing "Share project" to "Share project internally" or something like that -->
Se houver alterações não salvas, você será solicitado a salvar o projeto primeiro.

   ![](assets/share-proj-modal.png)

1. Clique em **[!UICONTROL Copiar link]** ao lado do **[!UICONTROL Campo Compartilhar URL]**.

1. Compartilhe o link com usuários em sua organização. Por exemplo, você pode colá-lo em um email, em um site interno e assim por diante.

## Compartilhar um link público com qualquer pessoa (não é necessário fazer logon) {#share-public-link}

{{release-limited-testing-section}}

Você pode compartilhar projetos do Analysis Workspace com pessoas que não têm acesso ao Adobe Analytics. Isso pode incluir:

* Pessoas fora da sua organização

* Pessoas em sua organização que não estão provisionadas com o Adobe Analytics

>[!NOTE]
>
>Essa opção pode ser desativada pelo administrador do Analytics, conforme descrito em [Preferências](/help/analyze/analysis-workspace/user-preferences.md). Se você não puder compartilhar um link público conforme descrito nesta seção, o administrador do Analytics desabilitou essa capacidade.

Para compartilhar um link público em um projeto do Analysis Workspace:

1. Abra o projeto do Analysis Workspace que deseja compartilhar.

1. Clique em **[!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar link público]**.

   Se houver alterações não salvas, você será solicitado a salvar o projeto.

   <!-- Add screen shot of new modal -->

1. Ative o **[!UICONTROL Link ativo]** se ainda não estiver ativada.

1. Escolha se deseja ativar as seguintes opções de segurança (essas opções podem ser controladas pelo administrador do Analytics):

   * **[!UICONTROL Exigir autenticação de logon único (SSO)]:**

      Exigir que as pessoas com o link sejam autenticadas via SSO antes de obter acesso ao projeto compartilhado. Selecione essa opção se desejar que o projeto seja acessível somente para usuários em sua organização.

      Os administradores do Analytics podem definir essa preferência para a empresa, conforme descrito em [Preferências](/help/analyze/analysis-workspace/user-preferences.md). Você pode encontrar os seguintes cenários, dependendo de como o administrador configurou essa opção:

      * Se essa opção não estiver visível, o SSO não está habilitado para sua organização ou o administrador do Analytics não habilitou esse recurso.

      * Se essa opção estiver ativada e esmaecida, o administrador do Analytics exigirá autenticação SSO para acessar todos os links públicos.
   * **[!UICONTROL Exigir senha]:** Exigir que as pessoas com o link especifiquem uma senha antes de acessar o projeto do Analysis Workspace. Isso oferece um nível adicional de segurança para o seu projeto.

      Se você selecionar essa opção, especifique uma senha. Lembre-se de compartilhar essa senha junto com o link do projeto quando compartilhá-la com outras pessoas. <!--go through this workflow and see how it works.-->

      Se essa opção estiver ativada e esmaecida, o administrador do Analytics exigirá que todos os links públicos sejam protegidos por senha. Os administradores do Analytics podem definir essa preferência para a empresa, conforme descrito em [Preferências](/help/analyze/analysis-workspace/user-preferences.md).


1. Ao lado do **[!UICONTROL Compartilhar com qualquer pessoa (sem logon necessário)]** clique no campo **Copiar link** ícone para copiar o link para a área de transferência do sistema.

1. Compartilhe o link com as pessoas que deseja que tenham acesso ao projeto. Por exemplo, você pode colar o link em um email.

   Qualquer pessoa com a qual você compartilha o link pode exibir o projeto do Analysis Workspace. Se você optar por exigir uma senha, também deverá compartilhá-la com qualquer pessoa com a qual deseja acessar o link.

1. Selecionar **[!UICONTROL Fechar]** para fechar a caixa de diálogo compartilhar. Suas alterações são salvas automaticamente. <!-- True? -->


## Compartilhar projetos no Gerenciador de projetos {#Manager}

Os projetos também podem ser compartilhados em **[!UICONTROL Componentes] > [!UICONTROL Projetos]**. Um único projeto pode ser compartilhado seguindo as mesmas etapas acima.  Se vários projetos forem selecionados para compartilhamento, os recipients serão adicionados à lista existente de recipients para cada projeto.

Por exemplo:

* O projeto A é compartilhado com os recipients 1, 2, 3
* O projeto B é compartilhado com os recipients 4, 5, 6

Com os projetos A e B selecionados, os recipients 4 e 7 são adicionados às listas de compartilhamento. A nova lista de compartilhamento para cada projeto agora é:

* Projeto A: 1, 2, 3, 4, 7
* Projeto B: 4, 5, 6, 7

![](assets/mult-proj-sharing.png)

## Compartilhar componentes integrados

Veja um vídeo sobre este tópico:

>[!VIDEO](https://video.tv.adobe.com/v/24713/?quality=12)

## Perguntas frequentes {#FAQs}

| Pergunta | Resposta |
| --- | --- |
| O que acontece se dois editores salvam um projeto ao mesmo tempo? | As alterações não são mescladas e a última versão do projeto salva será mantida. Atualmente, o Analysis Workspace não oferece suporte à colaboração em tempo real. |
| Como administrador, que experiência de projeto verei? | Os administradores colocados em uma função **[!UICONTROL Pode duplicar]** ou **[!UICONTROL Pode visualizar]** receberão essas experiências limitadas quando abrirem um projeto. Se desejar, um Administrador pode aumentar sua função para **[!UICONTROL Pode editar]** a qualquer momento por meio de **[!UICONTROL Componentes] > [!UICONTROL Projetos]**. |
| O que acontece se um recipient é colocado em uma função como indivíduo e outra como membro de um grupo? | Se um recipient for colocado em várias funções, ele sempre receberá a experiência mais alta. Por exemplo, se um recipient receber a função **[!UICONTROL Pode editar]** como um indivíduo e a função **[!UICONTROL Pode visualizar]** como membro de um grupo, ele receberá uma experiência de projeto **[!UICONTROL Pode editar]**. |
| Que experiência um recipient obtém se abrir um link de projeto? | Os recipients recebem a função que você os colocou no modal de compartilhamento. Se uma função não for atribuída a um recipient e ele receber um link para o projeto (**[!UICONTROL Compartilhar] > [!UICONTROL Obter link do projeto]**), ele será colocado em uma função por padrão. Os administradores recebem a função **[!UICONTROL Pode editar]** e os não administradores recebem a função **[!UICONTROL Pode duplicar]**. |
