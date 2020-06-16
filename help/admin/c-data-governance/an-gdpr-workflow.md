---
description: 'null'
title: Fluxo de trabalho de privacidade
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
translation-type: ht
source-git-commit: dcb07f8717337da904b252864eb7f800f1728231

---


# Fluxo de trabalho de privacidade

Este fluxo de trabalho descreve as etapas necessárias para preparar a implementação do Adobe Analytics para oferecer suporte aos direitos de acesso e de exclusão da Privacidade de dados dos titulares dos dados.

| Descrição da tarefa | Links para instruções e mais informações |
|--- |--- |
| **Etapa 1**: certifique-se de que todos os conjuntos de relatórios que possam conter dados relevantes para a Privacidade de dados sejam mapeados para a sua organização da Experience Cloud (ou IMS).  As solicitações de Privacidade de dados são enviadas por meio de uma organização da Experience Cloud e serão aplicadas a todos os conjuntos de relatórios reivindicados por essa organização. As solicitações não serão aplicadas a conjuntos de relatórios não mapeados para essa organização, mesmo se fizerem parte da sua empresa de logon. | Consulte [Mapear conjuntos de relatórios para uma organização](https://docs.adobe.com/content/help/pt-BR/core-services/interface/about-core-services/report-suite-mapping.html). |
| **Etapa 2**: defina sua política de retenção de dados. | Uma política de retenção de dados precisa estar em vigor para que a Adobe possa atender às solicitações de acesso à Privacidade de dados/exclusão de dados.  Para obter mais informações, consulte estas [Perguntas frequentes sobre a retenção de dados do Analytics](/help/technotes/data-retention.md). |
| **Etapa 3**: familiarize-se com rótulos DULE/Privacidade de dados, IDs do Adobe Analytics, namespaces e expansão de ID. | Leia os seguintes tópicos neste conjunto de documentação:<ul><li>[Rótulos de privacidade de dados para variáveis do Analytics](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[Práticas recomendadas de rotulagem](/help/admin/c-data-governance/gdpr-analytics-ids.md)</li></ul> |
| **Etapa 4**: atribua rótulos de identidade, sensibilidade e governança de dados a cada variável em um conjunto de relatórios.  Observação: lembre-se de que a Rotulagem precisa ser analisada sempre que um novo conjunto de relatórios for criado ou quando uma nova variável for ativada em um conjunto de relatórios existente. Você também pode analisar a rotulagem quando novas integrações da solução forem ativadas, pois elas podem expor novas variáveis que podem exigir rótulos. A reimplementação de aplicativos ou sites móveis pode alterar como as variáveis existentes são usadas, o que também pode exigir atualizações nos rótulos. | Siga as instruções em [Rotular dados do conjunto de relatórios](/help/admin/c-data-governance/gdpr-setup-reportsuite.md). |
| **Etapa 5**: conecte-se à API da Privacidade de dados da Adobe e envie solicitações de acesso e de exclusão. | Como cliente do Adobe Analytics, você pode enviar solicitações individuais da Privacidade de dados para acessar e excluir dados do cliente, ao chamar a [API da Privacidade de dados da Adobe Experience Cloud](https://www.adobe.io/apis/experienceplatform/gdpr.html). É possível enviar qualquer identificador do Analytics (conforme descrito na seção [Práticas recomendadas de rotulagem](/help/admin/c-data-governance/gdpr-analytics-ids.md)) nas solicitações, junto com suas respectivas IDs de namespace (IDs da fonte de dados). |
| **Etapa 6**: visualize e gerencie as configurações da Privacidade de dados do seu conjunto de relatórios. | Siga as instruções em [Exibir configurações da governança de dados do conjunto de relatórios](/help/admin/c-data-governance/gdpr-view-settings.md). |
