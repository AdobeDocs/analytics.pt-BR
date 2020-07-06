---
description: Utilize o Gerenciador de painéis para copiar, compartilhar, arquivar e agendar a entrega de painéis.
subtopic: Dashboards
title: Gerenciador do painel
topic: Reports and analytics
uuid: 380fd148-2ed9-43bf-9d42-46e373e788e4
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 100%

---


# Gerenciador do painel

Utilize o Gerenciador de painéis para copiar, compartilhar, arquivar e agendar a entrega de painéis.

>[!IMPORTANT]
>
>A prática recomendada ao usar o Gerenciador de painel é ter no máximo 300 painéis para qualquer usuário. Além disso, observe que o gerenciador carrega todos os painéis compartilhados abaixo, portanto, seja criterioso em compartilhar painéis.

## Gerenciador do painel

Utilize o Gerenciador de painéis para copiar, compartilhar, arquivar e agendar a entrega de painéis.

Clique em **[!UICONTROL Análises]** > **[!UICONTROL Componentes]** > **[!UICONTROL Painéis]**.

| Elemento | Descrição |
|--- |--- |
| Compartilhado | Mostra se o painel é compartilhado. |
| Programado | Permite programar a entrega do painel. |
| Visualizar Arquivo | Essa funcionalidade não está mais disponível. |
| Encaminhar para Usuários | Permite que você compartilhe um painel. |
| Gerenciar | Permite que você edite, copie e exclua um painel. |

## Gerenciar painéis compartilhados

Etapas que descrevem como usar as opções de gerenciamento de painel compartilhadas.

1. Vá até **[!UICONTROL Análises]** > **[!UICONTROL Componentes]** > **[!UICONTROL Painéis]**.
1. Em [!UICONTROL Painéis compartilhados], encontre o painel compartilhado (ou painel herdado) você deseja gerenciar e escolher um ou mais das seguintes opções:

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

>[!NOTE]
>
>Após a migração, considere a utilização de [projetos da Analysis Workspace](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html) e seus recursos de download e agendamento.

Ao copiar o painel legado, o sistema abre o painel para edição, onde você pode adicionar conteúdo legado ou novo conteúdo. Ao copiar um painel legado, o original é preservado em uma lista de painéis legados.

>[!NOTE]
>
>Adicionar conteúdo herdado a um painel cria um painel com base na funcionalidade mais recente do painel. No entanto, o reportlet legado pode conter dados com base na plataforma de dados anterior.

**Para migrar de uma versão de painel legado 14.x**

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Componentes]** > **[!UICONTROL Gerenciar painéis]**.
1. Na coluna [!UICONTROL Gerenciar], em [!UICONTROL Painéis legados], clique em **[!UICONTROL Copiar para novo painel]**.

   O painel copiado será aberto no editor de layout de painel.

   Consulte [Editar um painel de dados de reportlet](/help/analyze/reports-analytics/dashboard.md).

## Compartilhar um painel

Etapas que descrevem como um administrador pode compartilhar (ou promover) um painel para vários usuários. Ao fazer o push de painéis para os usuários, os painéis ficam disponíveis no menu [!UICONTROL Painéis compartilhados] do usuário.

1. No [!UICONTROL Gerenciador de painel], localize o painel e, em seguida, habilite a opção **[!UICONTROL Compartilhado]**.
1. Clique em **[!UICONTROL Encaminhar para usuários]**.  ![](assets/push.png)

1. Na página [!UICONTROL Encaminhar painel], selecione os usuários de destino ou clique em **[!UICONTROL Marcar tudo]**.
1. Clique em **[!UICONTROL Salvar]**.

Se alterado, os usuários do seu painel não poderão visualizar as alterações realizadas. Verifique seu Gerenciador de painel para ver se os usuários selecionaram a opção **[!UICONTROL Copiar-me]**. Em caso afirmativo, eles não poderão visualizar as atualizações/alterações realizadas por você. Para visualizar todas as alterações/atualizações, os usuários compartilhados precisam selecionar a opção **[!UICONTROL No Menu]** no Gerenciador de painel.

## Programar um painel para entrega

No [!UICONTROL Gerenciador de painéis], você pode verificar se um painel está agendado para entrega e editar o agendamento. As opções de entrega do painel são idênticas às opções de entrega do relatório.

1. Abra um painel.
1. Clique em **[!UICONTROL Mais]** > **[!UICONTROL Enviar]**.

   Consulte [Agendamento e distribuição](/help/analyze/reports-analytics/scheduling.md) para obter mais informações.

## Arquivar um painel

>[!NOTE]
>
>Essa funcionalidade não estará mais disponível em janeiro de 2020.

Etapas que descrevem como arquivar qualquer painel enviado como um arquivo PDF. O sistema armazena o arquivo armazenado por dois anos, ou até atingir o limite máximo de 4 GB de relatórios arquivados.

1. Abra um painel.
1. Clique em **[!UICONTROL Mais]** > **[!UICONTROL Enviar]**.
1. No grupo [!UICONTROL Relatório de email], habilite a opção **[!UICONTROL Arquivar]**.
1. Especifique as opções de entrega e, em seguida, clique em **[!UICONTROL Enviar]**.

   Você pode visualizar painéis arquivados no Gerenciador de painel. Como opção, abra um painel e clique em **[!UICONTROL Mais]** > **[!UICONTROL Exibir arquivo]**.
