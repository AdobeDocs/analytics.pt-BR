---
description: Utilize o Gerenciador de painéis para copiar, compartilhar, arquivar e agendar a entrega de painéis.
subtopic: Dashboards
title: Gerenciador do painel
topic: Reports and analytics
uuid: 380fd148-2ed9-43bf-9d42-46e373e788e4
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Gerenciador do painel

Utilize o Gerenciador de painéis para copiar, compartilhar, arquivar e agendar a entrega de painéis.

>[!IMPORTANT]
>
>A prática recomendada ao usar o Gerenciador de painel é ter no máximo 300 painéis para qualquer usuário. Além disso, observe que o gerenciador carrega todos os painéis compartilhados abaixo, portanto, seja criterioso em compartilhar painéis.

## Gerenciador do painel

Utilize o Gerenciador de painéis para copiar, compartilhar, arquivar e agendar a entrega de painéis.

Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.

| Elemento | Descrição |
|--- |--- |
| Compartilhado | Mostra se o painel é compartilhado. |
| Programado | Permite agendar o painel para o delivery. |
| Visualizar Arquivo | Essa funcionalidade não está mais disponível. |
| Enviar para usuários | Permite que você compartilhe um painel. |
| Gerenciar | Permite editar, copiar e excluir um painel. |

## Gerenciar painéis compartilhados

Etapas que descrevem como usar as opções de gerenciamento de painéis compartilhadas.

1. Vá para **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.
1. Under [!UICONTROL Shared Dashboards], locate the shared dashboard (or legacy dashboard) you want to manage and choose one or more of the following options:

<table id="choicetable_857E0E816D63404683D4E24DC8D7FC69"> 
 <thead class="chhead sthead"> 
  <th class="choptionhd"> Opção </th> 
  <th class="chdeschd"> Descrição </th> 
 </thead> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Visualizar Arquivo</strong></td> 
  <td class="chdesc stentry"> Essa funcionalidade não está mais disponível. </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Reprodutor do painel</strong></td> 
  <td class="chdesc stentry"> <p>Os servidores do SiteCatalyst 14 não responderão mais às solicitações de dados do Reprodutor de Painéis. Todos os painéis que estão sendo exibidos no Painel Player podem ser acessados na interface padrão do Relatórios e análises ou recriados como Painéis em tempo real. Os painéis em tempo real foram especificamente projetados para exibição contínua e incluem um modo de tela cheia para permitir a exibição em TVs ou outros dispositivos de tela grande. </p> <p>Ação necessária: É necessário interromper o uso do Painel Player. </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Copiar-me</strong></td> 
  <td class="chdesc stentry"> Adiciona uma cópia à sua lista de painéis, usando o mesmo nome do original. No entanto, não é possível visualizar nenhuma atualização/alteração feita pelo proprietário do painel. Copiar um painel legado abre um painel em branco, no qual você pode adicionar conteúdo legado. <p>Importante: se alterado, os usuários do painel não poderão visualizar as alterações feitas no painel. Verifique seu Gerenciador de painel para ver se os usuários selecionaram a opção <span class="uicontrol">Copiar-me</span>. Em caso afirmativo, eles não poderão visualizar as atualizações/alterações realizadas por você. Para visualizar todas as alterações/atualizações, os usuários compartilhados precisam selecionar a opção <span class="uicontrol">No Menu</span> no Gerenciador de painel. </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>No Menu</strong></td> 
  <td class="chdesc stentry"> Permite que você visualize alterações/atualizações efetuadas pelo proprietário do painel. </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Não Compartilhar</strong></td> 
  <td class="chdesc stentry"> Remove o painel pela lista dos painéis compartilhados. </td> 
 </tr> 
</table>

## Migrar um painel legado

Os painéis herdados existentes continuarão em execução e você ainda poderá editá-los, baixá-los e agendá-los; no entanto, não é mais possível criar novos painéis herdados. É altamente recomendável atualizar os painéis herdados existentes para o formato de painel mais recente.

>[!NOTE] Após a migração, considere a utilização de [projetos da Analysis Workspace](https://marketing.adobe.com/resources/help/pt_BR/analytics/analysis-workspace/) e seus recursos de download e agendamento.

Quando você copia o painel legado, o sistema abre o painel legado para edição, onde você pode adicionar conteúdo legado ou novo conteúdo. Quando você copia um painel legado, o original é preservado na lista dos painéis herdados.

>[!NOTE] Adicionar conteúdo herdado a um painel cria um painel com base na funcionalidade mais recente do painel. No entanto, o reportlet legado pode conter dados baseados na plataforma de dados anterior.

**Para migrar um painel legado da versão 14.x**

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. Na [!UICONTROL Manage] coluna, em [!UICONTROL Legacy Dashboards], clique em **[!UICONTROL Copy to New Dashboard]**.

   O painel copiado é aberto no editor de layout de painéis.

   See [Editing Dashboard and Reportlet Data](/help/analyze/reports-analytics/dashboard.md).

## Compartilhar um painel

Etapas que descrevem como um administrador pode compartilhar (ou encaminhar) um painel para vários usuários. Quando você envia painéis para os usuários, os painéis ficam disponíveis no [!UICONTROL Shared Dashboards] menu do usuário.

1. Na página [!UICONTROL Dashboard Manager], localize o painel e ative **[!UICONTROL Shared]**.
1. Clique em **[!UICONTROL Push To Users]**.  ![](assets/push.png)

1. Na [!UICONTROL Push Dashboard] página, selecione os usuários do público alvo ou clique em **[!UICONTROL Check All]**.
1. Clique em **[!UICONTROL Save]**.

If shared users of your dashboard cannot see changes you made in the dashboard, check your Dashboard Manager to see if the users have chosen the **[!UICONTROL Copy Me]** option. Em caso afirmativo, eles não poderão visualizar as atualizações/alterações realizadas por você. To see all the changes/updates, shared users need to select the **[!UICONTROL On Menu]** option in the Dashboard Manager.

## Agendar um painel para o delivery

No [!UICONTROL Dashboard Manager], você pode ver se um painel está programado para delivery e editar o agendamento. As opções de delivery do painel são idênticas às opções de delivery do relatório.

1. Abra um painel.
1. Clique em **[!UICONTROL More]** > **[!UICONTROL Send]**.

   Consulte [Agendamento e distribuição](/help/analyze/reports-analytics/scheduling.md) para obter mais informações.

## Arquivar um painel

>[!NOTE] Essa funcionalidade não estará mais disponível em janeiro de 2020.

Etapas que descrevem como arquivar qualquer painel enviado como um arquivo PDF. O sistema armazena o arquivo arquivado por dois anos ou até atingir um limite máximo de 4 GB de relatórios arquivados, o que ocorrer primeiro.

1. Abra um painel.
1. Clique em **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. No [!UICONTROL Email Report] grupo, ative **[!UICONTROL Archive]**.
1. Specify delivery options, then click **[!UICONTROL Send]**.

   Você pode visualização painéis arquivados no Gerenciador de Painéis. Como alternativa, abra um painel e clique em **[!UICONTROL More]** > **[!UICONTROL View Archive]**.
