---
title: Converter pastas de trabalho herdadas do Report Builder
description: Saiba como migrar e converter pastas de trabalho herdadas do Report Builder para a nova Report Builder. Siga as instruções passo a passo neste guia de migração sobre como converter facilmente pastas de trabalho baseadas no Adobe Analytics.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: 9743d7ac2a6c7e63d7a6701e60d05683c5680d36
workflow-type: tm+mt
source-wordcount: '1179'
ht-degree: 0%

---

# Converter pastas de trabalho herdadas do Report Builder

O Report Builder herdado será encerrado em junho de 2026. Você deve migrar suas pastas de trabalho do Report Builder herdado para o novo Report Builder. O novo Report Builder oferece uma maneira conveniente de migrar rapidamente pastas de trabalho criadas com o Report Builder herdado.

>[!IMPORTANT]
>
>Duplique cada pasta de trabalho e renomeie uma versão antes de converter a pasta de trabalho herdada. Isso garante que você sempre tenha uma cópia da pasta de trabalho herdada original, se necessário.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Converter pastas de trabalho](https://experienceleague.adobe.com/pt-br/docs/analytics-learn/tutorials/exporting/report-builder/upgrade-and-reschedule-workbooks){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


>[!NOTE]
>
>Para converter pastas de trabalho herdadas, primeiro [configure a nova Report Builder](/help/analyze/report-builder/report-builder-setup.md).


## Abrir uma pasta de trabalho herdada

Para abrir uma pasta de trabalho herdada, é possível:

* Abra uma pasta de trabalho herdada agendada na guia **[!UICONTROL Agendamento]** no [hub do Report Builder](report-builder-hub.md). Esta ação é o método preferido para pastas de trabalho herdadas programadas. Você tem a opção de usar o agendamento associado à pasta de trabalho herdada assim que [agendar a pasta de trabalho herdada convertida](#schedule-a-converted-legacy-workbook).

   1. Abra [!DNL Excel] e selecione ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** na barra de faixa [!DNL Excel].

   1. Selecione **[!UICONTROL Logon]** e faça logon no Report Builder.

   1. Selecione **[!UICONTROL Agendar]** no [hub do Report Builder](report-builder-hub.md).
   1. Selecione a guia **[!UICONTROL Herdado]**. A guia lista as pastas de trabalho agendadas baseadas no Report Builder herdadas que você criou.

      ![Aparências de trabalho herdadas](assets/upgrade-legacy-schedule.png)

   1. Selecione ![SelectBox](/help/assets/icons/SelectBox.svg) a pasta de trabalho agendada que você deseja converter da lista e selecione ![Download](/help/assets/icons/Download.svg). A pasta de trabalho foi baixada e é aberta em uma nova janela em [!DNL Excel]. Agora você pode [converter a pasta de trabalho herdada do Report Builder](#convert-a--workbook).


* Abra uma pasta de trabalho herdada diretamente do computador local ou da rede. Ao usar esse método, você não tem a opção de usar o agendamento que pode estar associado à pasta de trabalho herdada. <br/>Quando a pasta de trabalho herdada estiver aberta em [!DNL Excel]:

   1. Selecione ![AdobeLogoRedOnWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** na barra de faixa de opções [!DNL Excel].
   1. Selecione **[!UICONTROL Logon]** e faça logon no Report Builder.
   1. Em seguida [converta a pasta de trabalho herdada](#convert-a-workbook).


## Converter uma pasta de trabalho herdada

Para converter sua pasta de trabalho herdada:

1. Depois que você abre uma pasta de trabalho herdada, a nova Report Builder detecta se ela contém [solicitações herdadas do Report Builder](/help/analyze/legacy-report-builder/home.md).

   ![Captura de tela do relatório de atualização do Report Builder [!DNL Excel] mostrando a atualização da migração](assets/upgrade-workbook.png){zoomable="yes"}

1. Se uma ou mais solicitações herdadas forem encontradas, clique em **[!UICONTROL Atualizar]** na caixa de diálogo **[!UICONTROL Atualizar pasta de trabalho]** para atualizar a pasta de trabalho.

   >[!NOTE]
   >
   >Você precisa atualizar cada solicitação individualmente. Não há suporte para atualização em massa.


1. Uma caixa de diálogo **[!UICONTROL Aviso]** é exibida, alertando você sobre as alterações na pasta de trabalho se você atualizar. Ele também recomenda criar um backup da pasta de trabalho herdada antes de continuar.

   ![Captura de tela do relatório de atualização do Report Builder [!DNL Excel] mostrando o aviso de migração](assets/upgrade-warning.png){zoomable="yes"}

1. Clique em **[!UICONTROL Continuar]** para continuar com a atualização.

   Se a atualização for bem-sucedida, uma notificação **[!UICONTROL A atualização da pasta de trabalho foi concluída]** será exibida.

   ![Captura de tela do relatório de atualização do Report Builder [!DNL Excel] mostrando a migração concluída](assets/upgrade-complete.png)

   * Selecione **[!UICONTROL Fechar]** para fechar a notificação e continuar trabalhando na pasta de trabalho com solicitações atualizadas para a nova Report Builder.

   * Selecione **[!UICONTROL Baixar relatório de atualização]** para baixar e abrir uma nova pasta de trabalho [!DNL Excel] que mostre o resultado da atualização. Para obter um exemplo, consulte abaixo.

     ![Captura de tela do relatório de atualização do Report Builder [!DNL Excel] mostrando o relatório de migração](assets/upgrade-report.png)

Agora você pode [gerenciar os blocos de dados](/help/analyze/report-builder/manage-reportbuilder.md) na pasta de trabalho. Esses blocos de dados são o resultado da atualização e da substituição de solicitações herdadas do Report Builder.


## Agendar uma pasta de trabalho herdada convertida

Você tem a opção de usar os detalhes do agendamento da pasta de trabalho herdada que você baixou e abriu na guia **[!UICONTROL Agendamento]** no hub do Report Builder. Essa opção não está disponível para pastas de trabalho herdadas com detalhes de agendamento que você abre no computador local ou na rede.

1. Para programar uma pasta de trabalho herdada convertida com uma programação herdada:

   * Selecione **[!UICONTROL Enviar pasta de trabalho]** no hub do Report Builder ou
   * Selecione **[!UICONTROL Pasta de trabalho de agendamento]** na guia **[!UICONTROL Pastas de trabalho]**, disponível na guia **[!UICONTROL Agendamentos]**, no Report Builder.

1. Você pode usar os detalhes da programação da pasta de trabalho herdada como as configurações padrão da programação.

   ![Captura de tela de [!DNL Excel] opções de configurações de agendamento herdadas do Report Builder](assets/upgrade-legacy-schedule-convert.png)

   * Selecione **[!UICONTROL Usar]** para usar os detalhes do agendamento herdado. Os detalhes do agendamento são preenchidos previamente na interface [Enviar pasta de trabalho](schedule-reportbuilder.md#schedule-a-workbook).
   * Selecione **[!UICONTROL Não usar]** para não usar os detalhes do cronograma herdado.
   * Selecione **[!UICONTROL Cancelar]** para cancelar.

   Selecione **[!UICONTROL Remover metadados herdados do uso futuro]** para não usar os detalhes do agendamento herdado para esta pasta de trabalho no futuro.


## Migrar do Report Builder herdado

Alguns recursos do Report Builder herdado não são compatíveis, parcialmente compatíveis ou implementados de forma diferente no Report Builder:

* **Solicitações em tempo real**. As solicitações em tempo real não são suportadas e são removidas da pasta de trabalho herdada convertida.

* **Relatórios de Caminho/Fallout**. As solicitações de fallout não são compatíveis e são removidas da pasta de trabalho herdada convertida.

* **[!DNL FTP]opção para relatórios agendados**. A opção para agendar relatórios para envio para um local [!DNL FTP] não está mais disponível.

* **Opção Publicar pasta de trabalho em [!DNL Power BI] para relatórios agendados**. A opção de agendar relatórios para [!DNL Power BI] não está mais disponível.

* **Métricas de visitantes**. As métricas a seguir são convertidas em *visitantes únicos* na pasta de trabalho herdada convertida, mesmo que o resultado do relatório não seja uma correspondência exata: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` e `visitorsyearly`. Esta conversão também se aplica a `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` e `mobilevisitorsyearly`.

* **Reautenticação automática**. Ao abrir um novo arquivo [!DNL Excel], é necessário autenticar novamente explicitamente. Esta reautenticação é um recurso de segurança da funcionalidade [!DNL Office Add-ins].

* **Copie uma planilha com um grupo de blocos de dados**. Para suportar a cópia de uma planilha que contém mais de um bloco de dados:

   1. Selecione a guia da planilha na pasta de trabalho [!DNL Excel] que você deseja copiar.
   1. No menu de contexto da guia, selecione **[!UICONTROL Mover ou Copiar...]**
   1. Na caixa de diálogo **[!UICONTROL Mover ou Copiar]**:
      1. Selecione para onde deseja copiar a planilha copiada.
      1. Habilite **[!UICONTROL Criar uma cópia]**.
      1. Selecione **[!UICONTROL OK]**.
   1. Na planilha de origem:
      1. Selecione o intervalo de células que abrange todos os blocos de dados.
      1. Selecione ![Copiar](/help/assets/icons/Copy.svg) **[!UICONTROL Copiar bloco de dados]** do [hub de Report Builder](/help/analyze/report-builder/report-builder-hub.md).
   1. Na planilha de destino:
      1. Selecione a célula na qual deseja colar o intervalo de células copiado.
      1. Selecione ![Colar](/help/assets/icons/Paste.svg) **[!UICONTROL Colar bloco de dados]** do [hub do Report Builder](/help/analyze/report-builder/report-builder-hub.md).

* **Intervalo de datas**. O Report Builder não migra as opções de formatação de intervalo de datas **[!UICONTROL Mostrar período inicial e final como]** aplicadas a um rótulo de linha para um intervalo de datas no Report Builder herdado.

* **Média**. O Report Builder não migra a opção de formatação selecionada **[!UICONTROL Opções médias]** (**[!UICONTROL Média diária]** até **[!UICONTROL Média anual]**) aplicada a uma métrica no Report Builder herdado. Use uma métrica calculada para substituir a opção selecionada.

* **Incluir texto** como prefixo/sufixo. O Report Builder não migra o **[!UICONTROL Incluir/incluir como prefixo]** aplicado a uma métrica no Report Builder herdado.

* **Subtotais**. A Report Builder não migra a opção de formatação **[!UICONTROL SubTotal(esta solicitação)]** aplicada a uma métrica no Report Builder herdado. Quando você tiver usado **[!UICONTROL SubTotal(esta solicitação)]** em uma solicitação de pasta de trabalho herdada, a funcionalidade será convertida em **[!UICONTROL Total]**. Por exemplo: em um bloco de dados herdado com cinco nomes de página principais, onde você usou **[!UICONTROL SubTotal(Exibições de Página)]** para retornar a soma das exibições de página para os cinco nomes de página principais. Após a migração, o mesmo bloco de dados com os 5 nomes de página principais retorna a soma das exibições de página para *todos* nomes de página. Use a funcionalidade de métricas calculadas para substituir a funcionalidade herdada **[!UICONTROL SubTotal]**.
