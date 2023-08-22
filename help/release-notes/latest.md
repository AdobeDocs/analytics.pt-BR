---
title: Notas de versão atuais do Adobe Analytics
description: Exibir as notas de versão atuais do Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 00fd63b7486382da5506d16540bb949c52541c6d
workflow-type: ht
source-wordcount: '895'
ht-degree: 100%

---

# Notas de versão atuais do Adobe Analytics (Agosto de 2023)

**Última atualização**: 9 de agosto de 2023

Essas notas de versão abrangem o período de lançamento de 9 de agosto a 13 de setembro de 2023. As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Novos recursos ou melhorias {#features}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Conjuntos de classificação na API 2.0** | Fornece métodos da API 2.0 do Adobe Analytics para salvar, excluir, recuperar, importar e exportar dados do conjunto de classificações. | N/D | 31 de agosto de 2023 |
| **Gerenciador de atividades de relatórios** | O Gerenciador de atividades de relatórios fornece aos administradores visibilidade detalhada do consumo de relatórios para cada conjunto de relatórios, permitindo que os administradores diagnostiquem e corrijam problemas de capacidade facilmente durante os horários de pico de relatórios. [Saiba mais](/help/admin/admin/reporting-activity.md) | N/D | 6 de setembro de 2023 |

{style="table-layout:auto"}

## Correções no Adobe Analytics

* Correção de um problema em que os eventos personalizados não eram carregados. (AN-324163)
* Correção de um problema que impedia a edição de rótulos para as legendas em uma visualização. (AN-323246)

AN-315605; AN-316306; AN-317494; AN-317844; AN-320424; AN-320597; AN-320680; AN-320869; AN-321624; AN-321693; AN-322009; AN-322244; AN-322380; AN-322432; AN-322466; AN-322556; AN-322669; AN-322735; AN-323151; AN-323220; AN-323380; AN-323492; AN-323595; AN-323755; AN-323854; AN-323916; AN-324044; AN-324200; AN-324213; AN-324238; AN-324347; AN-323598; AN-323625; AN-323631; AN-323638; AN-323641; AN-323755; AN-323767; AN-323777; AN-323825; AN-323846; AN-323972; AN-324113; AN-324170; AN-324197; AN-324273; AN-324275; AN-324345; AN-324384; AN-324433; AN-324511; AN-324513; AN-324521; AN-324524; AN-324531; AN-324532; AN-324534; AN-324537; AN-324569; AN-324618; AN-324635; AN-324688; AN-324704; AN-324712; AN-324721; AN-324745; AN-324792; AN-324793; AN-324794; AN-324795; AN-324824; AN-324905; AN-324918; AN-324932; AN-324934; AN-324947; AN-325003; AN-325073; AN-325143; AN-325148; AN-325153; AN-325177; AN-325187; AN-325252; AN-325305; AN-325363; AN-325401; AN-325439; AN-325431; AN-325491; AN-325495; AN-325508; AN-325594; AN-325601; AN-325660; AN-325779; AN-325857; AN-325883; AN-325885; AN-325886


## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Expiração de 37 meses de IDs de compra e IDs de evento (serialização de eventos)** | 10 de julho de 2023 | Uma versão futura do mecanismo de processamento de ocorrências do Analytics, com lançamento previsto para **13 de julho de 2023**, começará a impor uma expiração de 37 meses para IDs de compra e IDs de evento (serialização de eventos). Atualmente, as IDs de compra e as IDs de evento nunca expiram no Adobe Analytics. Depois que uma ID de compra ou ID de evento for vista/usada, qualquer ocorrência futura, independente de quando, terá essa compra ou evento marcado como duplicado. Com a nova versão do mecanismo de processamento:<ul><li>IDs de compra e IDs de evento sempre expirarão após 37 meses.</li><li>Se tiver passado 37 meses desde que a ID de compra ou a ID de evento foi vista, ela não será mais considerada uma compra ou um evento duplicado.</li><li> Se você estiver “reutilizando” IDs de compra ou IDs de evento de mais de 37 meses atrás, elas não serão mais consideradas duplicatas.</li></ul> |
| **Migração para credenciais de servidor para servidor OAuth do Adobe I/O** | 11 de maio de 2023 | Os clientes da API e da transmissão ao vivo do Adobe Analytics que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor OAuth do Adobe I/O até o dia **1º de janeiro de 2025**. Para mais detalhes e linhas do tempo, consulte o aviso de fim de vida útil na tabela abaixo. |

{style="table-layout:auto"}

## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Migração para as credenciais de servidor para servidor do Adobe I/O OAuth** | 11 de maio de 2023 | Os clientes da API e da transmissão ao vivo do Adobe Analytics que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor OAuth do Adobe I/O até o dia **1º de janeiro de 2025**. O AdobeIO não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guia de implementação para aplicativos novos e antigos com o OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Fim da vida útil do [!DNL Reports & Analytics]** | 7 de março de 2023 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o [!DNL Reports & Analytics], juntamente com os relatórios e recursos que o acompanham. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o [!DNL Reports & Analytics] não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil.<p>Em 31 de dezembro de 2023, encerraremos muitos dos recursos associados do Reports &amp; Analytics, incluindo, entre outros: Relatórios agendados, Extrações de dados e Relatórios DL. Após 31 de dezembro de 2023, os relatórios agendados não serão mais enviados. Em **abril de 2023**, todos os relatórios agendados para expirar após o dia 31 de dezembro de 2023 serão atualizados e revertidos automaticamente para expirar no dia 31 de dezembro de 2023. Além disso, não será mais possível agendar relatórios para depois de 31 de dezembro de 2023. |
| **Fim da vida útil do recurso de [!UICONTROL Listas de publicação]** | 29 de setembro de 2022 | Como parte do fim da vida útil do Reports &amp; Analytics, as [!UICONTROL Listas de publicação] estão programadas para serem descontinuadas em **dezembro de 2023**. Você não poderá criar novas nem acessar [!UICONTROL Listas de publicação] já existentes para enviar ou agendar projetos do [!UICONTROL Analysis Workspace]. |
| **Fim da vida útil do Data Workbench** | 14 de setembro de 2022 | Adobe pretende encerrar a vida útil do Data Workbench em **31 de dezembro de 2023**. Consulte [Anúncio do fim da vida útil do Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=pt-BR) para obter detalhes. Entre em contato com o Gerente de conta da Adobe da sua organização se tiver dúvidas. |

{style="table-layout:auto"}

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.24.0), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).


## Recursos relacionados

* [Notas de versão anteriores para 2022](/help/release-notes/2022.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
