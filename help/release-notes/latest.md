---
title: Notas de versão mais recentes do Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: a71db2fac9333b70a55da91fe9a94b0cc8434b42
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 100%

---

# Notas de versão atuais do Adobe Analytics (julho de 2022)

**Última atualização**: 13 de julho de 2022

## Recursos relacionados

* [Notas de versão anteriores para 2022](/help/release-notes/2022.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)

## Novos recursos no Adobe Analytics

| Recurso | Descrição | [Data Alvo](releases.md) |
| ----------- | ---------- | ------- |
| Compatibilidade com variáveis de merchandising no XDM para o Edge Collection | Permite que os clientes que coletam dados por meio do Experience Edge/SDK da Web usem o XDM para especificar os diversos valores das variáveis de merchandising (eVars). [Saiba mais](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/evar-merchandising.html?lang=pt-BR) | 29 de junho de 2022 |

{style=&quot;table-layout:auto&quot;}

## Correções no Adobe Analytics

* Correção de alguns erros de conversão de segmento. (AN-291262, AN-294092)

**Correções para clientes individuais**:

AN-280192; AN-281628; AN-287022; AN-287104; AN-287876; AN-288802; AN-288457; AN-288779; AN-288799; AN-289198; AN-289852; AN-289931; AN-290162; AN-290213; AN-291059; AN-291090; AN-291270; AN-294091; AN-294135; AN-294152; AN-294158; AN-294285; AN-294317; AN-294404; AN-294531; AN-294769; AN-294984; AN-295172; AN-295211; AN-295224; AN-295413; AN-295440; AN-295465; AN-295499; AN-295516;

## Avisos importantes para administradores do Adobe Analytics

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Novo domínio para emails gerados pelo sistema** | 13 de julho de 2022 | Em **18 de maio de 2022**, a Adobe alterou o domínio do remetente para emails de projetos, alertas comuns e alertas de excesso do espaço de trabalho; ele foi alterado de `noreply@omniture.com` para `noreply@adobe.com`. Adicione esse novo email à sua lista de permissões se a organização permitir somente remetentes específicos. |
| **Atualização para o novo banco de dados da operadora NetAcuity** | 11 de julho de 2022 | **A partir de outubro de 2022**, as informações sobre a operadora armazenadas no campo `carrier` do Data Warehouse e dos feeds de dados do Adobe Analytics serão alteradas. Historicamente, o formato dos dados nessa coluna foi `<domain>:<ISP>`. A Adobe manteve uma tabela de pesquisa interna para mapear esses valores `<domain>:<ISP>` em nomes de operadoras para fins de relatório nas ferramentas de relatório do Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, API de relatórios, Data Warehouse, LiveStream etc.) O arquivo de pesquisa (carrier.tsv) também é fornecido com feeds de dados para que os clientes dos feeds de dados possam usar os mesmos mapeamentos.<p>Essa atualização melhora nossos mapeamentos de operadora ao usar um banco de dados de operadora mais preciso da NetAcuity. O formato dos dados na coluna da operadora nos feeds de dados será alterado a partir de agora. Em vez de `<domain>:<ISP>`, ele conterá um nome de operadora. A Adobe continuará a usar a tabela de pesquisa para manter a maior continuidade possível com os relatórios anteriores. As ferramentas de relatórios nas quais as pesquisas são aplicadas pela Adobe (Analysis Workspace, Reports &amp; Analytics, API de relatórios, Data Warehouse, LiveStream etc.) se beneficiarão de mapeamentos mais precisos. Alguns mapeamentos — especialmente os de domínios internacionais e ISPs — mudarão mais do que outros quando adotarmos o novo banco de dados. O arquivo de pesquisa da operadora dos feeds de dados (carrier.tsv) manterá os mapeamentos antigos e adicionará os novos mapeamentos.<p>No momento, o conector de origem do Analytics não mapeia o campo da operadora. Portanto, o relatório da operadora não está disponível no AEP, CJA etc. Sendo assim, o uso do novo banco de dados de operadora não afetará nada no AEP que seja baseado nos dados fornecidos pelo conector de origem do Analytics. |
| **Melhoria no mapeamento de IP para geolocalização** | 11 de julho de 2022 | Nosso fornecedor de pesquisas de IP, Digital Element, está atualizando para um novo conjunto de dados aprimorado (NetAcuity Pulse) de mapeamento de IP para geolocalização. O Adobe Analytics adotará esse novo conjunto de dados no decorrer do mês de **outubro de 2022**. O novo banco de dados será mais preciso que as versões anteriores. Alguns mapeamentos de IP para geolocalização serão alterados/melhorados quando o novo banco de dados for adotado.<p>Todas as ferramentas do Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, API de relatórios, Data Warehouse, LiveStream, feeds de dados etc.) aproveitarão automaticamente os novos mapeamentos aprimorados. Não haverá alteração no formato dos dados nos feeds de dados. Os dados do CJA fornecidos por meio do conector de origem do Analytics também aproveitarão automaticamente os novos mapeamentos. |
| **Pausa de relatórios agendados no Reports &amp; Analytics** | 8 de junho de 2022 | Em 21 de abril de 2022, anunciamos a desativação de vários recursos específicos dos relatórios agendados como preparação para o fim da vida útil do Reports &amp; Analytics anunciado anteriormente. Esses recursos incluíam a capacidade de agendar novos relatórios, bem como novas extrações de dados.<p>Em resposta às solicitações de clientes que buscam uma extensão e para facilitar a transição do Reports and Analytics, decidimos estender o acesso a esses recursos até **31 de janeiro de 2023**. Observe que as janelas de expiração dos relatórios e extrações de dados continuarão limitadas a nove meses; a entrega de relatórios e extrações de dados será pausada no final deste período, a menos que a programação seja reativada.<p>Em outras palavras, esses recursos serão descontinuados em 31 de janeiro de 2023. Antes dessa data, você deve migrar seus relatórios agendados para um dos outros mecanismos disponíveis no Adobe Analytics. Para perguntas adicionais ou suporte, entre em contato com o Atendimento ao cliente da Adobe. [Saiba mais](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Pausa de tarefas agendadas no Report Builder** | 8 de junho de 2022 | Em 21 de abril de 2022, lançamos alterações em tarefas agendadas do Report Builder como parte de nossos esforços de otimização de desempenho e entrega. Essas alterações incluíam a remoção da capacidade de agendar entregas “terminadas após x ocorrências”. Em resposta a várias solicitações de clientes que buscam mais tempo para explorar e implementar alternativas, decidimos restaurar essa opção de maneira limitada até **31 de janeiro de 2023**.<p>Você pode continuar a agendar tarefas do Report Builder por hora e programar seu término após um máximo de 99 ocorrências. Observe que a reversão se aplica somente a tarefas por hora; a opção “terminar após x ocorrências” permanecerá indisponível para todos os outros intervalos de entrega (diário, semanal, mensal e anual). Observe que essa opção será desativada em 31 de janeiro de 2023. Para perguntas adicionais ou suporte, entre em contato com o Atendimento ao cliente da Adobe. [Saiba mais](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **Atualização do SFTP** | 9 de maio de 2022 | Anteriormente, informamos que a Adobe atualizaria seus serviços de Protocolo de transferência segura de arquivo (SFTP) em maio de 2022 para oferecer segurança aprimorada em transferências de arquivos. Adiamos essa atualização para o **verão (do hemisfério norte) de 2022**. Quando essa alteração ocorrer, determinadas configurações de cliente SFTP não serão mais compatíveis. Isso afetará somente os dados enviados para o Adobe Analytics ou recuperados dele por meio do SFTP. O protocolo FTP não é afetado. Para evitar interrupções do serviço, verifique se os clientes SFTP (código, ferramentas, serviços) estarão de acordo com as alterações detalhadas [aqui](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=pt-BR). |
| **Fim da vida útil do [!DNL Reports & Analytics]** | 4 de janeiro de 2022 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o [!DNL Reports & Analytics], juntamente com os relatórios e recursos que o acompanham. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o [!DNL Reports & Analytics] não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.22.4), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).

