---
description: Descreve as etapas para permitir que sua implementação do Adobe Analytics seja compatível com o acesso à Privacidade de dados e aos direitos de exclusão.
title: Fluxo de trabalho de privacidade
feature: Data Governance
role: Admin
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
TQID: 'https://experienceleague.adobe.com/n0zqbcuPD2lvtgYNtdQx5VsBl-FrmzfqU-z2iIn83hg'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: b99602d0-836e-4dbb-979f-c0dec53f883c
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 333
ht-degree: 59%

---

# Fluxo de trabalho de privacidade

Este fluxo de trabalho descreve as etapas necessárias para preparar a implementação do Adobe Analytics para oferecer suporte aos direitos de acesso e de exclusão da Privacidade de dados dos titulares dos dados.

1. Comece com a página [Visão geral do Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=pt-BR) na Adobe Experience Platform para ter uma ideia de quais perguntas fazer antes de rotular os dados do Analytics.
1. **Defina sua política de retenção de dados.** É necessária uma política de retenção de dados para que o Adobe possa atender às solicitações de acesso/exclusão de dados da Privacidade de dados.  Para obter mais informações, consulte as [Perguntas frequentes sobre retenção de dados](/help/technotes/data-retention.md). Para usar a API Privacy Service, é necessário garantir que o período de retenção de dados esteja definido no Adobe Analytics.
1. **Familiarize-se com rótulos de Privacidade de dados, IDs do Adobe Analytics e namespaces.** Consulte [Rótulos de privacidade de dados para variáveis do Analytics](/help/admin/tools/privacy-labeling/labels.md) e [Práticas recomendadas de rotulagem](/help/admin/tools/privacy-labeling/best-practices.md).
1. **Atribua rótulos de identidade, sensibilidade e governança de dados a cada variável em um conjunto de relatórios.** A Rotulagem precisa ser revisada sempre que um novo conjunto de relatórios for criado ou quando uma nova variável for ativada em um conjunto de relatórios existente. A revisão da rotulagem também é necessária quando novas integrações da solução são habilitadas, pois elas podem expor novas variáveis que exijam rótulos. A reimplementação de aplicativos ou sites móveis pode alterar a maneira como as variáveis existentes são usadas, o que também pode exigir atualizações nos rótulos. Consulte [Rotular dados do conjunto de relatórios](/help/admin/tools/privacy-labeling/namespaces.md).
1. **Conecte-se à API da Privacidade de dados da Adobe e envie solicitações de acesso e de exclusão.** Como cliente do Adobe Analytics, você pode enviar solicitações individuais da Privacidade de dados para acessar e excluir dados do cliente, ao chamar a [API da Adobe Experience Privacy Service](https://experienceleague.adobe.com/pt-br/docs/experience-platform/privacy/api/overview). É possível enviar qualquer identificador do Analytics (conforme descrito na seção [Práticas recomendadas de rotulagem](/help/admin/tools/privacy-labeling/best-practices.md)) nas solicitações, junto com suas respectivas IDs de namespace (IDs da fonte de dados).
1. **Exiba e gerencie as configurações da Privacidade de Dados do seu conjunto de relatórios.** Consulte [Exibir as configurações de governança de dados do conjunto de relatórios](/help/admin/tools/privacy-labeling/view-settings.md).
