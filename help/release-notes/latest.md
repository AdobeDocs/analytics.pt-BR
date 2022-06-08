---
title: Notas de versão mais recentes do Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 8666c32ffe907ad486778fa382404807459be03c
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 62%

---

# Notas de versão atuais do Adobe Analytics (maio de 2022)

**Última atualização**: 8 de junho de 2022

## Recursos relacionados

* [Notas de versão anteriores para 2022](/help/release-notes/2022.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)

## Novos recursos no Adobe Analytics

| Recurso | Descrição | [Data Alvo](releases.md) |
| ----------- | ---------- | ------- |
| Preencher dimensões e métricas do ciclo de vida por meio do Experience Edge | Os dados do ciclo de vida móvel enviados pelo Experience Edge agora serão exibidos nos relatórios do Analytics. Consulte a documentação para obter detalhes sobre quais dados do ciclo de vida são coletados pelo Experience Edge e como eles correspondem aos relatórios existentes de ciclo de vida. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) | 27 de maio de 2022 |

{style=&quot;table-layout:auto&quot;}

### Correções no Adobe Analytics

(Correções para vários clientes)

N/D

### Outras correções no Adobe Analytics

(Correções para clientes individuais)

AN-274429; AN-279640; AN-280918; AN-280945; AN-282884; AN-283565; AN-284785; AN-284814; AN-284854; AN-284989; AN-285244; AN-285253; AN-285432; AN-285528; AN-285535; AN-285710; AN-286255; AN-286340; AN-286434; AN-286454; AN-286630; AN-286716; AN-286854; AN-286911

### Avisos importantes para administradores do Adobe Analytics

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| Pausando relatórios agendados no Reports &amp; Analytics | 8 de junho de 2022 | Em 21 de abril de 2022, anunciamos a desativação de vários recursos específicos dos relatórios agendados, como preparação para o anúncio anterior [Fim da vida útil do Reports &amp; Analytics](https://express.adobe.com/page/6WnF8JK6IRDhf/). Esses recursos incluíam a capacidade de agendar novos relatórios, bem como novas extrações de dados.<p>Em resposta às solicitações do cliente que buscam uma extensão e para facilitar a transição do Reports and Analytics, decidimos estender o acesso a esses recursos até **31 de janeiro de 2023**. Observe que as janelas de expiração dos relatórios e extrações de dados continuarão limitadas a nove meses; a entrega do relatório e da extração de dados será pausada no final deste período, a menos que a programação seja reativada. <p>Em outras palavras, esses recursos serão descontinuados em 31 de janeiro de 2023, antes do que você precisará migrar seus relatórios agendados para um dos outros mecanismos disponíveis no Adobe Analytics. Para perguntas adicionais ou suporte, entre em contato com o Atendimento ao cliente da Adobe. |
| Pausando tarefas agendadas no Report Builder | 8 de junho de 2022 | Em 21 de abril de 2022, lançamos alterações em tarefas agendadas no Report Builder como parte de nossos esforços de otimização de desempenho e delivery. Essas alterações incluíam a remoção da capacidade de agendar entregas &quot;terminadas após x ocorrências&quot;. Em resposta a várias solicitações do cliente que buscam mais tempo para explorar e implementar alternativas, decidimos restaurar essa opção de forma limitada até **31 de janeiro de 2023**.<p>Você continuará sendo capaz de agendar tarefas de Report Builder por hora e terminá-las após no máximo 99 ocorrências. Observe que a reversão se aplica somente a tarefas por hora; o &quot;fim após x ocorrências&quot; permanecerá indisponível para todos os outros intervalos de delivery (diário, semanal, mensal e anual). Observe que essa opção ficará obsoleta em 31 de janeiro de 2023. Para mais perguntas ou suporte, entre em contato com o Atendimento ao cliente do Adobe. |
| **Atualização do SFTP** | 9 de maio de 2022 | Anteriormente, informamos que a Adobe atualizaria seus serviços de Protocolo de transferência segura de arquivo (SFTP) em maio de 2022 para oferecer segurança aprimorada em transferências de arquivos. Adiamos essa atualização para o **Verão de 2022**. Quando essa alteração ocorrer, determinadas configurações de cliente SFTP não serão mais compatíveis. Isso afetará somente os dados enviados para o Adobe Analytics ou recuperados dele por meio do SFTP. O protocolo FTP não é afetado. Para evitar interrupções do serviço, verifique se os clientes SFTP (código, ferramentas, serviços) estarão de acordo com as alterações detalhadas [aqui](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=pt-BR). |
| **Atualização de métodos de criptografia de navegador compatíveis de determinados clientes** | 28 de março de 2022 | A Adobe oferece dois níveis de segurança de criptografia para atender às diversas necessidades de segurança do cliente na coleta de dados primários. Em **23 de junho de 2022**, removeremos o suporte para determinados algoritmos de criptografia HTTPS, conhecidos como cifras, para clientes com o nível de segurança definido como “Alto”. Essa ação significa que alguns sistemas operacionais mais antigos não poderão mais enviar dados para o Analytics porque eles não são compatíveis com métodos de criptografia modernos. Os clientes que usam as configurações de segurança de criptografia “Padrão” não serão afetados. Todos os clientes que atualmente usam a configuração “Alto” já foram contatados diretamente. Uma lista detalhada das cifras afetadas por essa alteração pode ser encontrada aqui. |
| **Atualizações da região ISO 2022** | 11 de março de 2021 | A Adobe planeja realizar as atualizações da região ISO 2022 em **10 de junho de 2022**. Você poderá ver pequenas atualizações de informações geográficas após esta versão. |
| **Fim da vida útil do [!DNL Reports & Analytics]** | 4 de janeiro de 2022 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o [!DNL Reports & Analytics], juntamente com os relatórios e recursos que o acompanham. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o [!DNL Reports & Analytics] não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil. |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.22.4), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).

