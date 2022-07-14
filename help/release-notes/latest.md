---
title: Notas de versão mais recentes do Analytics
description: Visualizar as notas de versão atuais do Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: c14fc5f07d74ed3ab85e68e567f37712e4a92883
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 96%

---

# Notas de versão atuais do Adobe Analytics (junho de 2022)

**Última atualização**: 13 de julho de 2022

## Recursos relacionados

* [Notas de versão anteriores para 2022](/help/release-notes/2022.md)
* [Notas de versão do Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* As atualizações de versão mais recentes para [produtos da Adobe Experience Cloud](https://business.adobe.com/br/products/adobe-experience-cloud-products.html)

## Novos recursos no Adobe Analytics

| Recurso | Descrição | [Data Alvo](releases.md) |
| ----------- | ---------- | ------- |
| **Nova interface de visualização de fluxo** | Fornece funcionalidades adicionais à visualização de fluxo para torná-la mais eficiente. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/flow/create-flow.html?lang=pt-BR) | A implantação terá início em 15 de junho de 2022; a disponibilização geral ocorrerá em 27 ou 28 de junho de 2022 |
| **Compartilhar anotações em cartões de pontuação móveis** | Você pode exibir anotações criadas no espaço de trabalho nos cartões de pontuação móveis. Isso permite compartilhar nuances de dados contextuais e insights sobre sua organização e campanhas diretamente para os projetos de cartões de pontuação móveis, visualizáveis no aplicativo móvel de painéis do Analytics. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/annotations/mobile-annotations.html?lang=pt-BR) | 15 de junho de 2022 |
| **Compatibilidade com a versão de sintaxe de produto de variáveis de merchandising com o Edge Collection** | Agora é possível definir variáveis de merchandising usando o equivalente da sintaxe de produto ao definir os campos XDM relevantes. Consulte [variáveis de produtos](../implement/vars/page-vars/products.md), sintaxe do SDK da Web com a variável `products` e [Mapeamento de variáveis do Analytics no Adobe Experience Edge](../implement/aep-edge/variable-mapping.md) para obter uma lista completa de variáveis disponíveis. | 15 de junho de 2022 |
| **Preencher dimensões e métricas do ciclo de vida por meio do Experience Edge** | Os dados do ciclo de vida móvel enviados pelo Experience Edge agora serão exibidos nos relatórios do Analytics. Consulte a documentação para obter detalhes sobre quais campos XDM são mapeados para relatórios de ciclo de vida móvel existentes. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=pt-BR) | 27 de maio de 2022 |
| **As regras de processamento do Mobile Services estão disponíveis nas regras de processamento do Analytics** | A data do fim da vida útil do Adobe Mobile Services é 31 de dezembro de 2022. As regras de processamento existentes que foram criadas ou geradas pelo Adobe Mobile Services migrarão automaticamente para as regras de processamento do Adobe Analytics, onde você poderá editá-las e gerenciá-las. Elas podem ser visualizadas, mas não podem mais ser editadas no Mobile Services até que o produto seja descontinuado. Para perguntas adicionais ou suporte, entre em contato com o Atendimento ao cliente da Adobe. [Saiba mais](https://experienceleague.adobe.com/docs/mobile-services/using/eol.html?lang=pt-BR) | 15 de junho de 2022 |
| **Conjuntos de classificações - Fase 1** | Essa versão em fases da nova experiência de classificações disponibilizada ao usuário melhora significativamente a visibilidade dos dados de classificação de propriedade do cliente. Consulte [Conjuntos de classificações](../components/classifications/sets/overview.md) para obter mais informações. | O teste limitado começa em 15 de junho de 2022 e a disponibilidade geral está prevista para o início de 2023 |

{style=&quot;table-layout:auto&quot;}

### Correções no Adobe Analytics

AN-251686; AN-283542; AN-286572; AN-286945; AN-286784; AN-286944; AN-287012; AN-287319; AN-287333; AN-287348; AN-287429; AN-288238; AN-288281; AN-288660; AN-288769; AN-288798; AN-288871; AN-288872; AN-288941; AN-288951; AN-288952; AN-288956; AN-289062; AN-289340; AN-289346; AN-289488; AN-289562; AN-289580; AN-289861; AN-289892;

### Avisos importantes para administradores do Adobe Analytics

| Aviso | Data de adição ou atualização | Descrição |
| ----------- | ---------- | ---------- |
| **Novo domínio para emails gerados pelo sistema** | 13 de julho de 2022 | Ligado **18 de maio de 2022**, o Adobe alterou o domínio do remetente para emails de projetos, alertas e alertas de sobreposição do Workspace, de `noreply@omniture.com` para `noreply@adobe.com`. Adicione esse novo email à lista de permissões se a organização permitir somente remetentes específicos. |
| **Pausa de relatórios agendados no Reports &amp; Analytics** | 8 de junho de 2022 | Em 21 de abril de 2022, anunciamos a desativação de vários recursos específicos dos relatórios agendados como preparação para o fim da vida útil do Reports &amp; Analytics anunciado anteriormente. Esses recursos incluíam a capacidade de agendar novos relatórios, bem como novas extrações de dados.<p>Em resposta às solicitações de clientes que buscam uma extensão e para facilitar a transição do Reports &amp; Analytics, decidimos estender o acesso a esses recursos até **31 de janeiro de 2023**. Observe que as janelas de expiração dos relatórios e extrações de dados continuarão limitadas a nove meses; a entrega de relatórios e extrações de dados será pausada no final deste período, a menos que a programação seja reativada.<p>Em outras palavras, esses recursos serão descontinuados em 31 de janeiro de 2023. Antes dessa data, você deve migrar seus relatórios agendados para um dos outros mecanismos disponíveis no Adobe Analytics. Para perguntas adicionais ou suporte, entre em contato com o Atendimento ao cliente da Adobe. [Saiba mais](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Pausa de tarefas agendadas no Report Builder** | 8 de junho de 2022 | Em 21 de abril de 2022, lançamos alterações em tarefas agendadas do Report Builder como parte de nossos esforços de otimização de desempenho e entrega. Essas alterações incluíam a remoção da capacidade de agendar entregas “terminadas após x ocorrências”. Em resposta a várias solicitações de clientes que buscam mais tempo para explorar e implementar alternativas, decidimos restaurar essa opção de maneira limitada até **31 de janeiro de 2023**.<p>Você pode continuar a agendar tarefas do Report Builder por hora e programar seu término após um máximo de 99 ocorrências. Observe que a reversão se aplica somente a tarefas por hora; a opção “terminar após x ocorrências” permanecerá indisponível para todos os outros intervalos de entrega (diário, semanal, mensal e anual). Observe que essa opção será desativada em 31 de janeiro de 2023. Para perguntas adicionais ou suporte, entre em contato com o Atendimento ao cliente da Adobe. [Saiba mais](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **Atualização do SFTP** | 9 de maio de 2022 | Anteriormente, informamos que a Adobe atualizaria seus serviços de Protocolo de transferência segura de arquivo (SFTP) em maio de 2022 para oferecer segurança aprimorada em transferências de arquivos. Adiamos essa atualização para o **verão (do hemisfério norte) de 2022**. Quando essa alteração ocorrer, determinadas configurações de cliente SFTP não serão mais compatíveis. Isso afetará somente os dados enviados para o Adobe Analytics ou recuperados dele por meio do SFTP. O protocolo FTP não é afetado. Para evitar interrupções do serviço, verifique se os clientes SFTP (código, ferramentas, serviços) estarão de acordo com as alterações detalhadas [aqui](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=pt-BR). |
| **Atualização de métodos de criptografia de navegador compatíveis de determinados clientes** | 28 de março de 2022 | A Adobe oferece dois níveis de segurança de criptografia para atender às diversas necessidades de segurança do cliente na coleta de dados primários. Em **23 de junho de 2022**, removeremos o suporte para determinados algoritmos de criptografia HTTPS, conhecidos como cifras, para clientes com o nível de segurança definido como “Alto”. Essa ação significa que alguns sistemas operacionais mais antigos não poderão mais enviar dados para o Analytics porque eles não são compatíveis com métodos de criptografia modernos. Os clientes que usam as configurações de segurança de criptografia “Padrão” não serão afetados. Todos os clientes que atualmente usam a configuração “Alto” já foram contatados diretamente. Uma lista detalhada das cifras afetadas por isso |
| **Atualizações da região ISO 2022** | 11 de março de 2021 | A Adobe realizou atualizações da região ISO 2022 em **10 de junho de 2022**. Você poderá ver pequenas atualizações de informações geográficas após esta versão. |
| **Fim da vida útil do [!DNL Reports & Analytics]** | 4 de janeiro de 2022 | A partir de **31 de dezembro de 2023**, a Adobe pretende descontinuar o [!DNL Reports & Analytics], juntamente com os relatórios e recursos que o acompanham. Os relatórios, as visualizações e as tecnologias subjacentes que alimentam o [!DNL Reports & Analytics] não atendem mais aos padrões de tecnologia da Adobe. A maioria dos recursos do [!DNL Reports & Analytics] estão disponíveis no [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=pt-BR). Desde o lançamento do Analysis Workspace em 2015, a funcionalidade e os recursos do [!DNL Reports & Analytics] foram movidos para o Analysis Workspace e um limite de paridade de fluxo de trabalho foi atingido. [Este aviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) explica o processo do fim da vida útil. |

{style=&quot;table-layout:auto&quot;}

### AppMeasurement

Para obter as atualizações mais recentes sobre as versões do AppMeasurement (versão 2.22.4), consulte as [notas de versão do AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=pt-BR).

