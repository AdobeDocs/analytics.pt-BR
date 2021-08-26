---
description: Descreve as etapas para permitir que sua implementação do Adobe Analytics seja compatível com o acesso à Privacidade de dados e aos direitos de exclusão.
title: Fluxo de trabalho de privacidade
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: 7cb2489c2deaf8e75c71589895314067a010caf8
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 58%

---

# Fluxo de trabalho de privacidade

Este fluxo de trabalho descreve as etapas necessárias para preparar a implementação do Adobe Analytics para oferecer suporte aos direitos de acesso e de exclusão da Privacidade de dados dos titulares dos dados.

1. **Defina sua política de retenção de dados.** É necessária uma política de retenção de dados para que o Adobe possa atender às solicitações de acesso/exclusão de dados da Privacidade de dados.  Para obter mais informações, consulte as [Perguntas frequentes sobre a retenção de dados](/help/technotes/data-retention.md).
1. **Familiarize-se com rótulos DULE/Privacidade de dados, IDs do Adobe Analytics, namespaces e expansão de ID.** Consulte Rótulos da privacidade  [de dados para ](/help/admin/c-data-governance/gdpr-labels.md) variáveis do Analytics e práticas recomendadas  [de rotulagem](/help/admin/c-data-governance/gdpr-analytics-ids.md).
1. **Atribua rótulos de identidade, sensibilidade e governança de dados a cada variável em um conjunto de relatórios.** A rotulagem precisa ser analisada sempre que um novo conjunto de relatórios for criado ou quando uma nova variável for ativada em um conjunto de relatórios existente. Analise também a rotulagem quando novas integrações da solução forem ativadas, pois elas podem expor novas variáveis que podem exigir rótulos. Uma reimplementação de seus aplicativos ou sites móveis pode alterar a forma como as variáveis existentes são usadas, o que também pode exigir atualizações nos rótulos. Consulte [Rotular dados do conjunto de relatórios](/help/admin/c-data-governance/gdpr-setup-reportsuite.md).
1. **Conecte-se à API da Privacidade de dados da Adobe e envie solicitações de acesso e de exclusão.** Como cliente do Adobe Analytics, você pode enviar solicitações individuais da Privacidade de dados para acessar e excluir dados do cliente, ao chamar a [API da Privacidade de dados da Adobe Experience Cloud](https://www.adobe.io/apis/experienceplatform/gdpr.html). É possível enviar qualquer identificador do Analytics (conforme descrito na seção [Práticas recomendadas de rotulagem](/help/admin/c-data-governance/gdpr-analytics-ids.md)) nas solicitações, junto com suas respectivas IDs de namespace (IDs da fonte de dados).
1. **Visualize e gerencie as configurações da Privacidade de dados do seu conjunto de relatórios.** Consulte  [Exibir as configurações de governança de dados do conjunto de relatórios](/help/admin/c-data-governance/gdpr-view-settings.md).
