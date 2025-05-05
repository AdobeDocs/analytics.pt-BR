---
title: Como converter pastas de trabalho Report Builder herdadas em blocos de dados
description: Descreve como converter suas solicitações herdadas em blocos de dados
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%

---

# Converter pastas de trabalho Report Builder herdadas em blocos de dados

Como parte da mudança para uma nova tecnologia Report Builder, você pode converter rapidamente suas pastas de trabalho legadas atuais para pastas de trabalho baseadas em JavaScript.

>[!IMPORTANT]
>
>Duplique cada pasta de trabalho e renomeie uma versão antes de convertê-la. Dessa forma, você ainda tem uma cópia da pasta de trabalho original, se necessário.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Converter pastas de trabalho](https://video.tv.adobe.com/v/3446187?quality=12&learn=on&captions=por_br){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]



1. Configure o novo Report Builder por [seguindo estas instruções](/help/analyze/report-builder/report-builder-setup.md).

1. Abra o Excel e clique no ícone Adobe Report Builder na parte superior direita.

1. Clique em **[!UICONTROL Logon]** e faça logon no Report Builder.

1. O suplemento Report Builder detecta se esta pasta de trabalho contém [solicitações Report Builder](/help/analyze/legacy-report-builder/home.md) herdadas.

   ![atualizar prompt da pasta de trabalho](assets/upgrade_workbook.png)

1. Se uma ou mais solicitações herdadas forem encontradas, clique em **[!UICONTROL Atualizar]** para atualizar uma pasta de trabalho.

   >[!NOTE]
   >
   >Você precisa atualizar cada solicitação individualmente. Não há suporte para atualização em massa.


1. Um aviso é exibido para alertá-lo sobre alterações na pasta de trabalho se você atualizar. Ele também recomenda criar um backup da pasta de trabalho herdada antes de continuar.

   ![aviso de atualização](assets/upgrade_warning.png)

1. Clique em **[!UICONTROL Continuar]** para continuar com a atualização.

   Se o upgrade for bem-sucedido, o seguinte aviso de conclusão será exibido:

   ![atualização concluída](assets/upgrade_complete.png)

1. (Opcional) Clique em **[!UICONTROL Baixar relatório de atualização]**. Este relatório contém o status em cada bloco de dados que foi atualizado.

Agora você pode [gerenciar o bloco de dados](/help/analyze/report-builder/manage-reportbuilder.md).


## Recursos de Report Builder herdados não são suportados no Novo Report Builder {#unsupported}

Ao comparar a funcionalidade do Report Builder herdado com o novo Suplemento de Report Builder, alguma funcionalidade herdada não está mais disponível:

- Solicitações em tempo real

- Relatório de caminho/fallout

- Opção de FTP para relatórios agendados

- Métricas de visitantes. As métricas a seguir serão convertidas em &quot;visitantes únicos&quot;, mesmo que o resultado do relatório não seja uma correspondência exata: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` e `visitorsyearly`. Isso também se aplica a `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` e `mobilevisitorsyearly`.

## Agendar uma pasta de trabalho convertida {#schedule}

Consulte [Agendar uma pasta de trabalho convertida](/help/analyze/report-builder/schedule-reportbuilder.md) no artigo de agendamento.