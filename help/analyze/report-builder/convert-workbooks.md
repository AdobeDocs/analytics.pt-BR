---
title: Converter suas pastas de trabalho herdadas do Report Builder
description: Entenda como converter suas pastas de trabalho herdadas baseadas em Report Builder para usar a nova Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: 504cce24babdd8aefa5f819433139671904f2e1e
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 0%

---

# Converter pastas de trabalho herdadas do Report Builder

Como parte da mudança para uma nova funcionalidade do Report Builder, você pode converter rapidamente suas pastas de trabalho atuais baseadas no Report Builder herdadas (pastas de trabalho herdadas) para usar a nova funcionalidade [blocos de dados](create-a-data-block.md) do Report Builder.

>[!IMPORTANT]
>
>Duplique cada pasta de trabalho e renomeie uma versão antes de converter a pasta de trabalho herdada. Isso garante que você sempre tenha uma cópia da pasta de trabalho herdada original, se necessário.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Converter pastas de trabalho](https://video.tv.adobe.com/v/3446187?captions=por_br&quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


>[!NOTE]
>
>Para converter pastas de trabalho herdadas, primeiro [configure a nova Report Builder](/help/analyze/report-builder/report-builder-setup.md).


## Abrir uma pasta de trabalho herdada

Para abrir uma pasta de trabalho herdada, é possível:

* Abra uma pasta de trabalho herdada agendada na guia **[!UICONTROL Agendamento]** no [hub do Report Builder](report-builder-hub.md). Esse é o método preferido para pastas de trabalho herdadas programadas. Você tem a opção de usar o agendamento associado à pasta de trabalho herdada assim que [agendar a pasta de trabalho herdada convertida](#schedule-a-converted-legacy-workbook).

   1. Abra o Excel e selecione ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** na barra de faixa do Excel.

   1. Selecione **[!UICONTROL Logon]** e faça logon no Report Builder.

   1. Selecione **[!UICONTROL Agendar]** no [hub do Report Builder](report-builder-hub.md).
   1. Selecione a guia **[!UICONTROL Herdado]**. A guia lista as pastas de trabalho agendadas baseadas no Report Builder herdadas.

      ![Aparências de trabalho herdadas](assets/upgrade-legacy-schedule.png)

   1. Selecione ![SelectBox](/help/assets/icons/SelectBox.svg) a pasta de trabalho agendada que você deseja converter da lista e selecione ![Download](/help/assets/icons/Download.svg). A pasta de trabalho é baixada e aberta em uma nova janela no Excel. Agora você pode [converter a pasta de trabalho herdada do Report Builder](#convert-a--workbook).


* Abra uma pasta de trabalho herdada diretamente do computador local ou da rede. Ao usar esse método, você não tem a opção de usar o agendamento que pode estar associado à pasta de trabalho herdada. <br/>Quando a pasta de trabalho herdada estiver aberta no Excel:

   1. Selecione ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** na barra de faixa do Excel.
   1. Selecione **[!UICONTROL Logon]** e faça logon no Report Builder.
   1. Em seguida [converta a pasta de trabalho herdada](#convert-a-workbook).


## Converter uma pasta de trabalho herdada

Para converter sua pasta de trabalho herdada:

1. Depois que você abre uma pasta de trabalho herdada, a nova Report Builder detecta se ela contém [solicitações herdadas do Report Builder](/help/analyze/legacy-report-builder/home.md).

   ![atualizar prompt da pasta de trabalho](assets/upgrade-workbook.png){zoomable="yes"}

1. Se uma ou mais solicitações herdadas forem encontradas, clique em **[!UICONTROL Atualizar]** na caixa de diálogo **[!UICONTROL Atualizar pasta de trabalho]** para atualizar a pasta de trabalho.

   >[!NOTE]
   >
   >Você precisa atualizar cada solicitação individualmente. Não há suporte para atualização em massa.


1. Uma caixa de diálogo **[!UICONTROL Aviso]** é exibida, alertando você sobre as alterações na pasta de trabalho se você atualizar. Ele também recomenda criar um backup da pasta de trabalho herdada antes de continuar.

   ![aviso de atualização](assets/upgrade-warning.png){zoomable="yes"}

1. Clique em **[!UICONTROL Continuar]** para continuar com a atualização.

   Se a atualização for bem-sucedida, uma notificação **[!UICONTROL A atualização da pasta de trabalho foi concluída]** será exibida.

   ![atualização concluída](assets/upgrade-complete.png)

   * Selecione **[!UICONTROL Fechar]** para fechar a notificação e continuar trabalhando na pasta de trabalho com solicitações atualizadas para a nova Report Builder.

   * Selecione **[!UICONTROL Baixar relatório de atualização]** para baixar e abrir uma nova pasta de trabalho do Excel que mostre o resultado da atualização. Para obter um exemplo, consulte abaixo.

     ![Pasta de trabalho de relatório de atualização do Excel Report Builder](assets/upgrade-report.png)

Agora você pode [gerenciar os blocos de dados](/help/analyze/report-builder/manage-reportbuilder.md) na pasta de trabalho. Esses blocos de dados são o resultado da atualização e da substituição de solicitações herdadas do Report Builder.


## Agendar uma pasta de trabalho herdada convertida

Você tem a opção de usar os detalhes do agendamento da pasta de trabalho herdada que você baixou e abriu na guia **[!UICONTROL Agendamento]** no hub do Report Builder. Essa opção não está disponível para pastas de trabalho herdadas com detalhes de agendamento que você abre no computador local ou na rede.

1. Para programar uma pasta de trabalho herdada convertida com uma programação herdada:

   * Selecione **[!UICONTROL Enviar pasta de trabalho]** no hub do Report Builder ou
   * Selecione **[!UICONTROL Pasta de trabalho de agendamento]** na guia **[!UICONTROL Pastas de trabalho]**, disponível na guia **[!UICONTROL Agendamentos]**, no Report Builder.

1. Você pode usar os detalhes da programação da pasta de trabalho herdada como as configurações padrão da programação.

   ![Migrar agendamento de pasta de trabalho herdada](assets/upgrade-legacy-schedule-convert.png)

   * Selecione **[!UICONTROL Usar]** para usar os detalhes do agendamento herdado. Os detalhes do agendamento são preenchidos previamente na interface [Enviar pasta de trabalho](schedule-reportbuilder.md#schedule-a-workbook).
   * Selecione **[!UICONTROL Não usar]** para não usar os detalhes do cronograma herdado.
   * Selecione **[!UICONTROL Cancelar]** para cancelar.

   Selecione **[!UICONTROL Remover metadados herdados do uso futuro]** para não usar os detalhes do agendamento herdado para esta pasta de trabalho no futuro.


## Recursos herdados do Report Builder não suportados {#unsupported}

Parte da funcionalidade herdada do Report Builder não está mais disponível na nova Report Builder

* Solicitações em tempo real.

* Relatório de caminho/fallout.

* Opção de FTP para relatórios agendados.

* Métricas de visitantes. As métricas a seguir são convertidas em *visitantes únicos*, mesmo que o resultado do relatório não seja uma correspondência exata: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` e `visitorsyearly`. Esta conversão também se aplica a `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` e `mobilevisitorsyearly`.
