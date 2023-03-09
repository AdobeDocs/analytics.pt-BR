---
title: Notas de versão mais recentes do Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: c99e4f2b91d6246a2a47e39dc24ba443b76636f6
workflow-type: tm+mt
source-wordcount: '1058'
ht-degree: 56%

---

# Notas de versão atuais do Adobe Analytics (Março de 2023)

**Última atualização**: 9 de março de 2023

As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados no Adobe Analytics {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Dicionário de dados no Analysis Workspace** | O Dicionário de dados ajuda os usuários e administradores a rastrear, gerenciar e entender melhor os componentes (dimensões, métricas) em seu ambiente do Analytics. [Saiba mais](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) | 15 de março de 2023 | 22 de março de 2023 |
| **Histórias de dados em painéis móveis** | As histórias de dados permitem adicionar várias exibições de detalhes personalizáveis aos blocos nos projetos de cartões de pontuação móveis. Use histórias de dados para se aprofundar em drivers principais, métricas relacionadas e diferentes etapas ao longo da jornada do cliente. Você pode passar facilmente por essas exibições para entender toda a história por trás de suas métricas principais. [Saiba mais](/help/analyze/mobile-app/create-scorecard.md#create-data-story) | N/D | 8 de março de 2023 |
| **Datas de expiração do projeto agendado** | Você pode definir datas de expiração máximas para projetos agendados para até um ano, independentemente da frequência de agendamento. | N/D | 8 de março de 2023 |
| **Compartilhamento de link para projetos (sem logon necessário)** - Somente acesso beta privado | <p>Agora você pode compartilhar links somente leitura para projetos do Analysis Workspace com pessoas que não têm acesso ao Adobe Analytics. Você pode compartilhar links de projeto com pessoas de fora da organização ou aquelas dentro da organização que não estão provisionadas para a Adobe Analytics. [Saiba mais](/help/analyze/analysis-workspace/curate-share/share-projects.md)</p> <p>Para participar do beta privado, entre em contato com a equipe de conta do Adobe.</p> | 15 de março de 2023 (Beta privado) | Abril de 2023 |

## Correções no Adobe Analytics 

AN-308177; AN-308727; AN-308846; AN-309591; AN-310614; AN-311544; AN-311570; AN-311665; AN-311948; AN-312108; AN-312114; AN-312142; AN-312143; AN-312389; AN-312391; AN-312431; AN-312453; AN-312454; AN-312458; AN-312503; AN-312533; AN-312682; AN-312698; AN-312714; AN-312738; AN-312807; AN-312829; AN-312849; AN-312875; AN-312980; AN-312997; AN-313059; AN-313077; AN-313110; AN-313195; AN-313196; AN-313258; AN-313554; AN-313580; AN-313702; AN-313820; AN-313844; AN-313859; AN-313879; AN-314273

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição  ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Atualização para pesquisas de dispositivo devido a dicas de clientes do Google** | 27 de fevereiro de 2023 | O uso de dicas do cliente, planejado para 16 de fevereiro de 2023, foi adiado para garantir melhor a qualidade das pesquisas de dispositivo usando dicas. Continuamos com a primeira fase da versão para oferecer suporte ao Client Hints em 27 de fevereiro de 2023. A segunda e última fase do lançamento foi concluída na quinta-feira, 2 de março de 2023. [Saiba mais](/help/technotes/client-hints.md) |
| **Disponibilidade do Conector de origem do Analytics** | 15 de fevereiro de 2023 | Em 28 de fevereiro de 2023, o Conector de origem do Analytics foi disponibilizado no novo data center da Adobe Experience Platform localizado no Canadá. |
| **Migração automática para a arquitetura do Conjunto de Classificações** | 8 de fevereiro de 2023 | Nos próximos meses, a Adobe planeja migrar todas as classificações em todas as organizações para a arquitetura de classificação mais recente. Estima-se que os últimos clientes a migrar ocorram em maio de 2023. Nenhuma ação do cliente é necessária e nenhum tempo de inatividade é esperado. Essa nova arquitetura tem muitos benefícios, incluindo:<ul><li>Redução significativa do tempo de processamento (72 horas → 24 horas)</li><li>A capacidade de usar a interface [Conjuntos de Classificações](/help/components/classifications/sets/overview.md)</li><li>A opção de usar os dados de classificação na Adobe Experience Platform no futuro por meio do [Conector de origem do Adobe Analytics para dados de classificação](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)</li></ul>Observe as seguintes alterações que podem afetar potencialmente o fluxo de trabalho de sua organização:<ul><li>Ao usar o navegador ou a importação de FTP, &#39;[!UICONTROL Substituir em conflito]&#39; está sempre ativado.</li><li>Ao usar o navegador ou importação de FTP, a opção de exportar imediatamente após a importação não é mais suportada.</li><li>O endpoint`GetDimensions` da API do Analytics 2.0 agora retorna identificadores de string para classificações em vez de identificadores numéricos. Identificadores numéricos ainda podem ser usados, mas a Adobe recomenda o uso dos novos identificadores de sequência, quando possível. Os identificadores numéricos podem ser recuperados usando o parâmetro da sequência de consulta `?expansion=hidden`.</li></ul>Entre em contato com o Atendimento ao cliente da Adobe se desejar um agendamento de migração mais específico para sua organização, ou se tiver dúvidas/preocupações sobre essa migração. [Saiba mais](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Fim da vida útil do [!DNL Reports & Analytics]** | 7 de março de 2023 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o [!DNL Reports & Analytics], juntamente com os relatórios e recursos que o acompanham. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o [!DNL Reports & Analytics] não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil.<p>Em 31 de dezembro de 2023, encerraremos muitos dos recursos associados do Reports &amp; Analytics, incluindo, entre outros: Relatórios agendados, Extrações de dados e Relatórios DL. Após 31 de dezembro de 2023, os relatórios agendados não serão mais enviados. Entrada **Abril de 2023** Além disso, todos os relatórios programados para expirar além de 31 de dezembro de 2023 serão atualizados e revertidos automaticamente para expirar em 31 de dezembro de 2023. Além disso, não será mais possível agendar relatórios futuros para depois de 31 de dezembro de 2023. |
| **Fim da vida útil de [!UICONTROL Pessoas] métrica** | 9 de março de 2023 | Com a descontinuação do [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html), a métrica Pessoas relacionada ao Device Co-op não é mais relevante. Em 8 de maio de 2023, removeremos o [!UICONTROL Pessoas] métrica. Nesse ponto, redirecionaremos seus dados para o [!UICONTROL Visitante único] para impedir que projetos, segmentos e métricas calculadas sejam quebrados.<p>**Nota**: A variável [[!UICONTROL Pessoas] métrica vinculada à Análise entre dispositivos](/help/components/metrics/people.md) não é afetado por este anúncio. |
| **Fim da vida útil do recurso de [!UICONTROL Listas de publicação]** | 29 de setembro de 2022 | Como parte do fim da vida útil do Reports &amp; Analytics, [!UICONTROL Listas de publicação] estão programados para atingir o fim da vida útil em **Dezembro de 2023**. Você não poderá criar novos arquivos ou acessar arquivos existentes [!UICONTROL Listas de publicação] para enviar ou agendar [!UICONTROL Analysis Workspace] projetos. |
| **Fim da vida útil do Data Workbench** | 14 de setembro de 2022 | Adobe pretende encerrar a vida útil do Data Workbench em **31 de dezembro de 2023**. Consulte [Anúncio do fim da vida útil do Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=pt-BR) para obter detalhes. Entre em contato com o Gerente de conta da Adobe da sua organização se tiver dúvidas. |
| **Fim da vida útil do [!DNL Reports & Analytics]** | 4 de janeiro de 2022 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o [!DNL Reports & Analytics], juntamente com os relatórios e recursos que o acompanham. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o [!DNL Reports & Analytics] não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil. |

{style="table-layout:auto"}

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.23.0), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).


## Recursos relacionados

* [Notas de versão anteriores para 2022](/help/release-notes/2022.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
