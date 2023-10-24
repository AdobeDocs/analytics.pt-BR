---
description: Saiba mais sobre como usar o Gerente de atividade de relatórios para diagnosticar e corrigir problemas de capacidade durante o pico dos relatórios.
title: Cancelar solicitações de relatórios no Gerenciador de atividades de relatórios
feature: Admin Tools
source-git-commit: 3c65e50bbfdbb011ef7b08d48a0ac3c87d7666b7
workflow-type: tm+mt
source-wordcount: '1352'
ht-degree: 15%

---

# Cancelar solicitações de relatórios no Gerenciador de atividades de relatórios

A variável [!UICONTROL Gerenciador de atividades de relatórios] O permite que os administradores diagnostiquem e cancelem rapidamente as solicitações de relatórios para corrigir problemas de capacidade durante o pico dos relatórios.

Considere o seguinte ao cancelar solicitações de relatórios:

* Você pode cancelar solicitações específicas, cancelar todas as solicitações de um usuário específico ou cancelar todas as solicitações relacionadas a um projeto específico.

* Ao cancelar solicitações, você também pode optar por restringir solicitações subsequentes por um determinado período.

* Não é possível cancelar uma solicitação se a variável [!UICONTROL **Usuário**] a coluna de uma solicitação é exibida como [!UICONTROL **Não reconhecido**]. Quando isso ocorre, significa que o usuário está em uma empresa de logon na qual você não tem permissões administrativas.

Para obter mais informações sobre o Gerente de atividades de relatórios, incluindo os principais benefícios e requisitos de permissão, consulte [Visão geral do Gerenciador de atividades de relatórios](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md).

## Cancelar solicitações específicas

Você pode cancelar solicitações individuais que estão consumindo uma grande quantidade de capacidade de relatório.

1. No Adobe Analytics, acesse **[!UICONTROL Admin]** > **[!UICONTROL Gerenciador de atividades de relatórios]**.

1. Selecione o conjunto de relatórios no qual você deseja cancelar solicitações de relatórios. <!--double-check this step-->

   Para obter mais informações sobre os dados disponíveis nesta página, consulte [Exibir atividade de relatórios no Gerenciador de atividades de relatórios](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Selecione o [!UICONTROL **Solicitações**] e selecione uma ou mais solicitações.

   <!-- add screenshot -->

1. Selecionar [!UICONTROL **Cancelar solicitações**].

   A variável [!UICONTROL **Cancelar _x_ solicitações de relatório**] é exibida.

1. O campo de mensagem Cancelamento mostra a mensagem que o exibe aos usuários quando as solicitações são canceladas. Uma mensagem padrão é fornecida. Você pode atualizar a mensagem padrão para fornecer detalhes adicionais.

1. (Opcional) Para restringir solicitações futuras em um determinado período:

   1. Ative a opção para [!UICONTROL **Restringir solicitações subsequentes**]

      ![Restringir solicitações subsequentes](assets/restrict-subsequent-requests.png)

   1. Escolha entre as seguintes opções:

      | Opção | Função |
      |---------|----------|
      | [!UICONTROL **Usuário e projeto**] | Usuários(as) associados(as) às solicitações selecionadas serão temporariamente restringidos de executar solicitações de relatórios para os projetos associados. |
      | [!UICONTROL **Usuário**] | Usuários(as) associados(as) às solicitações selecionadas serão temporariamente restringidos(as) de fazer solicitações de relatórios. |
      | [!UICONTROL **Projeto**] | Os projetos associados às solicitações selecionadas ficarão temporariamente fechados a todas as solicitações de relatórios. |
      | [!UICONTROL **Restrito para**] | Escolha por quanto tempo as solicitações serão restritas. Você pode escolher 1 minuto (padrão), 5 minutos, 10 minutos, 15 minutos ou 30 minutos. <!-- double-check this --><p>Não é possível remover uma restrição antecipadamente depois que ela é definida.</p> |

      {style="table-layout:auto"}

1. Selecionar [!UICONTROL **Continuar com o cancelamento**].

   Uma notificação é exibida no Analysis Workspace, informando aos usuários que a solicitação foi cancelada. Para obter mais informações sobre como isso é exibido no Analysis Workspace, consulte [Experiência quando usuários acessam um relatório cancelado](#experience-when-users-access-a-cancelled-report).

## Cancelar solicitações por usuário

Você pode cancelar todas as solicitações associadas a um ou mais usuários.

1. No Adobe Analytics, acesse **[!UICONTROL Admin]** > **[!UICONTROL Gerenciador de atividades de relatórios]**.

1. Selecione o conjunto de relatórios no qual você deseja cancelar solicitações de relatórios. <!--double-check this step-->

   Para obter mais informações sobre os dados disponíveis nesta página, consulte [Exibir atividade de relatórios no Gerenciador de atividades de relatórios](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Selecione o [!UICONTROL **Usuários**] e selecione um ou mais usuários.

   <!-- add screenshot -->

1. Selecionar [!UICONTROL **Cancelar solicitações**].

   A variável [!UICONTROL **Cancelar _x_ solicitações de relatório de x usuários**] é exibida.

1. O campo de mensagem Cancelamento mostra a mensagem que o exibe aos usuários quando as solicitações são canceladas. Uma mensagem padrão é fornecida. Você pode atualizar a mensagem padrão para fornecer detalhes adicionais.

1. (Opcional) Para restringir solicitações futuras em um determinado período:

   1. Ative a opção para [!UICONTROL **Restringir solicitações subsequentes**].

      ![Restringir solicitações subsequentes por usuário](assets/restrict-subsequent-requests-user.png)

   1. Escolha entre as seguintes opções:

      | Opção | Função |
      |---------|----------|
      | [!UICONTROL **Usuário e projeto**] | Usuários(as) selecionados(as) serão temporariamente restringidos(as) de fazer solicitações de relatórios para os projetos associados. |
      | [!UICONTROL **Usuário**] | Usuários(as) selecionados(as) serão temporariamente restringidos(as) de fazer solicitações de relatórios. |
      | [!UICONTROL **Projeto**] | Os projetos associados a usuários(as) selecionados(as) ficarão fechados a quaisquer solicitações de relatórios feitas por um(a) usuário(a). |
      | [!UICONTROL **Restrito para**] | Escolha por quanto tempo as solicitações serão restritas. Você pode escolher 1 minuto (padrão), 5 minutos, 10 minutos, 15 minutos ou 30 minutos. <!--double-check this--> <p>Não é possível remover uma restrição antecipadamente depois que ela é definida.</p> |

      {style="table-layout:auto"}

1. Selecionar [!UICONTROL **Continuar com o cancelamento**].

   Uma notificação é exibida no Analysis Workspace, informando aos usuários que a solicitação foi cancelada. Para obter mais informações sobre como isso é exibido no Analysis Workspace, consulte [Experiência quando usuários acessam um relatório cancelado](#experience-when-users-access-a-cancelled-report).

## Cancelar solicitações por projeto

Você pode cancelar todas as solicitações associadas a um ou mais projetos.

1. No Adobe Analytics, acesse **[!UICONTROL Admin]** > **[!UICONTROL Gerenciador de atividades de relatórios]**.

1. Selecione o conjunto de relatórios no qual você deseja cancelar solicitações de relatórios. <!--double-check this step-->

   Para obter mais informações sobre os dados disponíveis nesta página, consulte [Exibir atividade de relatórios no Gerenciador de atividades de relatórios](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Selecione o [!UICONTROL **Projetos**] e selecione um ou mais projetos.

   <!-- add screenshot -->

1. Selecionar [!UICONTROL **Cancelar solicitações**].

   A variável [!UICONTROL **Cancelar _x_ solicitações de relatório de x projetos**] é exibida.

1. O campo de mensagem Cancelamento mostra a mensagem que o exibe aos usuários quando as solicitações são canceladas. Uma mensagem padrão é fornecida. Você pode atualizar a mensagem padrão para fornecer detalhes adicionais.

1. (Opcional) Para restringir solicitações futuras em um determinado período:

   1. Ative a opção para [!UICONTROL **Restringir solicitações subsequentes**].

      ![Restringir solicitações subsequentes por projeto](assets/restrict-subsequent-requests-project.png)

   1. Escolha entre as seguintes opções:

      | Opção | Função |
      |---------|----------|
      | [!UICONTROL **Usuário e projeto**] | Os projetos selecionados ficarão temporariamente fechados a solicitações de relatórios feitas por usuários(as) associados(as). |
      | [!UICONTROL **Usuário**] | Usuários(as) associados(as) aos projetos selecionados serão restringidos(as) de fazer solicitações de relatórios. |
      | [!UICONTROL **Projeto**] | Os projetos selecionados estarão temporariamente restritos a quaisquer solicitações de relatórios feitas por qualquer usuário do. |
      | [!UICONTROL **Restrito para**] | Escolha por quanto tempo as solicitações serão restritas. Você pode escolher 1 minuto (padrão), 5 minutos, 10 minutos, 15 minutos ou 30 minutos. <!--double-check this--> <p>Não é possível remover uma restrição antecipadamente depois que ela é definida.</p> |

      {style="table-layout:auto"}

1. Selecionar [!UICONTROL **Continuar com o cancelamento**].

   Uma notificação é exibida no Analysis Workspace, informando aos usuários que a solicitação foi cancelada. Para obter mais informações sobre como isso é exibido no Analysis Workspace, consulte [Experiência quando usuários acessam um relatório cancelado](#experience-when-users-access-a-cancelled-report).

## Cancelar solicitações por aplicativo

É possível cancelar todas as solicitações associadas a um ou mais aplicativos. Ao cancelar solicitações associadas a um aplicativo, você pode optar por restringir ainda mais as solicitações associadas a esse aplicativo em um determinado período.

Os aplicativos incluem o seguinte:

* Interface do Analysis Workspace
* Projetos agendados do Espaço de trabalho.
* Report Builder
* Interfaces do construtor: segmento, métricas calculadas, anotações, públicos etc.
* Chamadas de API da API 1.4 ou 2.0
* Alertas inteligentes
* Compartilhar com qualquer pessoa através de links
* Qualquer outro aplicativo que consulte o mecanismo de relatórios do Analytics

Para cancelar solicitações por aplicativo:

1. No Adobe Analytics, acesse **[!UICONTROL Admin]** > **[!UICONTROL Gerenciador de atividades de relatórios]**.

1. Selecione a conexão na qual deseja cancelar solicitações de relatórios. <!--double-check this step-->

   Para obter mais informações sobre os dados disponíveis nesta página, consulte [Exibir atividade de relatórios no Gerenciador de atividades de relatórios](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Selecione o [!UICONTROL **Aplicativos**] e selecione um ou mais aplicativos.

   <!-- add screenshot -->

1. Selecionar [!UICONTROL **Cancelar solicitações**].

   A variável [!UICONTROL **Cancelar _x_ solicitações de relatório de x projetos**] é exibida.

1. O campo de mensagem Cancelamento mostra a mensagem que o exibe aos usuários quando as solicitações são canceladas. Uma mensagem padrão é fornecida. Você pode atualizar a mensagem padrão para fornecer detalhes adicionais.

1. (Opcional) Para restringir solicitações futuras em um determinado período:

   1. Ative a opção para [!UICONTROL **Restringir solicitações subsequentes**]

      ![Restringir solicitações subsequentes por aplicativo](assets/restrict-subsequent-requests-application.png)

   1. Escolha entre as seguintes opções:

      | Opção | Função |
      |---------|----------|
      | [!UICONTROL **Usuário e projeto**] | Os aplicativos selecionados serão temporariamente impedidos de qualquer solicitação de relatório feita pelos usuários e projetos associados.<p>Essa é a opção menos restritiva.</p> |
      | [!UICONTROL **Usuário**] | Os usuários associados aos aplicativos selecionados não poderão fazer solicitações de relatórios. |
      | [!UICONTROL **Projeto**] | Os projetos associados aos aplicativos selecionados serão restritos a qualquer solicitação de relatório feita por qualquer usuário. |
      | [!UICONTROL **Restrito para**] | Escolha por quanto tempo as solicitações serão restritas. Você pode escolher 1 minuto (padrão), 5 minutos, 10 minutos, 15 minutos ou 30 minutos. <!--double-check this--> <p>Não é possível remover uma restrição antecipadamente depois que ela é definida.</p> |

      {style="table-layout:auto"}

1. Selecionar [!UICONTROL **Continuar com o cancelamento**].

   Uma notificação é exibida no aplicativo (como no Analysis Workspace), informando aos usuários que a solicitação foi cancelada. Para obter mais informações sobre como isso é exibido no Analysis Workspace, consulte [Experiência quando usuários acessam um relatório cancelado](#experience-when-users-access-a-cancelled-report).

## Experiência quando usuários acessam um relatório cancelado

No Analysis Workspace, os usuários veem as seguintes mensagens ao tentar acessar um relatório ou uma visualização afetada por um cancelamento:

### Mensagem no projeto

Quando os usuários tentam acessar um projeto afetado por um cancelamento, eles veem uma mensagem informando que o relatório está temporariamente restrito:

![Mensagem de cancelamento do projeto](assets/workspace-canceled-report.png)

### Mensagem na visualização

Quando os usuários tentam acessar uma visualização afetada por um cancelamento, eles veem uma mensagem informando que o processamento de dados para o relatório está temporariamente restrito:

![Mensagem de cancelamento da visualização](assets/workspace-cancelled-visualization.png)