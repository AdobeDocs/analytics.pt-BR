---
description: Saiba mais sobre como usar o Gerenciador de atividades de relatórios para diagnosticar e corrigir problemas de capacidade durante o pico dos relatórios.
title: Cancelar solicitações de relatórios no Gerenciador de atividades de relatórios
feature: Admin Tools
exl-id: 37a2fa8f-7804-4220-a508-ec66996b3801
role: Admin
source-git-commit: 815e50e30fa6a0bce1bf78f33843070f96f52de8
workflow-type: ht
source-wordcount: '1438'
ht-degree: 100%

---

# Cancelar solicitações de relatórios no Gerenciador de atividades de relatórios

O [!UICONTROL Gerenciador de atividades de relatórios] permite que admins diagnostiquem e cancelem rapidamente as solicitações de relatórios para corrigir problemas de capacidade durante o pico de relatórios.

Considere o seguinte ao cancelar solicitações de relatórios:

* É possível cancelar solicitações específicas, todas as solicitações de um usuário específico ou todas as solicitações relacionadas a um projeto específico.

  Ao cancelar uma solicitação, a ação é registrada nos [Logs](/help/admin/admin/logs.md). A coluna [!UICONTROL **Tipo de evento**] é exibida como [!UICONTROL **Ação do admin**] e uma descrição do cancelamento aparece na coluna [!UICONTROL **Evento**].

* Ao cancelar solicitações, também é possível optar por restringir solicitações subsequentes por um determinado período.

  Ao restringir uma solicitação subsequente, a ação é registrada nos [Logs](/help/admin/admin/logs.md). A coluna [!UICONTROL **Tipo de evento**] é exibida como [!UICONTROL **Ação do admin**] e uma descrição da restrição aparece na coluna [!UICONTROL **Evento**].

* Não é possível cancelar uma solicitação se a coluna [!UICONTROL **Usuário**] for exibida como [!UICONTROL **Não reconhecido**]. Isso indica que o usuário está em uma empresa de logon sem permissões administrativas.

Para obter mais informações sobre o Gerenciador de atividades de relatórios, incluindo os principais benefícios e permissões necessárias, consulte [Visão geral do Gerenciador de atividades de relatórios](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md).

## Cancelar solicitações específicas

É possível cancelar solicitações individuais que estão consumindo uma grande quantidade da capacidade de relatório.

1. No Adobe Analytics, acesse **[!UICONTROL Admin]** > **[!UICONTROL Gerenciador de atividades de relatórios]**.

1. Selecione o conjunto de relatórios no qual deseja cancelar as solicitações de relatórios. <!--double-check this step-->

   Para obter mais informações sobre os dados disponíveis nesta página, consulte [Visualizar atividades de relatório no Gerenciador de atividades de relatórios](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Selecione a guia [!UICONTROL **Solicitações**] e escolha uma ou mais solicitações.

   <!-- add screenshot -->

1. Selecione [!UICONTROL **Cancelar solicitações**].

   A caixa de diálogo [!UICONTROL **Cancelar _x_ solicitações de relatório**] é exibida.

1. O campo Mensagem de cancelamento mostra a mensagem que é exibida aos usuários quando suas solicitações são canceladas. Uma mensagem padrão é fornecida. É possível atualizar a mensagem padrão para fornecer detalhes adicionais.

1. (Opcional) Para restringir solicitações futuras por um determinado período:

   1. Habilite a opção [!UICONTROL **Restringir solicitações subsequentes**]

      ![Restringir solicitações subsequentes](assets/restrict-subsequent-requests.png)

   1. Escolha entre as seguintes opções:

      | Opção | Função |
      |---------|----------|
      | [!UICONTROL **Usuário e projeto**] | Usuários associados às solicitações selecionadas serão temporariamente restringidos de executar solicitações de relatórios nos projetos associados. |
      | [!UICONTROL **Usuário**] | Usuários associados às solicitações selecionadas serão temporariamente restringidos de criar solicitações de relatórios. |
      | [!UICONTROL **Projeto**] | Todas as solicitações de relatórios serão restringidas temporariamente nos projetos associados às solicitações selecionadas. |
      | [!UICONTROL **Restringir por**] | Escolha por quanto tempo as solicitações serão restringidas. É possível escolher as opções 1 minuto (padrão), 5 minutos, 10 minutos, 15 minutos ou 30 minutos. <!-- double-check this --><p>Não é possível remover uma restrição antecipadamente após defini-la.</p> |

      {style="table-layout:auto"}

1. Selecione [!UICONTROL **Continuar com o cancelamento**].

   Uma notificação será exibida no Analysis Workspace informando aos usuários que a solicitação foi cancelada. Para obter mais informações sobre como isso é exibido no Analysis Workspace, consulte [Experiência de usuários ao acessar um relatório cancelado](#experience-when-users-access-a-cancelled-report).

## Cancelar solicitações por usuário

É possível cancelar todas as solicitações associadas a um ou mais usuários.

1. No Adobe Analytics, acesse **[!UICONTROL Admin]** > **[!UICONTROL Gerenciador de atividades de relatórios]**.

1. Selecione o conjunto de relatórios no qual deseja cancelar as solicitações de relatórios. <!--double-check this step-->

   Para obter mais informações sobre os dados disponíveis nesta página, consulte [Visualizar atividades de relatório no Gerenciador de atividades de relatórios](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Selecione a guia [!UICONTROL **Usuários**] e escolha um ou mais usuários.

   <!-- add screenshot -->

1. Selecione [!UICONTROL **Cancelar solicitações**].

   A caixa de diálogo [!UICONTROL **Cancelar _x_ solicitações de relatório de x usuários**] é exibida.

1. O campo Mensagem de cancelamento mostra a mensagem que é exibida aos usuários quando suas solicitações são canceladas. Uma mensagem padrão é fornecida. É possível atualizar a mensagem padrão para fornecer detalhes adicionais.

1. (Opcional) Para restringir solicitações futuras por um determinado período:

   1. Habilite a opção [!UICONTROL **Restringir solicitações subsequentes**].

      ![Restringir solicitações subsequentes por usuário](assets/restrict-subsequent-requests-user.png)

   1. Escolha entre as seguintes opções:

      | Opção | Função |
      |---------|----------|
      | [!UICONTROL **Usuário e projeto**] | Usuários selecionados serão temporariamente restringidos de criar solicitações de relatórios nos projetos associados. |
      | [!UICONTROL **Usuário**] | Usuários selecionados serão temporariamente restringidos de criar solicitações de relatórios. |
      | [!UICONTROL **Projeto**] | As solicitações de relatórios serão restringidas nos projetos associados aos usuários selecionados. |
      | [!UICONTROL **Restringir por**] | Escolha por quanto tempo as solicitações serão restringidas. É possível escolher as opções 1 minuto (padrão), 5 minutos, 10 minutos, 15 minutos ou 30 minutos. <!--double-check this--> <p>Não é possível remover uma restrição antecipadamente após defini-la.</p> |

      {style="table-layout:auto"}

1. Selecione [!UICONTROL **Continuar com o cancelamento**].

   Uma notificação será exibida no Analysis Workspace informando aos usuários que a solicitação foi cancelada. Para obter mais informações sobre como isso aparece no Analysis Workspace, consulte [Experiência de usuários ao acessar um relatório cancelado](#experience-when-users-access-a-cancelled-report).

## Cancelar solicitações por projeto

É possível cancelar todas as solicitações associadas a um ou mais projetos.

1. No Adobe Analytics, acesse **[!UICONTROL Admin]** > **[!UICONTROL Gerenciador de atividades de relatórios]**.

1. Selecione o conjunto de relatórios no qual deseja cancelar as solicitações de relatórios. <!--double-check this step-->

   Para obter mais informações sobre os dados disponíveis nesta página, consulte [Visualizar atividades de relatório no Gerenciador de atividades de relatórios](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Selecione a guia [!UICONTROL **Projetos**] e escolha um ou mais projetos.

   <!-- add screenshot -->

1. Selecione [!UICONTROL **Cancelar solicitações**].

   A caixa de diálogo [!UICONTROL **Cancelar _x_ solicitações de relatório de x projetos**] é exibida.

1. O campo Mensagem de cancelamento mostra a mensagem que é exibida aos usuários quando suas solicitações são canceladas. Uma mensagem padrão é fornecida. É possível atualizar a mensagem padrão para fornecer detalhes adicionais.

1. (Opcional) Para restringir solicitações futuras por um determinado período:

   1. Habilite a opção [!UICONTROL **Restringir solicitações subsequentes**].

      ![Restringir solicitações subsequentes por projeto](assets/restrict-subsequent-requests-project.png)

   1. Escolha entre as seguintes opções:

      | Opção | Função |
      |---------|----------|
      | [!UICONTROL **Usuário e projeto**] | A criação de solicitações de relatórios por usuários associados será restringida temporariamente nos projetos selecionados. |
      | [!UICONTROL **Usuário**] | Usuários associados aos projetos selecionados serão restringidos de criar solicitações de relatórios. |
      | [!UICONTROL **Projeto**] | A criação de solicitações de relatórios por usuários será restringida temporariamente nos projetos selecionados. |
      | [!UICONTROL **Restringir por**] | Escolha por quanto tempo as solicitações serão restringidas. É possível escolher as opções 1 minuto (padrão), 5 minutos, 10 minutos, 15 minutos ou 30 minutos. <!--double-check this--> <p>Não é possível remover uma restrição antecipadamente após defini-la.</p> |

      {style="table-layout:auto"}

1. Selecione [!UICONTROL **Continuar com o cancelamento**].

   Uma notificação será exibida no Analysis Workspace informando aos usuários que a solicitação foi cancelada. Para obter mais informações sobre como isso aparece no Analysis Workspace, consulte [Experiência de usuários ao acessar um relatório cancelado](#experience-when-users-access-a-cancelled-report).

## Cancelar solicitações por aplicativo

É possível cancelar todas as solicitações associadas a um ou mais aplicativos. Ao cancelar, é possível optar por restringir ainda mais as solicitações associadas ao aplicativo por um determinado período.

Estes aplicativos incluem:

* Interface do Analysis Workspace
* Projetos agendados do Espaço de trabalho.
* Report Builder
* Interfaces do construtor: segmento, métricas calculadas, anotações, públicos etc.
* Chamadas de API da API 1.4 ou 2.0
* Alertas
* Links para compartilhar com qualquer pessoa
* Qualquer outro aplicativo que consulte o mecanismo de relatórios do Analytics

Para cancelar solicitações por aplicativo:

1. No Adobe Analytics, acesse **[!UICONTROL Admin]** > **[!UICONTROL Gerenciador de atividades de relatórios]**.

1. Selecione a conexão na qual deseja cancelar as solicitações de relatórios. <!--double-check this step-->

   Para obter mais informações sobre os dados disponíveis nesta página, consulte [Visualizar atividades de relatório no Gerenciador de atividades de relatórios](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Selecione a guia [!UICONTROL **Aplicativos**] e escolha um ou mais aplicativos.

   <!-- add screenshot -->

1. Selecione [!UICONTROL **Cancelar solicitações**].

   A caixa de diálogo [!UICONTROL **Cancelar _x_ solicitações de relatório de x projetos**] é exibida.

1. O campo Mensagem de cancelamento mostra a mensagem que é exibida aos usuários quando suas solicitações são canceladas. Uma mensagem padrão é fornecida. É possível atualizar a mensagem padrão para fornecer detalhes adicionais.

1. (Opcional) Para restringir solicitações futuras por um determinado período:

   1. Habilite a opção [!UICONTROL **Restringir solicitações subsequentes**]

      ![Restringir solicitações subsequentes por aplicativo](assets/restrict-subsequent-requests-application.png)

   1. Escolha entre as seguintes opções:

      | Opção | Função |
      |---------|----------|
      | [!UICONTROL **Usuário e projeto**] | A criação de solicitações de relatórios por usuários e projetos associados será restringida temporariamente nos aplicativos selecionados.<p>Esta é a opção menos restritiva.</p> |
      | [!UICONTROL **Usuário**] | Usuários associados aos aplicativos selecionados serão restringidos de criar solicitações de relatórios. |
      | [!UICONTROL **Projeto**] | A criação de solicitações de relatórios por usuários será restringida temporariamente nos projetos associados aos aplicativos selecionados. |
      | [!UICONTROL **Restringir por**] | Escolha por quanto tempo as solicitações serão restringidas. É possível escolher as opções 1 minuto (padrão), 5 minutos, 10 minutos, 15 minutos ou 30 minutos. <!--double-check this--> <p>Não é possível remover uma restrição antecipadamente após defini-la.</p> |

      {style="table-layout:auto"}

1. Selecione [!UICONTROL **Continuar com o cancelamento**].

   Uma notificação aparecerá no aplicativo (como no Analysis Workspace) para informar usuários de que a solicitação foi cancelada. Para obter mais informações sobre como isso aparece no Analysis Workspace, consulte [Experiência de usuários ao acessar um relatório cancelado](#experience-when-users-access-a-cancelled-report).

## Experiência de usuários ao acessar um relatório cancelado

No Analysis Workspace, as seguintes mensagens aparecem ao tentar acessar um relatório ou visualização afetados por um cancelamento:

### Mensagem no projeto

Ao tentar acessar um projeto afetado por um cancelamento, uma mensagem informa que o relatório está temporariamente restrito:

![Mensagem de cancelamento no projeto](assets/workspace-canceled-report.png)

### Mensagem na visualização

Ao tentar acessar uma visualização afetada por um cancelamento, uma mensagem informa que o processamento de dados de relatório está temporariamente restrito:

![Mensagem de cancelamento na visualização](assets/workspace-cancelled-visualization.png)
