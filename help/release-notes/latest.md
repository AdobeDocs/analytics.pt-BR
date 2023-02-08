---
title: Notas de versão mais recentes do Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: e7140b78b7b2c6c63cb93f1341581cc83af7b33b
workflow-type: tm+mt
source-wordcount: '954'
ht-degree: 62%

---

# Notas de versão atuais do Adobe Analytics (fevereiro de 2023)

**Última atualização**: 2 de fevereiro de 2023

As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados no Adobe Analytics

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Interface do usuário atualizada para rótulos de Privacidade de dados** | A interface atualizada simplifica o processo de criação, gerenciamento e edição de rótulos de privacidade de dados para componentes do conjunto de relatórios. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-setup-reportsuite.html?lang=en) | N/D | 8 de fevereiro de 2023 |
| **Intervalos de datas de comparação em Scorecards para dispositivos móveis** | Com os Scorecards para dispositivos móveis, você pode alternar a variável **[!UICONTROL Incluir datas de comparação]** configuração para exibir ou ocultar datas de comparação. | N/D | 8 de fevereiro de 2023 |
| **Atualizações do calendário no Workspace** | <ul><li>Datas do painel de âncora: Você pode tornar os componentes do intervalo de datas relativos ao calendário do painel. [Saiba mais](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates)</li><li>Atualizações do estilo do calendário: Os estilos de calendário na interface do usuário foram atualizados para apresentar um fluxo de trabalho mais consistente e fácil de usar.</li><li>Atualizações da fórmula do calendário: Se você usar datas relativas, todas as fórmulas do calendário refletirão o início do intervalo de datas do painel. [Saiba mais](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#formula-relative-dates)</li></ul> | N/D | 8 de fevereiro de 2023 |
| **Filtragem de linha/coluna para transmissão do conector de origem do Adobe Analytics** | O Conector de origem do Analytics no Adobe Experience Platform agora permite filtrar os dados do Analytics, que são usados para preencher perfis no [Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR). A filtragem de nível de linha ajuda a reduzir o número de eventos associados a perfis. A filtragem de nível de coluna ajuda a reduzir a riqueza dos eventos, permitindo otimizar o uso dos direitos do perfil. Essa filtragem se aplica somente aos dados enviados para o Perfil do cliente em tempo real e [Serviço de identidade](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=pt-BR). **A filtragem não afeta os dados enviados para o Data Lake para uso em aplicativos como o Customer Journey Analytics**. [Saiba mais](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile) | N/D | 22 de fevereiro de 2023 |

{style=&quot;table-layout:auto&quot;}

## Correções no Adobe Analytics

-302282; AN-303127; AN-303541; AN-303550; AN-305282; AN-306504; AN-307351; AN-307496; AN-307530; AN-307947; AN-308497; AN-; AN-308610; AN-308777; AN-308994; AN-309143; AN-309404; AN-309414; AN-309445; AN-309575; AN-309630; AN-309658; AN-309690; AN-309742; AN-309861; AN-309967; AN-309973; AN-310059; AN-310132; AN-310168; AN-310238; AN-310241; AN-310301; AN-310318; AN-310324; AN-310335; AN-310338; AN-310460; AN-310500; AN-310684; AN-310690; AN-311010; AN-311022; AN-311043; AN-311125; AN-311250; AN-311370; AN-311458;

## Avisos importantes para administradores do Adobe Analytics

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Atualização para pesquisas de dispositivo devido a dicas de clientes do Google** | 25 de janeiro de 2023 | O uso de dicas do cliente na pesquisa de dispositivo será iniciado em **16 de fevereiro de 2023**. <p> <p>A partir de outubro de 2022, é possível coletar dicas do cliente com o SDK da Web ou as bibliotecas JavaScript do AppMeasurement. Mas as dicas do cliente não serão incorporadas à pesquisa de dispositivo até fevereiro de 2023. Nesse momento, o Adobe começará a usar dicas do cliente, além do Agente do usuário, ao derivar determinadas informações do dispositivo para ocorrências provenientes de navegadores Chromium, como Google Chrome e Microsoft Edge. Isso é uma resposta ao plano do Google de reduzir gradualmente as informações apresentadas pela string do usuário-agente para dar prioridade aos dados transmitidos por meio de dicas do cliente. <p> <p>Como parte dessa alteração, a Adobe usará um Device Atlas para todas as pesquisas de dispositivos relacionadas ao usuário-agente. [Saiba mais](/help/technotes/client-hints.md) |
| **Pausa de relatórios agendados no Reports &amp; Analytics** | 6 de janeiro de 2023 | O Adobe descontinuou esses recursos no **31 de janeiro de 2023**. Observe que as janelas de expiração dos relatórios e extrações de dados continuarão limitadas a nove meses; a entrega de relatórios e extrações de dados será pausada no final deste período, a menos que a programação seja reativada.<p>Antes de 31 de janeiro de 2023, era necessário migrar os relatórios agendados para um dos outros mecanismos disponíveis no Adobe Analytics. Para perguntas adicionais ou suporte, entre em contato com o Atendimento ao cliente da Adobe. [Saiba mais](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Pausa de tarefas agendadas no Report Builder** | 6 de janeiro de 2023 | Ligado **31 de janeiro de 2023**, o Adobe lançou alterações para tarefas agendadas no Report Builder como parte de nossos esforços de otimização de desempenho e delivery. Essas alterações incluíam a remoção da capacidade de programar entregas “terminadas após x ocorrências”. <p>Você pode continuar a agendar tarefas do Report Builder por hora e programar seu término após um máximo de 99 ocorrências. Observe que a reversão se aplica somente a tarefas por hora; a opção “terminar após x ocorrências” permanecerá indisponível para todos os outros intervalos de entrega (diário, semanal, mensal e anual). Para perguntas adicionais ou suporte, entre em contato com o Atendimento ao cliente da Adobe. [Saiba mais](/help/analyze/report-builder/r-arb-scheduled-reports.md) |

{style=&quot;table-layout:auto&quot;}

## Avisos de fim de vida útil

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Fim da vida útil do Data Workbench** | 14 de setembro de 2022 | Adobe pretende encerrar a vida útil do Data Workbench em **31 de dezembro de 2023**. Consulte [Anúncio do fim da vida útil do Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=pt-BR) para obter detalhes. Entre em contato com o Gerente de conta da Adobe da sua organização se tiver dúvidas. |
| **Fim da vida útil do [!DNL Reports & Analytics]** | 4 de janeiro de 2022 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o [!DNL Reports & Analytics], juntamente com os relatórios e recursos que o acompanham. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o [!DNL Reports & Analytics] não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil. |
| **Fim da vida útil do recurso de [!UICONTROL Listas de publicação]** | 29 de setembro de 2022 | Como parte do fim da vida útil do Reports &amp; Analytics, as listas de publicação estão programadas para serem descontinuadas em **dezembro de 2023**. Você não poderá criar novas listas de publicação ou acessar listas de publicação existentes para enviar ou agendar projetos do Analysis Workspace. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.23.0), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).


## Recursos relacionados

* [Notas de versão anteriores para 2022](/help/release-notes/2022.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
