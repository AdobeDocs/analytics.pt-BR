---
description: Configure um conjunto de relatórios mapeados da Experience Cloud para uso no Advertising Analytics.
title: Habilitar conjunto de relatórios para o Advertising Analytics
feature: Advertising Analytics
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
source-git-commit: c53b533a1d037ab3ed811bcc0960418f037a708f
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 47%

---

# Habilitar conjunto de relatórios para o Advertising Analytics

Para ver dados de pesquisa do Advertising Analytics no Analytics, é necessário configurar cada conjunto de relatórios mapeados por Experience Cloud para os relatórios do Advertising Analytics.

1. Navegue até **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de relatórios]**.

1. Selecione o conjunto de relatórios que está mapeado à sua organização Experience Cloud.
1. Clique em **[!UICONTROL Editar configurações]** > **[!UICONTROL Configuração do Advertising Analytics]**.

   ![Relatórios](assets/aa-reporting.png)

   >[!IMPORTANT]
   >
   >A ID do AMO se refere à variável do Adobe Advertising Cloud (também conhecida como Adobe Media Optimizer) na qual os dados de pesquisa serão inseridos.

1. Selecione **[!UICONTROL Não está familiarizado com o Advertising Analytics? Clique aqui para saber mais]** para obter mais informações sobre o Advertising Analytics.

1. Defina a alocação e a expiração da variável que você deseja que a variável da ID do AMO use. As variáveis de conversão (eVars) permitem que o Adobe Analytics atribua eventos bem-sucedidos a valores de variáveis específicas. Às vezes, as variáveis encontram mais de um valor antes da ocorrência de um evento bem-sucedido. Nesses casos, a alocação determina qual valor de variável deve receber o crédito pelo evento.

   | Configuração | Definição |
   |--- |--- |
   | **[!UICONTROL Alocação]** | Selecionar entre:<br/> **[!UICONTROL Valor Original (Primeiro)]**: o primeiro valor visto obtém crédito de alocação total, independentemente dos valores subsequentes dessa variável. <br/>**[!UICONTROL Mais recente (último)]**: o último valor visto obtém crédito de alocação total para o evento bem-sucedido, independentemente das variáveis acionadas antes dele. |
   | **[!UICONTROL Expirar após]** | Permite especificar o período ou evento após o qual o valor do eVar expira (ou seja, não recebe mais crédito por eventos bem-sucedidos).  Se um evento bem-sucedido ocorrer após a expiração da eVar, o valor Nenhum receberá o crédito pelo evento (nenhuma eVar estava ativa). |

1. Clique em **[!UICONTROL Habilitar Relatórios do Advertising Analytics]** (primeiro momento) ou **[!UICONTROL Atualizar Relatórios do Advertising Analytics]** (momentos subsequentes). Seu conjunto de relatórios está pronto para receber dados de pesquisa do Advertising Analytics. Agora você está pronto para [criar Contas do Advertising](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md).
