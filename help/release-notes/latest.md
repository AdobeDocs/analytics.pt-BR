---
title: Notas de versão mais recentes do Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 1e8aa373bcb2714c6b2c7605e1ea7c7c462b89e7
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 45%

---

# Notas de versão atuais do Adobe Analytics (março de 2022)

**Última atualização: 12 de abril de 2022**

* Para as notas de versão de fevereiro de 2022, acesse [here](/help/release-notes/2022.md).
* Para obter as notas de versão do Customer Journey Analytics, acesse [here](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* Para obter as notas de versão do Media Analytics, acesse [here](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=en)
* Saiba mais sobre as atualizações de versão mais recentes para [produtos Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html). Obtenha a documentação de autoajuda, os tutoriais e os cursos mais recentes da Experience League.

## Novos recursos no Adobe Analytics {#aa-features}

| Recurso | Descrição | [Data Alvo](releases.md) |
| ----------- | ---------- | ------- |
| Anotações no Workspace | As anotações no Workspace permitem que você comunique com eficácia nuances de dados contextuais e insights à sua organização. [Saiba mais](/help/analyze/analysis-workspace/components/annotations/overview.md) | A implantação gradual começa em 23 de março de 2022. Disponibilidade geral: 11 de abril de 2022 |
| Atualizações da página de aterrissagem do Adobe Analytics | Atualizações na página de aterrissagem conjunta do Workspace/Reports &amp; Analytics que melhora a usabilidade e a facilidade de navegação. [Saiba mais](/help/analyze/landing.md) | 20 de abril de 2022 |
| [!UICONTROL Próximo item] ou [!UICONTROL Item anterior] Painel Área de trabalho | O [!UICONTROL Item seguinte ou anterior] permite explorar itens que seguem ou precedem um item de dimensão de sua escolha. Por exemplo, use-o se desejar visualizar as páginas anteriores ou seguintes de uma página de produto específica, de um canal de marketing ou até mesmo de um tipo de dispositivo. Esse painel vai além dos próximos relatórios/relatórios anteriores, pois permite que você veja qualquer dimensão e não requer nenhuma nova implementação para obter insights. | 20 de abril de 2022 |
| [!UICONTROL Resumo da página] Painel Área de trabalho | O [!UICONTROL Resumo da página] O painel fornece uma análise detalhada para uma página de sua escolha. Ela fornece os mesmos detalhes que os Relatórios e análises herdados [!UICONTROL Resumo da página] , mais muito mais. | 20 de abril de 2022 |

{style=&quot;table-layout:auto&quot;}

## Correções no Adobe Analytics

* Correção de um problema que resultava em erro ao tentar acessar o Activity Map. (AN-267177)
* Correção de um problema com transferências de ativos do usuário malsucedidas. (AN-279813)
* Correção de problemas com o painel Espaço de trabalho A4T . (AN-281594; AN-282418)
* Correção de um problema em que alguns usuários não conseguiam acessar o Adobe Analytics. (AN-282776)
* Correção de problemas com alguns conjuntos de relatórios recém-criados que não coletavam dados. (AN-283114, AN-283311)
* Correção de problemas com emails de Feeds de dados enviados incorretamente. (AN-280255; AN-282051)

### Outras correções no Adobe Analytics

AN-256929; AN-270937; AN-272158; AN-275130; AN-277830; AN-278635; AN-279066; AN-279683; AN-279899; AN-280504; AN-280617; AN-280663; AN-281423; AN-281523; AN-281608; AN-281671; AN-281963; AN-282027; AN-282218; AN-282593; AN-282605; AN-282632; AN-282654; AN-282694; AN-282744; AN-282756; AN-282804; AN-282838; AN-282862; AN-282903; AN-282937; AN-282892; AN-283315; AN-283338; AN-283388; AN-283417; AN-283474; AN-283511; AN-283691, AN-283895; AN-283943; AN-283957; AN-284030; AN-284100; AN-284142; AN-284162

## Avisos importantes para administradores do Adobe Analytics

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| Alteração na maneira como o Analytics lida com dados A4T coletados pelo Experience Edge | 31 de março de 2022 | Ligado **7 de março de 2022**, alteramos a forma como lidamos com algumas chamadas provenientes do Experience Edge que incluem conteúdo Target destinado aos relatórios do Analytics for Target (A4T). A partir de 7 de março, todas as ocorrências com conteúdo de relatório A4T foram modificadas para não serem tratadas como Exibição de página ou Eventos de link. **A partir de 31 de março de 2022**, alteramos nossa lógica para ser mais seletiva para que os eventos padrão de Exibição de página e Clique não sejam modificados. A partir de agora, os únicos eventos que serão modificados serão chamadas somente de personalização com conteúdo A4T. |
| Atualização de métodos de criptografia de navegador compatíveis com determinados clientes | 28 de março de 2022 | O Adobe oferece dois níveis de segurança de criptografia para atender às diversas necessidades de segurança do cliente na coleta de dados primários. Ligado **23 de junho de 2022** removeremos o suporte para determinados algoritmos de criptografia HTTPS, conhecidos como cifras, para clientes com seu nível de segurança definido como &quot;Alto&quot;. Isso significa que alguns sistemas operacionais mais antigos não poderão mais enviar dados para o Analytics porque eles não suportam métodos de criptografia modernos. Os clientes que usam as configurações padrão de segurança de criptografia &quot;Padrão&quot; não serão afetados. Todos os clientes que atualmente usam a configuração &quot;Alto&quot; já foram contatados diretamente. Uma lista detalhada das cifras afetadas por essa alteração pode ser encontrada [here](/help/technotes/rdc/encryption-algos.md). |
| Pausando relatórios agendados mais antigos | 12 de abril de 2022 | Efetivo **21 de abril de 2022**, o Adobe pretende pausar todos os relatórios agendados com uma data de criação superior a dois anos (criados antes de 31 de janeiro de 2020). Nenhum relatório ou dado será excluído. Somente os relatórios identificados como com mais de dois anos serão pausados e nenhum relatório agendado adicional será enviado. Qualquer relatório com uma data de criação inferior a dois anos sem data de expiração (ou com uma data de expiração superior a dois anos) terá uma data de expiração padrão de 9 meses aplicada. [Saiba mais](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| Atualizações da região ISO 2022 | 11 de março de 2021 | O Adobe executará atualizações de 2022 da região ISO em **10 de junho de 2022**. Espera-se ver pequenas atualizações de informações geográficas após esta versão. |
| Pausa de tarefas agendadas mais antigas do Report Builder | 12 de abril de 2022 | **A partir de 21 de abril de 2022**, a Adobe pretende pausar todas as tarefas agendadas do Report Builder que foram criadas há mais de dois anos. Essa pausa se aplica especificamente a qualquer tarefa criada antes de 31 de janeiro de 2020. Nenhuma tarefa, pasta de trabalho ou dados serão excluídos. No entanto, as tarefas identificadas com mais de dois anos serão pausadas e nenhuma tarefa agendada adicional será enviada. [Saiba mais](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| Expiração de lista de permissões de extensão EOL para integrações OAuth/JWT herdadas do Analytics | 14 de janeiro de 2022 | Em **25 de maio de 2022**, a [API do Analytics 1.3, a API SOAP 1.4 e a extensão de lista de permissões do Analytics OAuth/JWT EOL](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md) herdado irá expirar. Ela era fornecida para que os clientes que usavam credenciais herdadas do [!DNL Adobe Analytics] OAuth/JWT tivessem mais tempo para migrar suas integrações de clientes para as [credenciais do Adobe IMS](https://developer.adobe.com/console). Essa expiração afeta (mas não se limita a) [!DNL Adobe Analytics Livestream] e [!DNL Adobe Campaign] clientes que não concluíram as migrações de IMS necessárias. Atualmente, os clientes que estão usando as [!DNL Analytics] credenciais OAuth/JWT herdadas por meio da extensão da lista de permissões e que não concluírem a migração para credenciais do IMS até o dia 25 de maio de 2022, perderão o acesso aos serviços da Adobe. Os clientes do Livestream podem se referir a essas [instruções](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) ao migrar seus aplicativos de clientes para as credenciais IMS. [!DNL Campaign] os clientes podem entrar em contato com a equipe da conta da Adobe para saber como atualizar para a versão mais recente do [!DNL Campaign]. |
| Atualização de serviços do Protocolo de transferência segura de arquivo (SFTP) | 3 de março de 2022 | Em **15 de maio de 2022**, o [!DNL Adobe Analytics] atualizará os seus serviços de Protocolo de transferência segura de arquivo (SFTP) para oferecer maior segurança às transferências de arquivos. Com essa alteração, não haverá mais suporte para algumas configurações de cliente SFTP. Também adicionaremos algumas opções de conexão que estarão disponíveis em **1 de março de 2022**. Isso afetará somente os dados enviados para o Adobe Analytics ou recuperados dele por meio do SFTP. O protocolo FTP não é afetado. Para evitar interrupções do serviço, verifique se os clientes SFTP (código, ferramentas, serviços) estarão de acordo com as alterações detalhadas [aqui](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=pt-BR). |
| Fim da vida útil do [!DNL Reports & Analytics] | 4 de janeiro de 2022 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o [!DNL Reports & Analytics], juntamente com os relatórios e recursos que o acompanham. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o [!DNL Reports & Analytics] não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement {#appm}

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.22.4), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] notas de versão](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=en)
