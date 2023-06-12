---
title: Notas de versão mais recentes do Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 0916ef4ddc2ca65f01721f4d79d7af825dcf50e3
workflow-type: tm+mt
source-wordcount: '1441'
ht-degree: 53%

---

# Notas de versão atuais do Adobe Analytics (Junho de 2023)

**Última atualização**: 1 de junho de 2023

As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Destaques da versão {#highlights}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Compartilhamento de links para projetos (sem necessidade de logon)** | Agora você pode compartilhar links de somente leitura para projetos do Analysis Workspace com pessoas que não têm acesso ao Adobe Analytics. Isso inclui o compartilhamento com pessoas de fora da organização, ou com aquelas de dentro da organização que não estejam provisionadas para o Adobe Analytics. [Saiba mais](../analyze/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required)<p>Essa funcionalidade está habilitada por padrão e pode ser desativada pelo administrador do sistema. [Saiba mais](../analyze/analysis-workspace/user-preferences.md#company-preferences)</p> | 3 de maio de 2023 | 7 de junho de 2023 |
| **Novos recursos para conjuntos de classificação** | [Conjuntos de classificações](/help/components/classifications/sets/overview.md) O foi atualizado com vários novos recursos:<ul><li>**Consolidações**: combine conjuntos de classificações em um único conjunto de classificações consolidadas. O conjunto de classificações consolidado pode ser usado como outros conjuntos de classificações ou como um conjunto de dados de pesquisa no CJA. [Saiba mais](../components/classifications/sets/consolidations/manage.md)</li><li>**Regras**: classifica automaticamente os valores com base nas regras no conjunto de classificação. [Saiba mais](../components/classifications/sets/manage/rules.md)</li><li>**Importação automatizada**: importe automaticamente dados de classificação de destinos de armazenamento na nuvem. [Saiba mais](../components/classifications/sets/manage/schema.md)</li></ul> | | 7 de junho de 2023 |
| **Nova variável do AppMeasurement** | A variável `doubleEncodeLinkParameters` O acomoda casos de borda em que as implementações codificam caracteres de vários bytes em variáveis de rastreamento de link. A maioria das implementações não precisa definir essa variável. [Saiba mais](../implement/vars/config-vars/doubleencodelinkparameters.md) |  | 7 de junho de 2023 |
| **Destinos seguros para exportação de feed de dados** | Os feeds de dados agora podem ser enviados para os seguintes destinos de armazenamento na nuvem:<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>Os destinos que estavam disponíveis anteriormente (FTP, SFTP, S3 e Blob do Azure) não são mais recomendados. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=pt-BR) | 12 de junho de 2023 | 15 de julho de 2023 |
| **Relatórios de bot no Workspace** | Os relatórios de bot agora estão disponíveis no Analysis Workspace. Este recurso vem com várias adições:<ul><li>Uma nova dimensão: [Nome do bot](/help/components/dimensions/bot-name.md)</li><li>Duas novas métricas: [Exibições de página de bot](/help/components/metrics/bot-page-views.md) e [Ocorrências de bot](/help/components/metrics/bot-occurrences.md).</li><li>Um novo modelo de métrica calculada: [Taxa de visualizações da página de bot](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)</li><li>Um novo relatório do Workspace: Relatórios de bot</li></ul>A nova dimensão e métrica contêm dados que são preenchidos retroativamente a partir de março de 2023. |  | Junho de 7,2023 |

{style="table-layout:auto"}

## Outros recursos novos ou atualizados {#other}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Excluir linhas que contenham dimensões dinâmicas de uma Tabela de forma livre** | Em uma Tabela de forma livre no Analysis Workspace, agora é possível excluir rapidamente linhas específicas que contenham dimensões dinâmicas usando o ícone x. Ao fazer isso, uma regra de filtro &quot;Sempre excluir itens&quot; é aplicada automaticamente.<p>Anteriormente, a única maneira de excluir linhas que continham dimensões dinâmicas era criar manualmente uma regra na caixa de diálogo Filtro. [Saiba mais](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | N/D | 17 de maio de 2023 |
| **Novo botão para adicionar uma visualização dentro de um painel** | Um novo botão agora está disponível na parte inferior de cada painel no Analysis Workspace, permitindo que você adicione uma visualização rapidamente. <p>Anteriormente, os únicos métodos para adicionar uma visualização a um painel eram arrastar uma visualização do painel esquerdo, duplicar ou copiar uma visualização já existente ou criar um painel em branco. [Saiba mais](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | N/D | 17 de maio de 2023 |
| **Deep Linking (aplicativo para dispositivos móveis)** | Permite que usuários enviem links para cartões de pontuação que os levarão diretamente ao projeto do cartão de pontuação no aplicativo. Isso facilita ainda mais o compartilhamento de projetos e aumenta o engajamento de um público menos técnico. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#share-scorecards-using-a-shareable-link) | N/D | 17 de maio de 2023 |
| **Filtros suspensos dinâmicos** | Estamos introduzindo um novo tipo de filtro suspenso que determina os valores disponíveis com base nos dados no intervalo de relatórios do painel e nos valores em outros filtros suspensos. Você pode usar filtros suspensos dinâmicos arrastando uma dimensão para a área suspensa do painel enquanto mantém pressionada [!UICONTROL Shift]. Os filtros suspensos estáticos permanecem inalterados ao arrastar um grupo de itens de dimensão para a área suspensa do painel enquanto mantêm [!UICONTROL Shift]. [Saiba mais](/help/analyze/analysis-workspace/c-panels/panels.md) |  | 14 de junho de 2023 |
| **Atualização da página de aprendizado do Analytics** | A guia Aprendizado na página de aterrissagem do Adobe Analytics agora contém as seguintes melhorias:<ul><li>Design aprimorado que mostra mais conteúdo de aprendizagem em uma única página com navegação aprimorada</li><li>Capacidade de personalizar o conteúdo de aprendizado por nível de experiência (iniciante, intermediário e avançado)</li></ul>[Saiba mais](/help/analyze/landing.md) |  | Junho de 30,2023 |
| **Classificar componentes no Analysis Workspace** | Uma nova opção Classificar está disponível ao visualizar componentes no painel esquerdo ou no Dicionário de dados no Analysis Workspace. É possível classificar componentes por Recomendado (os mais usados), Alfabético ou Categórico (tipo).<p>Anteriormente, só era possível pesquisar ou filtrar componentes. [Saiba mais](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)</p> | N/D | TBD |

{style="table-layout:auto"}

## Correções no Adobe Analytics

-311878; -313968; AN-314130; AN-315701; AN-315761; AN-316613; AN-317563; AN-318829; AN-319009; AN-319043; AN-319066; AN-; AN-; AN-319166; AN-319245; AN-319271; AN-319381; AN-319391; AN-319482; AN-319621; AN-319637; AN-319676; AN-320176; AN-320221; AN-320225; AN-320286; AN-320312; AN-320316; AN-320449; AN-320477; AN-320492; AN-320538; AN-320556; AN-320569; AN-320679; AN-320684; AN-320786; AN-320802; AN-320811; AN-320812; AN-320815; AN-321032; AN-321033; AN-321070; AN-321096; AN-321105; AN-321122; AN-321337;

## Avisos importantes para administradores do Adobe Analytics {#admin}

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Expiração de 37 meses de IDs de compra e IDs de evento (serialização de eventos)** | Maio de 25,2023 | Uma versão futura do mecanismo de processamento de ocorrências do Analytics, direcionada para lançamento em **final de junho de 2023 ou início de julho de 2023**, começará a impor uma expiração de 37 meses de IDs de compra e IDs de evento (serialização de eventos). Atualmente, as IDs de compra e as IDs de evento nunca expiram no Adobe Analytics. Depois que uma ID de compra ou ID de evento for vista/usada, qualquer ocorrência futura, independentemente de quando, terá essa compra ou evento marcado como duplicado. Com a nova versão do mecanismo de processamento:<ul><li>IDs de compra e IDs de evento sempre expiram após 37 meses.</li><li>Se tiver passado 37 meses desde que a ID de compra ou a ID de evento foi vista, ela não será mais considerada uma compra ou um evento duplicado.</li><li> Se você estiver &quot;reutilizando&quot; IDs de compra ou IDs de evento de mais de 37 meses atrás, elas não serão mais consideradas duplicatas.</li></ul> |
| **Migração para credenciais de servidor para servidor do OAuth do Adobe I/O** | 11 de maio de 2023 | Os clientes da API Adobe Analytics e do Livestream que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor do Adobe I/O OAuth ao **1 de janeiro de 2025**. Para obter mais detalhes e linhas do tempo, consulte o aviso de fim de vida útil na tabela abaixo. |
| **Novos IPs usados pelos Feeds de dados do Adobe Analytics e saída do Data Warehouse no Data Center de Londres** | 27 de abril de 2023 | Isso se refere aos clientes no data center de Londres que têm solicitações de feed de dados e/ou relatórios de Data Warehouse sendo entregues a um serviço FTP/SFTP. Os seguintes intervalos de endereço IP devem ser adicionados à configuração do firewall para permitir o acesso: <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |

{style="table-layout:auto"}

## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Migração para credenciais de servidor para servidor do OAuth do Adobe I/O** | 11 de maio de 2023 | Os clientes da API Adobe Analytics e do Livestream que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor do Adobe I/O OAuth ao **1 de janeiro de 2025**. O Adobe I/O não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam o JWT devem criar uma nova credencial OAuth de servidor para servidor ou migrar sua credencial JWT existente para uma credencial OAuth de servidor para servidor. Os clientes também devem atualizar seus aplicativos clientes para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Usar as novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Fim da vida útil do [!DNL Reports & Analytics]** | 7 de março de 2023 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o [!DNL Reports & Analytics], juntamente com os relatórios e recursos que o acompanham. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o [!DNL Reports & Analytics] não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil.<p>Em 31 de dezembro de 2023, encerraremos muitos dos recursos associados do Reports &amp; Analytics, incluindo, entre outros: Relatórios agendados, Extrações de dados e Relatórios DL. Após 31 de dezembro de 2023, os relatórios agendados não serão mais enviados. Em **abril de 2023**, todos os relatórios agendados para expirar após o dia 31 de dezembro de 2023 serão atualizados e revertidos automaticamente para expirar no dia 31 de dezembro de 2023. Além disso, não será mais possível agendar relatórios para depois de 31 de dezembro de 2023. |
| **Fim da vida útil do recurso de [!UICONTROL Listas de publicação]** | 29 de setembro de 2022 | Como parte do fim da vida útil do Reports &amp; Analytics, as [!UICONTROL Listas de publicação] estão programadas para serem descontinuadas em **dezembro de 2023**. Você não poderá criar novas nem acessar [!UICONTROL Listas de publicação] já existentes para enviar ou agendar projetos do [!UICONTROL Analysis Workspace]. |
| **Fim da vida útil do Data Workbench** | 14 de setembro de 2022 | Adobe pretende encerrar a vida útil do Data Workbench em **31 de dezembro de 2023**. Consulte [Anúncio do fim da vida útil do Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=pt-BR) para obter detalhes. Entre em contato com o Gerente de conta da Adobe da sua organização se tiver dúvidas. |

{style="table-layout:auto"}

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.23.0), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).


## Recursos relacionados

* [Notas de versão anteriores para 2022](/help/release-notes/2022.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
