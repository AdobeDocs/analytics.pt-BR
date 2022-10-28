---
title: Notas de versão mais recentes do Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 96488440c73acfdc015560012de5481368baed8a
workflow-type: tm+mt
source-wordcount: '1425'
ht-degree: 94%

---

# Notas de versão atuais do Adobe Analytics (outubro/novembro de 2022)

**Última atualização**: 25 de outubro de 2022

As versões do Adobe Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados no Adobe Analytics

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| Visualização do **[!UICONTROL Resumo da métrica principal]** | A visualização do [!UICONTROL Resumo da métrica principal] permite ver a tendência de uma métrica importante em um único período. Ela também permite comparar o desempenho da métrica em dois intervalos de tempo. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/key-metric.html?lang=pt-BR) | 5 de outubro de 2022 | 19 de outubro de 2023 |
| **Variáveis multivalores que não diferenciam maiúsculas de minúsculas** | Para variáveis multivalores que não diferenciam maiúsculas de minúsculas, os valores são armazenados em `mvvar1` - `mvvar3` nos feeds de dados não serão mais convertidos em minúsculas automaticamente. Em vez disso, os feeds de dados (e os dados transmitidos pelo Conector de origem do Analytics para a Adobe Experience Platform e CJA) refletirão a caixa original transmitida pela página. | N/D | 24 de outubro de 2022 |

{style=&quot;table-layout:auto&quot;}

## Correções no Adobe Analytics

* Correção de um problema em que versões recentes do MacOS eram nomeadas incorretamente como &quot;Macintosh&quot;. Com essa correção, a dimensão Sistema operacional começará a usar a numeração de versão &quot;MacOS&quot;, a partir do MacOS 11. (AN-301834)
* Correção de um problema com o intervalo de datas &quot;datas fixas&quot; no Report Builder. (AN-303684)
* Correção de problemas em que a interface do usuário do Feed de dados não carregava. (AN-303803, AN-303784)

### Outras correções

-295574; AN-296354; AN-297143; AN-299501; AN-301755; AN-302054; AN-302304; AN-302631; AN-302811; AN-303090; AN-303372; AN-; AN-303428; AN-303429; AN-303432; AN-303434; AN-303437; AN-303438; AN-303519; AN-303610; AN-303656; AN-303659; AN-303663; AN-303664; AN-303818; AN-303823; AN-303837; AN-304036; AN-304195; AN-304321; AN-304325; AN-304339; AN-304356; AN-304435; AN-304457; AN-304509; AN-304519; AN-304534

## Avisos importantes para administradores do Adobe Analytics

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Atualização para pesquisas de dispositivo devido a dicas de clientes do Google** | 14 de outubro de 2022 | O uso de dicas do cliente na pesquisa de dispositivo, originalmente planejado para 26 de outubro de 2022, foi adiado para **janeiro de 2023**. <p> <p>A partir de outubro de 2022, é possível coletar dicas do cliente com o SDK da Web ou com as bibliotecas JavaScript do AppMeasurement. Mas as dicas do cliente não serão incorporadas à pesquisa de dispositivo até janeiro de 2023. Nessa data, a Adobe começará a usar dicas de clientes, além do usuário-agente, ao obter determinadas informações do dispositivo para ocorrências provenientes de navegadores Chromium, como Google Chrome e Microsoft Edge. Isso é uma resposta ao plano do Google de reduzir gradualmente as informações apresentadas pela string do usuário-agente para dar prioridade aos dados transmitidos por meio de dicas do cliente. <p> <p>Como parte dessa alteração, a Adobe usará um Device Atlas para todas as pesquisas de dispositivos relacionadas ao usuário-agente. [Saiba mais](/help/technotes/client-hints.md) |
| **Página de destino padrão** | 29 de setembro de 2022 | A [nova página de destino](/help/analyze/landing.md) que foi introduzida no início deste ano se tornará a experiência padrão para todos os usuários em **janeiro de 2023**. A página atual será descontinuada e todos precisarão usar a nova experiência. |
| Condições de execução automática da **[!UICONTROL Detecção de anomalias]** | 29 de setembro de 2022 | Atualmente, a [!UICONTROL detecção de anomalias] é executada automaticamente em todas as colunas das tabelas de forma livre de série de tempo. Para garantir que os dados estejam disponíveis para análise e que os projetos sejam carregados mais rapidamente, a Adobe alterará a forma como a detecção de anomalias é executada automaticamente. A partir de **26 de outubro de 2022**, a [!UICONTROL detecção de anomalias] será executada automaticamente somente na primeira coluna de métrica de uma tabela. Se necessário, é possível configurar a coluna para executar a detecção de anomalias em outras colunas. |
| **Atualização para o novo banco de dados da operadora NetAcuity** | 26 de setembro de 2022 | Esta atualização, originalmente planejada para 5 de outubro de 2022, foi adiada para **janeiro de 2023**. As informações sobre a operadora armazenadas no campo `carrier` do Data Warehouse e dos feeds de dados do Adobe Analytics serão alteradas. Historicamente, o formato dos dados nessa coluna foi `<domain>:<ISP>`. A Adobe manteve uma tabela de pesquisa interna para mapear esses valores `<domain>:<ISP>` em nomes de operadoras para fins de relatório nas ferramentas de relatório do Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, API de relatórios, Data Warehouse, LiveStream etc.). O arquivo de pesquisa (`carrier.tsv`) também é fornecido com feeds de dados para que você possa usar os mesmos mapeamentos.<p>Essa atualização melhora nossos mapeamentos de operadora ao usar um banco de dados de operadora mais preciso da NetAcuity. O formato dos dados na coluna da operadora nos feeds de dados será alterado a partir de agora. Em vez de `<domain>:<ISP>`, ele conterá um nome de operadora. A Adobe continuará a usar a tabela de pesquisa para manter a maior continuidade possível com os relatórios anteriores. As ferramentas de relatórios nas quais as pesquisas são aplicadas pela Adobe (Analysis Workspace, Reports &amp; Analytics, API de relatórios, Data Warehouse, LiveStream etc.) se beneficiarão de mapeamentos mais precisos. Alguns mapeamentos — especialmente os de domínios internacionais e ISPs — mudarão mais do que outros quando adotarmos o novo banco de dados. O arquivo de pesquisa da operadora dos feeds de dados (`carrier.tsv`) manterá os mapeamentos antigos e adicionará os novos mapeamentos.<p>No momento, o conector de origem do Analytics não mapeia o campo da operadora. Portanto, o relatório da operadora não está disponível na Experience Platform, CJA etc. Sendo assim, o uso do novo banco de dados de operadora não afetará nada na Experience Platform que seja baseada nos dados fornecidos pelo conector de origem do Analytics. |
| **Melhoria no mapeamento de IP para geolocalização** | 26 de setembro de 2022 | Nosso fornecedor de pesquisas de IP, Digital Element, está atualizando para um novo conjunto de dados aprimorado (NetAcuity Pulse) de mapeamento de IP para geolocalização. Planejado originalmente para outubro de 2022, o Adobe Analytics adotará esse novo conjunto de dados em **janeiro de 2023**. O novo banco de dados será mais preciso que as versões anteriores. Alguns mapeamentos de IP para geolocalização serão alterados/melhorados quando o novo banco de dados for adotado.<p>Todas as ferramentas do Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, API de relatórios, Data Warehouse, LiveStream, feeds de dados etc.) aproveitarão automaticamente os novos mapeamentos aprimorados. Não haverá alteração no formato dos dados nos feeds de dados. Os dados do CJA fornecidos por meio do conector de origem do Analytics também aproveitarão automaticamente os novos mapeamentos. |
| **Pausa de relatórios agendados no Reports &amp; Analytics** | 8 de junho de 2022 | Em 21 de abril de 2022, anunciamos a desativação de vários recursos específicos dos relatórios agendados como preparação para o fim da vida útil do Reports &amp; Analytics anunciado anteriormente. Esses recursos incluíam a capacidade de agendar novos relatórios, bem como novas extrações de dados.<p>Em resposta às solicitações de clientes que buscam uma extensão e para facilitar a transição do Reports &amp; Analytics, decidimos estender o acesso a esses recursos até **31 de janeiro de 2023**. Observe que as janelas de expiração dos relatórios e extrações de dados continuarão limitadas a nove meses; a entrega de relatórios e extrações de dados será pausada no final deste período, a menos que a programação seja reativada.<p>Em outras palavras, esses recursos serão descontinuados em 31 de janeiro de 2023. Antes dessa data, você deve migrar seus relatórios agendados para um dos outros mecanismos disponíveis no Adobe Analytics. Para perguntas adicionais ou suporte, entre em contato com o Atendimento ao cliente da Adobe. [Saiba mais](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Pausa de tarefas agendadas no Report Builder** | 8 de junho de 2022 | Em 21 de abril de 2022, lançamos alterações em tarefas agendadas do Report Builder como parte de nossos esforços de otimização de desempenho e entrega. Essas alterações incluíam a remoção da capacidade de programar entregas “terminadas após x ocorrências”. Em resposta a várias solicitações de clientes que buscam mais tempo para explorar e implementar alternativas, decidimos restaurar essa opção de maneira limitada até **31 de janeiro de 2023**.<p>Você pode continuar a agendar tarefas do Report Builder por hora e programar seu término após um máximo de 99 ocorrências. Observe que a reversão se aplica somente a tarefas por hora; a opção “terminar após x ocorrências” permanecerá indisponível para todos os outros intervalos de entrega (diário, semanal, mensal e anual). Observe que essa opção será desativada em 31 de janeiro de 2023. Para perguntas adicionais ou suporte, entre em contato com o Atendimento ao cliente da Adobe. [Saiba mais](/help/analyze/report-builder/r-arb-scheduled-reports.md) |

{style=&quot;table-layout:auto&quot;}

## Avisos de fim de vida útil

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Fim da vida útil do recurso de [!UICONTROL Listas de publicação]** | 29 de setembro de 2022 | Como parte do fim da vida útil do Reports &amp; Analytics, as listas de publicação estão programadas para serem descontinuadas em **dezembro de 2023**. Você não poderá criar novas listas de publicação ou acessar listas de publicação existentes para enviar ou agendar projetos do Analysis Workspace. [Saiba mais](/help/admin/admin/publishing-list.md) |
| **Fim da vida útil do Data Workbench** | 14 de setembro de 2022 | Adobe pretende encerrar a vida útil do Data Workbench em **31 de dezembro de 2023**. Consulte [Anúncio do fim da vida útil da Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=pt-BR) para obter detalhes. Entre em contato com o Gerente de conta do Adobe de de sua organização se tiver dúvidas. |
| **Fim da vida útil do [!DNL Reports & Analytics]** | 4 de janeiro de 2022 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o [!DNL Reports & Analytics], juntamente com os relatórios e recursos que o acompanham. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o [!DNL Reports & Analytics] não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.23.0), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).

## Recursos relacionados

* [Notas de versão anteriores para 2022](/help/release-notes/2022.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)
