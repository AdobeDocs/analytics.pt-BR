---
description: Como visualizar o uso atual de chamada de servidor no Adobe Analytics.
title: Visualizar uso de chamadas do servidor atual
feature: Server Call Usage
exl-id: 07eac732-b9d6-41ab-be34-5688eaa8166e
role: Admin
TQID: 'https://experienceleague.adobe.com/5DgWR4QWklOEMK1Ato17-lcpMdnRgaIrMfds9ATXUpE'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c9d85838-8d05-4bc7-9f18-30ec779251bc
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 293
ht-degree: 35%

---

# Visualizar uso de chamadas do servidor atual

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Uso de chamadas do servidor]** > **[!UICONTROL Uso atual]**

>[!IMPORTANT]
>
>Quaisquer números de uso e de compromisso exibidos são cumulativos em todas as suas empresas de logon e conjuntos de relatórios.

O painel Uso atual

* Exibe um detalhamento do seu consumo e compromisso de chamadas do servidor entre cada um de seus tipos de chamadas do servidor. Essa visualização pode ser diferente para clientes diferentes e é consistente com o que o contrato inclui. Por exemplo, você pode ter se inscrito em quatro tipos separados de chamadas de servidor: Primárias e Secundárias para Web e Primárias e Secundárias para Móveis. Nesse caso, essa visualização seria composta por quatro guias, uma para cada tipo. Em cada guia, é possível visualizar o consumo do período de uso atual.
* Compara o uso atual (linha verde) com o limite de uso contratual (linha vermelha).

  ![](/help/admin/tools/server-call-usage/assets/current_period.png)

* Compara seu período de uso atual ao uso do ano anterior (lina azul). Obviamente, a linha azul só aparecerá se sua empresa tiver dados de uso de chamadas do servidor do ano anterior.

  >[!NOTE]
  >
  >Se quiser exibir o uso de um período anterior, acesse a guia [Uso do conjunto de relatórios](/help/admin/tools/server-call-usage/report-suite-usage.md) e baixe os dados de uso de um período anterior.

* Lista a porcentagem de chamadas usadas (em porcentagens e dados brutos) e a porcentagem do período de uso gasto (em porcentagens e dados brutos).
* Por padrão, é atualizado diariamente, com uma latência de processamento de 5 dias.
* Permite recolher e expandir todos os reportlets.

![](/help/admin/tools/server-call-usage/assets/server_call_dashboard.png)

| Termo da interface | Definição |
| --- | --- |
| Uso do Período Atual (verde) | O período atual é baseado no [período de uso](/help/admin/tools/server-call-usage/overage-overview.md). |
| Uso do Período Anterior (azul) | O período anterior é definido como o período de uso atual menos 1 ano. |
| Limite de uso (vermelho) | Seu limite de uso contratual para este período de uso. |
