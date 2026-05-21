---
description: Saiba mais sobre como usar o Gerenciador de atividades de relatórios para diagnosticar e corrigir problemas de capacidade durante o pico dos relatórios.
title: Cancelar solicitações de relatórios no gerenciador de atividades de relatórios
feature: Admin Tools
exl-id: 37a2fa8f-7804-4220-a508-ec66996b3801
role: Admin
TQID: https://experienceleague.adobe.com/zMNTnhG6SP-SAIWBOAWm-etPHvBOykscB90n4UIgdrA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1438
ht-degree: 100%

---

# Cancelar solicitações de relatórios no gerenciador de atividades de relatórios

O [!UICONTROL Gerenciador de atividades de relatórios] permite que os administradores diagnostiquem e cancelem rapidamente as solicitações de relatórios para corrigir problemas de capacidade de relatórios durante os horários de pico de relatórios.

Considere o seguinte ao cancelar solicitações de relatórios:

* Você pode cancelar solicitações específicas, cancelar todas as solicitações de um usuário específico ou cancelar todas as solicitações relacionadas a um projeto específico.

  Ao cancelar uma solicitação, a ação é registrada nos [Logs](/help/admin/tools/logs.md). A coluna [!UICONTROL **Tipo de evento**] é exibida como [!UICONTROL **Ação do admin**] e uma descrição do cancelamento aparece na coluna [!UICONTROL **Evento**].

* Ao cancelar solicitações, também é possível optar por restringir solicitações subsequentes por um determinado período.

  Ao restringir uma solicitação subsequente, a ação é registrada nos [Logs](/help/admin/tools/logs.md). A coluna [!UICONTROL **Tipo de evento**] é exibida como [!UICONTROL **Ação do admin**] e uma descrição da restrição aparece na coluna [!UICONTROL **Evento**].

* Não será possível cancelar uma solicitação se a coluna [!UICONTROL **Usuário**] de uma solicitação estiver mostrando [!UICONTROL **Não reconhecido**]. Se isso ocorrer, significa que o usuário está em uma empresa de logon na qual você não tem permissões administrativas.

Para mais informações sobre o gerenciador de atividades de relatórios, incluindo os principais benefícios e requisitos de permissão, consulte [Visão geral do gerenciador de atividades de relatórios](/help/admin/tools/reporting-activity-manager/reporting-activity-overview.md).

## Cancelar solicitações específicas

Você pode cancelar solicitações individuais que estão consumindo uma grande quantidade de capacidade de relatórios.

1. No Adobe Analytics, acesse **[!UICONTROL Admin]** > **[!UICONTROL Gerenciador de atividades de relatórios]**.

1. Selecione o conjunto de relatórios no qual deseja cancelar as solicitações de relatórios. <!--double-check this step-->

   Para mais informações sobre os dados disponíveis nesta página, consulte [Exibir atividades de relatórios no gerenciador de atividades de relatórios](/help/admin/tools/reporting-activity-manager/reporting-activity.md).

1. Selecione a guia [!UICONTROL **Solicitações**] e escolha uma ou mais solicitações.

   <!-- add screenshot -->

1. Selecione [!UICONTROL **Cancelar solicitações**].

   A caixa de diálogo [!UICONTROL **Cancelar _x_ solicitações de relatórios**] é exibida.

1. O campo Mensagem de cancelamento mostra a mensagem que é exibida aos usuários quando suas solicitações são canceladas. Uma mensagem padrão é fornecida. É possível atualizar a mensagem padrão para fornecer detalhes adicionais.

1. (Opcional) Para restringir solicitações futuras em um determinado período:

   1. Habilite a opção para [!UICONTROL **Restringir solicitações subsequentes**]

      ![Restringir solicitações subsequentes](assets/restrict-subsequent-requests.png)

   1. Escolha entre as seguintes opções:

      | Opção | Função |
      |---------|----------|
      | [!UICONTROL **Usuário e projeto**] | Usuários(as) associados(as) às solicitações selecionadas serão temporariamente restringidos de executar solicitações de relatórios para os projetos associados. |
      | [!UICONTROL **Usuário**] | Usuários(as) associados(as) às solicitações selecionadas serão temporariamente restringidos(as) de fazer solicitações de relatórios. |
      | [!UICONTROL **Projeto**] | Os projetos associados às solicitações selecionadas ficarão temporariamente fechados a todas as solicitações de relatórios. |
      | [!UICONTROL **Restrito para**] | Escolha por quanto tempo as solicitações serão restringidas. É possível escolher as opções 1 minuto (padrão), 5 minutos, 10 minutos, 15 minutos ou 30 minutos. <!-- double-check this --><p>Não é possível remover uma restrição antecipadamente após defini-la.</p> |

      {style="table-layout:auto"}

1. Selecione [!UICONTROL **Continuar com cancelamento**].

   Uma notificação é exibida no Analysis Workspace, informando aos usuários que a solicitação foi cancelada. Para mais informações sobre como isso aparece no Analysis Workspace, consulte [Experiência quando usuários acessam um relatório cancelado](#experience-when-users-access-a-cancelled-report).

## Cancelar solicitações por usuário

Você pode cancelar todas as solicitações associadas a um ou mais usuários.

1. No Adobe Analytics, acesse **[!UICONTROL Admin]** > **[!UICONTROL Gerenciador de atividades de relatórios]**.

1. Selecione o conjunto de relatórios no qual deseja cancelar as solicitações de relatórios. <!--double-check this step-->

   Para mais informações sobre os dados disponíveis nesta página, consulte [Exibir atividades de relatórios no gerenciador de atividades de relatórios](/help/admin/tools/reporting-activity-manager/reporting-activity.md).

1. Selecione a guia [!UICONTROL **Usuários**] e escolha um ou mais usuários.

   <!-- add screenshot -->

1. Selecione [!UICONTROL **Cancelar solicitações**].

   A caixa de diálogo [!UICONTROL **Cancelar _x_ solicitações de relatório de x usuários**] é exibida.

1. O campo Mensagem de cancelamento mostra a mensagem que é exibida aos usuários quando suas solicitações são canceladas. Uma mensagem padrão é fornecida. É possível atualizar a mensagem padrão para fornecer detalhes adicionais.

1. (Opcional) Para restringir solicitações futuras em um determinado período:

   1. Habilite a opção para [!UICONTROL **Restringir solicitações subsequentes**].

      ![Restringir solicitações subsequentes por usuário](assets/restrict-subsequent-requests-user.png)

   1. Escolha entre as seguintes opções:

      | Opção | Função |
      |---------|----------|
      | [!UICONTROL **Usuário e projeto**] | Usuários(as) selecionados(as) serão temporariamente restringidos(as) de fazer solicitações de relatórios para os projetos associados. |
      | [!UICONTROL **Usuário**] | Usuários(as) selecionados(as) serão temporariamente restringidos(as) de fazer solicitações de relatórios. |
      | [!UICONTROL **Projeto**] | Os projetos associados a usuários(as) selecionados(as) ficarão fechados a quaisquer solicitações de relatórios feitas por um(a) usuário(a). |
      | [!UICONTROL **Restrito para**] | Escolha por quanto tempo as solicitações serão restringidas. É possível escolher as opções 1 minuto (padrão), 5 minutos, 10 minutos, 15 minutos ou 30 minutos. <!--double-check this--> <p>Não é possível remover uma restrição antecipadamente após defini-la.</p> |

      {style="table-layout:auto"}

1. Selecione [!UICONTROL **Continuar com cancelamento**].

   Uma notificação é exibida no Analysis Workspace, informando aos usuários que a solicitação foi cancelada. Para mais informações sobre como isso aparece no Analysis Workspace, consulte [Experiência quando usuários acessam um relatório cancelado](#experience-when-users-access-a-cancelled-report).

## Cancelar solicitações por projeto

É possível cancelar todas as solicitações associadas a um ou mais projetos.

1. No Adobe Analytics, acesse **[!UICONTROL Admin]** > **[!UICONTROL Gerenciador de atividades de relatórios]**.

1. Selecione o conjunto de relatórios no qual deseja cancelar as solicitações de relatórios. <!--double-check this step-->

   Para obter mais informações sobre os dados disponíveis nesta página, consulte [Exibir atividade de relatório no Gerenciador de atividades de relatórios](/help/admin/tools/reporting-activity-manager/reporting-activity.md).

1. Selecione a guia [!UICONTROL **Projetos**] e escolha um ou mais projetos.

   <!-- add screenshot -->

1. Selecione [!UICONTROL **Cancelar solicitações**].

   A caixa de diálogo [!UICONTROL **Cancelar _x_ solicitações de relatório de x projetos**] é exibida.

1. O campo Mensagem de cancelamento mostra a mensagem que é exibida aos usuários quando suas solicitações são canceladas. Uma mensagem padrão é fornecida. É possível atualizar a mensagem padrão para fornecer detalhes adicionais.

1. (Opcional) Para restringir solicitações futuras em um determinado período:

   1. Habilite a opção de [!UICONTROL **Restringir solicitações seguintes**].

      ![Restringir solicitações subsequentes por projeto](assets/restrict-subsequent-requests-project.png)

   1. Escolha entre as seguintes opções:

      | Opção | Função |
      |---------|----------|
      | [!UICONTROL **Usuário e projeto**] | Os projetos selecionados ficarão temporariamente fechados a solicitações de relatórios feitas por usuários(as) associados(as). |
      | [!UICONTROL **Usuário**] | Usuários(as) associados(as) aos projetos selecionados serão restringidos(as) de fazer solicitações de relatórios. |
      | [!UICONTROL **Projeto**] | Os projetos selecionados ficarão temporariamente fechados a qualquer solicitação de relatório feita por usuários. |
      | [!UICONTROL **Restrito para**] | Escolha por quanto tempo as solicitações serão restringidas. É possível escolher as opções 1 minuto (padrão), 5 minutos, 10 minutos, 15 minutos ou 30 minutos. <!--double-check this--> <p>Não é possível remover uma restrição antecipadamente após defini-la.</p> |

      {style="table-layout:auto"}

1. Selecione [!UICONTROL **Continuar com cancelamento**].

   Uma notificação é exibida no Analysis Workspace, informando aos usuários que a solicitação foi cancelada. Para mais informações sobre como isso aparece no Analysis Workspace, consulte [Experiência quando usuários acessam um relatório cancelado](#experience-when-users-access-a-cancelled-report).

## Cancelar solicitações por aplicativo

É possível cancelar todas as solicitações associadas a um ou mais aplicativos. Ao cancelar solicitações associadas a um aplicativo, é possível optar por restringir ainda mais as solicitações associadas a esse aplicativo para um determinado período.

Os aplicativos incluem:

* Interface do Analysis Workspace
* Projetos agendados do Espaço de trabalho.
* Report Builder
* Interfaces do construtor: segmento, métricas calculadas, anotações, públicos-alvos etc.
* Chamadas de API da API 1.4 ou 2.0
* Alertas
* Links para compartilhar com qualquer pessoa
* Qualquer outro aplicativo que consulte o mecanismo de relatórios do Analytics

Para cancelar solicitações por aplicativo:

1. No Adobe Analytics, acesse **[!UICONTROL Admin]** > **[!UICONTROL Gerenciador de atividades de relatórios]**.

1. Selecione a conexão na qual deseja cancelar solicitações de relatórios. <!--double-check this step-->

   Para mais informações sobre os dados disponíveis nesta página, consulte [Exibir atividades de relatórios no gerenciador de atividades de relatórios](/help/admin/tools/reporting-activity-manager/reporting-activity.md).

1. Selecione a guia [!UICONTROL **Aplicativos**] e escolha um ou mais aplicativos.

   <!-- add screenshot -->

1. Selecione [!UICONTROL **Cancelar solicitações**].

   A caixa de diálogo [!UICONTROL **Cancelar _x_ solicitações de relatório de x projetos**] é exibida.

1. O campo Mensagem de cancelamento mostra a mensagem que é exibida aos usuários quando suas solicitações são canceladas. Uma mensagem padrão é fornecida. É possível atualizar a mensagem padrão para fornecer detalhes adicionais.

1. (Opcional) Para restringir solicitações futuras em um determinado período:

   1. Habilite a opção para [!UICONTROL **Restringir solicitações subsequentes**]

      ![Restringir solicitações subsequentes por aplicativo](assets/restrict-subsequent-requests-application.png)

   1. Escolha entre as seguintes opções:

      | Opção | Função |
      |---------|----------|
      | [!UICONTROL **Usuário e projeto**] | Os aplicativos selecionados ficarão temporariamente fechados a qualquer solicitação de relatório feita por usuários associados e projetos.<p>Esta é a opção menos restritiva.</p> |
      | [!UICONTROL **Usuário**] | Usuários associados aos aplicativos selecionados serão impedidos de fazer qualquer solicitação de relatório. |
      | [!UICONTROL **Projeto**] | Os projetos associados aos aplicativos selecionados ficarão fechados a qualquer solicitação de relatório feita por usuários. |
      | [!UICONTROL **Restrito para**] | Escolha por quanto tempo as solicitações serão restringidas. É possível escolher as opções 1 minuto (padrão), 5 minutos, 10 minutos, 15 minutos ou 30 minutos. <!--double-check this--> <p>Não é possível remover uma restrição antecipadamente após defini-la.</p> |

      {style="table-layout:auto"}

1. Selecione [!UICONTROL **Continuar com cancelamento**].

   Uma notificação é exibida no aplicativo (como no Analysis Workspace), informando aos usuários que a solicitação foi cancelada. Para obter mais informações sobre como isso aparece no Analysis Workspace, consulte [Experiência quando usuários acessam um relatório cancelado](#experience-when-users-access-a-cancelled-report).

## Experiência quando usuários acessam um relatório cancelado

No Analysis Workspace, os usuários veem as seguintes mensagens ao tentar acessar um relatório ou uma visualização afetada por um cancelamento:

### Mensagem no projeto

Quando usuários tentam acessar um projeto afetado por um cancelamento, veem uma mensagem informando que o relatório foi temporariamente restringido:

![Mensagem de cancelamento do projeto](assets/workspace-canceled-report.png)

### Mensagem na visualização

Quando usuários tentam acessar uma visualização afetada por um cancelamento, veem uma mensagem informando que o processamento de dados do relatório foi temporariamente restringido:

![Mensagem de cancelamento da visualização](assets/workspace-cancelled-visualization.png)
