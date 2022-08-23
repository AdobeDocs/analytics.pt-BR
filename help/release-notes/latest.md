---
title: Notas de versão mais recentes do Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 21b8e21a0f5488e4e8702d5e7538360add1cd621
workflow-type: tm+mt
source-wordcount: '1264'
ht-degree: 80%

---

# Notas de versão atuais do Adobe Analytics (agosto de 2022)

**Última atualização**: 19 de agosto de 2022

## Recursos relacionados

* [Notas de versão anteriores para 2022](/help/release-notes/2022.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)

## Recursos novos ou atualizados no Adobe Analytics

| Recurso | Descrição | [Data Alvo](releases.md) |
| ----------- | ---------- | ------- |
| Suporte para variáveis de lista no XDM para coleção de borda | Permite que os clientes que coletam dados por meio do Experience Edge/SDK da Web usem o XDM para especificar o conteúdo da variável de lista. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/list.html?lang=en#list-variables-using-the-web-sdk) | 18 de agosto de 2022 |
| Uso do campo SKU no XDM para Edge Collection ao definir variáveis de sequência de produtos | Permite que os clientes que coletam dados por meio do Experience Edge/SDK da Web usem o valor SKU para definir o campo do produto na variável products . [Saiba mais](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html?lang=en#products-using-the-web-sdk) | 18 de agosto de 2022 |

{style=&quot;table-layout:auto&quot;}

## Correções no Adobe Analytics

* Correção de vários problemas relacionados ao feed de dados. (AN-297264; AN-297295; AN-297449)

**Correções para clientes individuais**:

AN-274281; AN-280956; AN-285670; AN-288176; AN-289221; AN-289665; AN-289768; AN-294632; AN-294970; AN-295078; AN-295233; AN-295482; AN-295549; AN-295633; AN-295712; AN-295749; AN-295963; AN-295977; AN-296094; AN-296153; AN-296167; AN-296177; AN-296297; AN-296383; AN-296394; AN-296414; AN-296431; AN-296459; AN-296486; AN-296510; AN-296514; AN-296540; AN-296734; AN-296840; AN-296841; AN-296977; AN-296987; AN-297002; AN-297141; AN-297158; AN-297267; AN-297396; AN-297397; AN-297522; AN-297704; AN-297705; AN-297829; AN-297895;

## Avisos importantes para administradores do Adobe Analytics

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Atualização em pesquisas de dispositivo devido a dicas de cliente do Google** | 19 de agosto de 2022 | A partir de outubro de 2022, o Adobe começará a usar dicas do cliente além do Agente do usuário ao derivar determinadas informações do dispositivo para ocorrências provenientes de navegadores Chromium, como Google Chrome e Microsoft Edge. Isso é uma resposta ao plano da Google de reduzir gradualmente as informações apresentadas a partir da sequência de agente do usuário, em vez dos dados transmitidos por meio de dicas do cliente. Leia mais sobre dicas de clientes [here](https://web.dev/user-agent-client-hints/).<p> Até outubro, as bibliotecas de coleção do AppMeasurement e do SDK da Web oferecerão suporte à coleta de dicas do cliente e à configuração da coleta de dicas de cliente de alta entropia. Como parte dessa alteração, o Adobe usará o Device Atlas para todas as pesquisas de dispositivos relacionadas ao Agente do usuário. Atualmente, o Device Atlas é usado apenas para ocorrências móveis. Essas atualizações podem resultar em pequenas alterações nas informações do dispositivo historicamente derivadas do Agente do usuário - especificamente Navegador, Tipo de navegador, Sistema operacional, Tipo de sistema operacional e Dispositivo móvel. |
| **Atualização do SFTP** | 12 de agosto de 2022 | Anteriormente, informamos que a Adobe atualizaria seus serviços de Protocolo de transferência segura de arquivo (SFTP) em maio de 2022 para oferecer segurança aprimorada em transferências de arquivos. Adiamos essa atualização para **7 de setembro de 2022**. Quando essa alteração ocorrer, determinadas configurações de cliente SFTP não serão mais compatíveis. Isso afetará somente os dados enviados para o Adobe Analytics ou recuperados dele por meio do SFTP. O protocolo FTP não é afetado. Para evitar interrupções do serviço, verifique se os clientes SFTP (código, ferramentas, serviços) estarão de acordo com as alterações detalhadas [aqui](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=pt-BR). |
| **Atualização para o novo banco de dados da operadora NetAcuity** | 11 de julho de 2022 | **A partir de outubro de 2022**, as informações sobre a operadora armazenadas no campo `carrier` do Data Warehouse e dos feeds de dados do Adobe Analytics serão alteradas. Historicamente, o formato dos dados nessa coluna foi `<domain>:<ISP>`. A Adobe manteve uma tabela de pesquisa interna para mapear esses valores `<domain>:<ISP>` em nomes de operadoras para fins de relatório nas ferramentas de relatório do Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, API de relatórios, Data Warehouse, LiveStream etc.). O arquivo de pesquisa (`carrier.tsv`) também é fornecido com feeds de dados para que você possa usar os mesmos mapeamentos.<p>Essa atualização melhora nossos mapeamentos de operadora ao usar um banco de dados de operadora mais preciso da NetAcuity. O formato dos dados na coluna da operadora nos feeds de dados será alterado a partir de agora. Em vez de `<domain>:<ISP>`, ele conterá um nome de operadora. A Adobe continuará a usar a tabela de pesquisa para manter a maior continuidade possível com os relatórios anteriores. As ferramentas de relatórios nas quais as pesquisas são aplicadas pela Adobe (Analysis Workspace, Reports &amp; Analytics, API de relatórios, Data Warehouse, LiveStream etc.) se beneficiarão de mapeamentos mais precisos. Alguns mapeamentos — especialmente os de domínios internacionais e ISPs — mudarão mais do que outros quando adotarmos o novo banco de dados. O arquivo de pesquisa da operadora dos feeds de dados (`carrier.tsv`) manterá os mapeamentos antigos e adicionará os novos mapeamentos.<p>No momento, o conector de origem do Analytics não mapeia o campo da operadora. Portanto, o relatório da operadora não está disponível no AEP, CJA etc. Sendo assim, o uso do novo banco de dados de operadora não afetará nada no AEP que seja baseado nos dados fornecidos pelo conector de origem do Analytics. |
| **Melhoria no mapeamento de IP para geolocalização** | 11 de julho de 2022 | Nosso fornecedor de pesquisas de IP, Digital Element, está atualizando para um novo conjunto de dados aprimorado (NetAcuity Pulse) de mapeamento de IP para geolocalização. O Adobe Analytics adotará esse novo conjunto de dados no decorrer do mês de **outubro de 2022**. O novo banco de dados será mais preciso que as versões anteriores. Alguns mapeamentos de IP para geolocalização serão alterados/melhorados quando o novo banco de dados for adotado.<p>Todas as ferramentas do Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, API de relatórios, Data Warehouse, LiveStream, feeds de dados etc.) aproveitarão automaticamente os novos mapeamentos aprimorados. Não haverá alteração no formato dos dados nos feeds de dados. Os dados do CJA fornecidos por meio do conector de origem do Analytics também aproveitarão automaticamente os novos mapeamentos. |
| **Pausa de relatórios agendados no Reports &amp; Analytics** | 8 de junho de 2022 | Em 21 de abril de 2022, anunciamos a desativação de vários recursos específicos dos relatórios agendados como preparação para o fim da vida útil do Reports &amp; Analytics anunciado anteriormente. Esses recursos incluíam a capacidade de agendar novos relatórios, bem como novas extrações de dados.<p>Em resposta às solicitações de clientes que buscam uma extensão e para facilitar a transição do Reports and Analytics, decidimos estender o acesso a esses recursos até **31 de janeiro de 2023**. Observe que as janelas de expiração dos relatórios e extrações de dados continuarão limitadas a nove meses; a entrega de relatórios e extrações de dados será pausada no final deste período, a menos que a programação seja reativada.<p>Em outras palavras, esses recursos serão descontinuados em 31 de janeiro de 2023. Antes dessa data, você deve migrar seus relatórios agendados para um dos outros mecanismos disponíveis no Adobe Analytics. Para perguntas adicionais ou suporte, entre em contato com o Atendimento ao cliente da Adobe. [Saiba mais](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Pausa de tarefas agendadas no Report Builder** | 8 de junho de 2022 | Em 21 de abril de 2022, lançamos alterações em tarefas agendadas do Report Builder como parte de nossos esforços de otimização de desempenho e entrega. Essas alterações incluíam a remoção da capacidade de agendar entregas “terminadas após x ocorrências”. Em resposta a várias solicitações de clientes que buscam mais tempo para explorar e implementar alternativas, decidimos restaurar essa opção de maneira limitada até **31 de janeiro de 2023**.<p>Você pode continuar a agendar tarefas do Report Builder por hora e programar seu término após um máximo de 99 ocorrências. Observe que a reversão se aplica somente a tarefas por hora; a opção “terminar após x ocorrências” permanecerá indisponível para todos os outros intervalos de entrega (diário, semanal, mensal e anual). Observe que essa opção será desativada em 31 de janeiro de 2023. Para perguntas adicionais ou suporte, entre em contato com o Atendimento ao cliente da Adobe. [Saiba mais](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **Fim da vida útil do [!DNL Reports & Analytics]** | 4 de janeiro de 2022 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o [!DNL Reports & Analytics], juntamente com os relatórios e recursos que o acompanham. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o [!DNL Reports & Analytics] não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.22.4), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).

