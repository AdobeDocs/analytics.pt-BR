---
description: Configure um conjunto de relatórios mapeados da Experience Cloud para uso no Advertising Analytics.
title: Habilitar conjunto de relatórios para o Advertising Analytics
uuid: 934f0e02-b5d7-4eca-93d8-92f95bd7014a
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 95%

---


# Habilitar conjunto de relatórios para o Advertising Analytics

Para visualizar qualquer dado de pesquisa do Advertising Analytics no Analytics, é necessário configurar cada conjunto de relatórios mapeados para Experience Cloud para os relatórios do Advertising Analytics.

1. [Mapear seu conjunto de relatórios para uma organização](https://docs.adobe.com/content/help/pt-BR/core-services/interface/about-core-services/report-suite-mapping.html).
1. Navegue até **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de relatórios]**.

1. Selecione o conjunto de relatórios que está mapeado à sua organização Experience Cloud.
1. Clique em **[!UICONTROL Editar configurações]** > **[!UICONTROL Configuração do Advertising Analytics]**.

   ![Relatórios](assets/aa_reporting.png)

   >[!IMPORTANT]
   >
   >A ID do AMO faz referência à variável do Adobe Advertising Cloud na qual os dados de pesquisa serão inseridos.

1. Defina a alocação e expiração da variável que deseja que a variável da ID do AMO ID utilize. As variáveis de conversão (eVars) permitem que o Adobe Analytics atribua eventos bem-sucedidos a valores de variáveis específicas. Às vezes, as variáveis encontram mais de um valor antes da ocorrência de um evento bem-sucedido. Nesses casos, a alocação determina qual valor de variável deve receber o crédito pelo evento.

   | Configuração | Definição |
   |--- |--- |
   | Valor original (primeiro) | O primeiro valor observado recebe o crédito de alocação completo, independentemente dos valores subsequentes da variável. |
   | Mais recente (último) | O último valor observado obtém crédito de alocação completo para o evento bem-sucedido, independente de quais variáveis foram antes dele. |
   | Expirar após | Permite especificar o período ou evento após o qual o valor do eVar expira (ou seja, não recebe mais crédito por eventos bem-sucedidos).  Se um evento bem-sucedido ocorrer após a expiração da eVar, o valor Nenhum receberá o crédito pelo evento (nenhuma eVar estava ativa). |

1. Clique em **[!UICONTROL Habilitar Relatórios do Advertising Analytics]** (primeiro momento) ou **[!UICONTROL Atualizar Relatórios do Advertising Analytics]** (momentos subsequentes). Seu conjunto de relatórios está pronto para receber dados de pesquisa do Advertising Analytics. Você está pronto para [criar contas publicitárias](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md).

