---
description: Configure um conjunto de relatórios mapeados da Experience Cloud para uso no Advertising Analytics.
title: Habilitar conjunto de relatórios para o Advertising Analytics
feature: Advertising Analytics
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
source-git-commit: cbfe932eecf2e89d72b1aa373d723de4cf0af073
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 27%

---

# Habilitar conjunto de relatórios para o Advertising Analytics

Para ver dados de pesquisa do Advertising Analytics no Analytics, é necessário configurar cada conjunto de relatórios mapeados para Experience Cloud para os relatórios do Advertising Analytics.

1. Navegue até **[!UICONTROL Admin]** > **[!UICONTROL Conjuntos de relatórios]**.

1. Selecione o conjunto de relatórios que está mapeado à sua organização Experience Cloud.
1. Clique em **[!UICONTROL Editar configurações]** > **[!UICONTROL Configuração do Advertising Analytics]**.

   ![Relatórios](assets/aa-reporting.png)

1. Selecione **[!UICONTROL Não está familiarizado com o Advertising Analytics? Clique aqui para saber mais]** para obter mais informações sobre o Advertising Analytics.

1. Defina a alocação e a expiração da variável que você deseja que a variável da ID do AMO use. As variáveis de conversão (eVars) permitem que o Adobe Analytics atribua eventos bem-sucedidos a valores de variáveis específicos. Às vezes, as variáveis encontram mais de um valor antes de atingir um evento bem-sucedido. Para esses casos, a alocação determina qual valor variável recebe crédito pelo evento.

   | Configuração | Definição |
   |--- |--- |
   | **[!UICONTROL Alocação]** | Selecionar entre:<br/> **[!UICONTROL Valor Original (Primeiro)]**: o primeiro valor visto obtém crédito de alocação total, independentemente dos valores subsequentes dessa variável. <br/>**[!UICONTROL Mais recente (último)]**: o último valor visto obtém crédito de alocação total para o evento bem-sucedido, independentemente das variáveis acionadas antes dele. |
   | **[!UICONTROL Expirar após]** | Permite especificar o período ou evento após o qual o valor do eVar expira (ou seja, não recebe mais crédito por eventos bem-sucedidos).  Se um evento bem-sucedido ocorrer após a expiração da eVar, o valor Nenhum receberá o crédito pelo evento (nenhuma eVar estava ativa). |

1. Clique em **[!UICONTROL Habilitar Relatórios do Advertising Analytics]** (primeira vez) ou **[!UICONTROL Atualizar Relatórios do Advertising Analytics]** (vezes subsequentes). Seu conjunto de relatórios agora está pronto para receber dados do Advertising Analytics Search. Agora você está pronto para [criar Contas do Advertising](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md).
