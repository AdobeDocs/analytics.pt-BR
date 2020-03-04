---
description: Utilize o Gerenciador de painéis para copiar, compartilhar, arquivar e agendar a entrega de painéis.
subtopic: Dashboards
title: Gerenciador do painel
topic: Reports and analytics
uuid: 380fd148-2ed9-43bf-9d42-46e373e788e4
translation-type: tm+mt
source-git-commit: 92eaaeafdd587febcfe7fe60f696baca0691b4bc

---


# Gerenciador do painel

Utilize o Gerenciador de painéis para copiar, compartilhar, arquivar e agendar a entrega de painéis.

>[!IMPORTANT]
>
>A prática recomendada ao usar o Gerenciador de painel é ter no máximo 300 painéis para qualquer usuário. Além disso, observe que o gerente carrega todos os painéis compartilhados abaixo, portanto, seja criterioso com o compartilhamento de painéis.

## Gerenciador do painel

Utilize o Gerenciador de painéis para copiar, compartilhar, arquivar e agendar a entrega de painéis.

Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Dashboards]**.

| Elemento | Descrição |
|--- |--- |
| Compartilhado | Mostra se o painel é compartilhado. |
| Programado | Permite programar a entrega do painel. |
| Visualizar Arquivo | Essa funcionalidade não está mais disponível. |
| Encaminhar para Usuários | Permite que você compartilhe um painel. |
| Gerenciar | Permite que você edite, copie e exclua um painel. |

## Gerenciar painéis compartilhados

Etapas que descrevem como usar as opções de gerenciamento de painel compartilhadas.

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
  <td class="chdesc stentry"> <p>Os servidores do SiteCatalyst 14 não responderão mais às solicitações de dados do Reprodutor do painel. Qualquer painel exibido atualmente no Reprodutor do painel pode ser acessado na interface padrão do Reports &amp; Analytics ou recriado como um Painel em tempo real. Os Painéis em tempo real foram especificamente projetados para exibição contínua e incluem um modo de tela inteira para permitir a exibição em TVs ou em outros dispositivos de tela grande. </p> <p>Ação necessária: você deve interromper o uso do Reprodutor do painel. </p> </td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Copiar-me</strong></td> 
  <td class="chdesc stentry"> Adiciona uma cópia à lista de painéis, usando o mesmo nome do original. No entanto, você não pode visualizar qualquer atualização/alteração efetuada pelo proprietário do painel. A cópia de um painel legado abre um painel em branco, no qual você pode adicionar conteúdo legado. <p>Importante: se alterado, os usuários do painel não poderão visualizar as alterações feitas no painel. Verifique seu Gerenciador de painel para ver se os usuários selecionaram a opção <span class="uicontrol">Copiar-me</span>. Em caso afirmativo, eles não poderão visualizar as atualizações/alterações realizadas por você. Para visualizar todas as alterações/atualizações, os usuários compartilhados precisam selecionar a opção <span class="uicontrol">No Menu</span> no Gerenciador de painel. </p> </td> 
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

Os painéis legados existentes continuarão em execução, e você ainda poderá editar, baixar e agendar os painéis; entretanto, você não poderá mais criar novos painéis legados. É altamente recomendável atualizar os painéis legados existentes para o formato de painel mais recente.

> [!NOTE] Além disso, considere usar projetos [da](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) Analysis Workspace e sua capacidade de serem baixados e programados.

Ao copiar o painel legado, o sistema abre o painel para edição, onde você pode adicionar conteúdo legado ou novo conteúdo. Ao copiar um painel legado, o original é preservado em uma lista de painéis legados.

> [!NOTE] Adicionar conteúdo legado a um painel cria um painel com base na funcionalidade mais recente do painel. No entanto, o reportlet legado pode conter dados com base na plataforma de dados anterior.

**Para migrar de uma versão de painel legado 14.x**

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. Na [!UICONTROL Manage] coluna, em [!UICONTROL Legacy Dashboards], clique em **[!UICONTROL Copy to New Dashboard]**.

   O painel copiado será aberto no editor de layout de painel. 

   Consulte [Editar um painel de dados de reportlet](/help/analyze/reports-analytics/dashboard.md).

## Compartilhar um painel

Etapas que descrevem como um administrador pode compartilhar (ou promover) um painel para vários usuários. When you push dashboards to users, the dashboards become available in user&#39;s [!UICONTROL Shared Dashboards] menu.

1. No [!UICONTROL Dashboard Manager], localize o painel e ative **[!UICONTROL Shared]**.
1. Clique em **[!UICONTROL Push To Users]**.  ![](assets/push.png)

1. Na [!UICONTROL Push Dashboard] página, selecione os usuários de destino ou clique em **[!UICONTROL Check All]**.
1. Clique em **[!UICONTROL Save]**.

If shared users of your dashboard cannot see changes you made in the dashboard, check your Dashboard Manager to see if the users have chosen the **[!UICONTROL Copy Me]** option. Em caso afirmativo, eles não poderão visualizar as atualizações/alterações realizadas por você. To see all the changes/updates, shared users need to select the **[!UICONTROL On Menu]** option in the Dashboard Manager.

## Programar um painel para entrega

In the [!UICONTROL Dashboard Manager], you can see whether a dashboard is scheduled for delivery, and edit the schedule. As opções de entrega do painel são idênticas às opções de entrega do relatório.

1. Abra um painel.
1. Clique em **[!UICONTROL More]** > **[!UICONTROL Send]**.

   See [Schedule and Distribution](/help/analyze/reports-analytics/scheduling.md) for more information.

## Arquivar um painel

> [!NOTE] Essa funcionalidade não estará mais disponível em janeiro de 2020.

Etapas que descrevem como arquivar qualquer painel enviado como um arquivo PDF. O sistema armazena o arquivo armazenado por dois anos, ou até atingir o limite máximo de 4 GB de relatórios arquivados.

1. Abra um painel.
1. Clique em **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. No [!UICONTROL Email Report] grupo, ative **[!UICONTROL Archive]**.
1. Specify delivery options, then click **[!UICONTROL Send]**.

   Você pode visualizar painéis arquivados no Gerenciador de painel. Como alternativa, abra um painel e clique em **[!UICONTROL More]** > **[!UICONTROL View Archive]**.
