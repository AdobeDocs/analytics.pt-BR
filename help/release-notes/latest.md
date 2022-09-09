---
title: Notas de versão mais recentes do Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 74c347c72394b75cc332ae459b9cbf1f72fa033b
workflow-type: tm+mt
source-wordcount: '1205'
ht-degree: 77%

---

# Notas de versão atuais do Adobe Analytics (setembro de 2022)

**Última atualização**: 9 de setembro de 2022

>[!NOTE]
>
>Esta página contém conteúdo de pré-lançamento e está sujeita a alterações.

## Recursos relacionados

* [Notas de versão anteriores para 2022](/help/release-notes/2022.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)

## Recursos novos ou atualizados no Adobe Analytics

| Recurso | Descrição | [Data Alvo](releases.md) |
| ----------- | ---------- | ------- |
| Visualização de Gráficos de combinação no Workspace | Os gráficos de combinação permitem que você compare métricas de forma mais fácil e intuitiva no Workspace. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/combo-charts.html) | 14 de setembro de 2022 |

{style=&quot;table-layout:auto&quot;}

## Correções no Adobe Analytics

* Correção de problemas com a importação e exportação de Classificações . (AN-299267)

**Correções para clientes individuais**:

AN-288519; AN-289300; AN-297387; AN-297465; AN-297520; AN-297641; AN-298134; AN-298351; AN-298429; AN-298483; AN-298520; AN-298582; AN-298816; AN-298832; AN-298855; AN-298864; AN-299407; AN-299545; AN-299644; AN-299715

## Avisos importantes para administradores do Adobe Analytics

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Atualização do SFTP** | 9 de setembro de 2022 | Anteriormente, informamos que o Adobe atualizaria seus serviços de Protocolo de transferência segura de arquivo (SFTP) em setembro de 2022 para oferecer segurança aprimorada para transferência de arquivos. Adiamos essa atualização para **meados do final de setembro de 2022**. Quando essa alteração ocorrer, determinadas configurações de cliente SFTP não serão mais compatíveis. Isso afetará somente os dados enviados para o Adobe Analytics ou recuperados dele por meio do SFTP. O protocolo FTP não é afetado. Para evitar interrupções do serviço, verifique se os clientes SFTP (código, ferramentas, serviços) estarão de acordo com as alterações detalhadas [aqui](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=pt-BR). |
| **EOL para Data Workbench** | 9 de setembro de 2022 | Adobe pretende que a Data Workbench do fim da vida seja eficaz **31 de dezembro de 2023**. Mais detalhes serão comunicados em breve. |
| **Atualização para pesquisas de dispositivo devido a dicas de clientes do Google** | 9 de setembro de 2022 | A partir de **29 de setembro de 2022**, o Adobe começará a usar dicas do cliente, além do Agente do usuário, ao derivar determinadas informações do dispositivo para ocorrências provenientes de navegadores Chromium, como Google Chrome e Microsoft Edge. Isso é uma resposta ao plano da Google de reduzir gradualmente as informações apresentadas a partir da sequência de agente do usuário, em vez dos dados passados por dicas do cliente. Leia mais sobre dicas de clientes [aqui](https://web.dev/user-agent-client-hints/).<p> Até outubro, as bibliotecas de coleção do AppMeasurement e do SDK da Web serão compatíveis com a coleta de dicas de clientes e configuração da coleta de dicas de clientes de alta entropia. Como parte dessa alteração, a Adobe usará o Device Atlas para todas as pesquisas de dispositivos relacionadas ao agente do usuário. Atualmente, o Device Atlas é usado apenas para ocorrências de dispositivos móveis. Essas atualizações podem resultar em pequenas alterações nas informações do dispositivo historicamente derivadas do agente do usuário — mais especificamente, Navegador, Tipo de navegador, Sistema operacional, Tipo de sistema operacional e Dispositivo móvel. |
| **Atualização para o novo banco de dados da operadora NetAcuity** | 9 de setembro de 2022 | **A partir de 5 de outubro de 2022**, informações relacionadas com a transportadora armazenadas no `carrier` no Adobe Analytics Data Warehouse e nos Feeds de dados do Analytics serão alterados. Historicamente, o formato dos dados nessa coluna foi `<domain>:<ISP>`. A Adobe manteve uma tabela de pesquisa interna para mapear esses valores `<domain>:<ISP>` em nomes de operadoras para fins de relatório nas ferramentas de relatório do Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, API de relatórios, Data Warehouse, LiveStream etc.). O arquivo de pesquisa (`carrier.tsv`) também é fornecido com feeds de dados para que você possa usar os mesmos mapeamentos.<p>Essa atualização melhora nossos mapeamentos de operadora ao usar um banco de dados de operadora mais preciso da NetAcuity. O formato dos dados na coluna da operadora nos feeds de dados será alterado a partir de agora. Em vez de `<domain>:<ISP>`, ele conterá um nome de operadora. A Adobe continuará a usar a tabela de pesquisa para manter a maior continuidade possível com os relatórios anteriores. As ferramentas de relatórios nas quais as pesquisas são aplicadas pela Adobe (Analysis Workspace, Reports &amp; Analytics, API de relatórios, Data Warehouse, LiveStream etc.) se beneficiarão de mapeamentos mais precisos. Alguns mapeamentos — especialmente os de domínios internacionais e ISPs — mudarão mais do que outros quando adotarmos o novo banco de dados. O arquivo de pesquisa da operadora dos feeds de dados (`carrier.tsv`) manterá os mapeamentos antigos e adicionará os novos mapeamentos.<p>No momento, o conector de origem do Analytics não mapeia o campo da operadora. Portanto, o relatório da operadora não está disponível no AEP, CJA etc. Sendo assim, o uso do novo banco de dados de operadora não afetará nada no AEP que seja baseado nos dados fornecidos pelo conector de origem do Analytics. |
| **Melhoria no mapeamento de IP para geolocalização** | 9 de setembro de 2022 | Nosso fornecedor de pesquisas de IP, Digital Element, está atualizando para um novo conjunto de dados aprimorado (NetAcuity Pulse) de mapeamento de IP para geolocalização. A Adobe Analytics adotará esse novo conjunto de dados em **5 de outubro de 2022**. O novo banco de dados será mais preciso que as versões anteriores. Alguns mapeamentos de IP para geolocalização serão alterados/melhorados quando o novo banco de dados for adotado.<p>Todas as ferramentas do Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, API de relatórios, Data Warehouse, LiveStream, feeds de dados etc.) aproveitarão automaticamente os novos mapeamentos aprimorados. Não haverá alteração no formato dos dados nos feeds de dados. Os dados do CJA fornecidos por meio do conector de origem do Analytics também aproveitarão automaticamente os novos mapeamentos. |
| **Pausa de relatórios agendados no Reports &amp; Analytics** | 8 de junho de 2022 | Em 21 de abril de 2022, anunciamos a desativação de vários recursos específicos dos relatórios agendados como preparação para o fim da vida útil do Reports &amp; Analytics anunciado anteriormente. Esses recursos incluíam a capacidade de agendar novos relatórios, bem como novas extrações de dados.<p>Em resposta às solicitações de clientes que buscam uma extensão e para facilitar a transição do Reports and Analytics, decidimos estender o acesso a esses recursos até **31 de janeiro de 2023**. Observe que as janelas de expiração dos relatórios e extrações de dados continuarão limitadas a nove meses; a entrega de relatórios e extrações de dados será pausada no final deste período, a menos que a programação seja reativada.<p>Em outras palavras, esses recursos serão descontinuados em 31 de janeiro de 2023. Antes dessa data, você deve migrar seus relatórios agendados para um dos outros mecanismos disponíveis no Adobe Analytics. Para perguntas adicionais ou suporte, entre em contato com o Atendimento ao cliente da Adobe. [Saiba mais](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Pausa de tarefas agendadas no Report Builder** | 8 de junho de 2022 | Em 21 de abril de 2022, lançamos alterações em tarefas agendadas do Report Builder como parte de nossos esforços de otimização de desempenho e entrega. Essas alterações incluíam a remoção da capacidade de agendar entregas &quot;terminadas após x ocorrências&quot;. Em resposta a várias solicitações de clientes que buscam mais tempo para explorar e implementar alternativas, decidimos restaurar essa opção de maneira limitada até **31 de janeiro de 2023**.<p>Você pode continuar a agendar tarefas do Report Builder por hora e programar seu término após um máximo de 99 ocorrências. Observe que a reversão se aplica somente a tarefas por hora; o &quot;fim após x ocorrências&quot; permanecerá indisponível para todos os outros intervalos de delivery (diário, semanal, mensal e anual). Observe que essa opção será desativada em 31 de janeiro de 2023. Para perguntas adicionais ou suporte, entre em contato com o Atendimento ao cliente da Adobe. [Saiba mais](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **Fim da vida útil do [!DNL Reports & Analytics]** | 4 de janeiro de 2022 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o [!DNL Reports & Analytics], juntamente com os relatórios e recursos que o acompanham. Os relatórios, visualizações e a tecnologia subjacente que alimentam [!DNL Reports & Analytics] não cumpre mais os padrões da tecnologia Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.22.4), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).

