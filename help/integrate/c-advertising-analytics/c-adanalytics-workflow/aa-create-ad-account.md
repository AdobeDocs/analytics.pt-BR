---
title: Como configurar uma conta publicitária no Advertising Analytics
description: Este artigo explica como criar novas contas publicitárias e mapear várias contas a vários conjuntos de relatórios.
feature: Advertising Analytics
exl-id: f593c714-e85f-4000-85b2-6294cad81e25
TQID: 'https://experienceleague.adobe.com/UAPEgVKZ4EW-GMvHGgz9tMHi36M2HazOuEBHOtJ1OUY'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2: id: fe0a7292-80bc-407a-b456-64170267d1ccid: a9364d69-0c51-44bf-8b5f-6d99c04493b8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 660
ht-degree: 13%

---

# Configurar uma conta publicitária

Os administradores do Adobe Analytics podem criar novas contas publicitárias e mapear várias contas a vários conjuntos de relatórios (1 : 1, 1 : muitos, muitos : muitos).

Administradores também podem [conceder acesso a não administradores](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) para configurar contas publicitárias.

<!--
![](assets/aa_accounts.png)
-->

1. No Adobe Analytics, navegue até **[!UICONTROL Admin]** > **[!UICONTROL Contas publicitárias]**.
1. (Somente na primeira vez) Aceite os termos do Contrato de licença de usuário final.
1. Selecione **[!UICONTROL + Adicionar]**.
1. A caixa de diálogo [!UICONTROL Nova configuração do mecanismo de pesquisa] é exibida.

   ![](assets/aa-new-se-account.png)

1. Preencha as **[!UICONTROL Configurações do mecanismo de pesquisa]** seguindo estas diretrizes:

   | Configuração | Descrição |
   | --- | --- |
   | **[!UICONTROL Tipo]** | Você tem duas opções: **[!UICONTROL Google Adwords]** e **[!UICONTROL Bing Ads]**. Observação: o Yahoo Gemini foi absorvido pelo Microsoft em 31 de março de 2019. Como consequência, a opção de conta de publicidade do Yahoo Gemini não está mais disponível. |
   | Nome da conta | Você pode optar por definir esse nome de conta como qualquer nome que lhe convenha.  Nome da conta é o nome amigável da conta que aparece na interface do usuário do. |
   | Token OAuth | **Observação**: OAuth é um padrão aberto para delegação de acesso, geralmente usado como uma maneira de conceder a sites ou aplicativos da Web o acesso a informações em sites, sem fornecer senhas. Você percebe que é roteado para um URL de terceiros (efrontier.com). O Adobe usa o Adobe Media Otimizer para potencializar o processo de autenticação OAuth para todos os três mecanismos de pesquisa. Se você usa o Internet Explorer 11 (ou anterior), não será possível recuperar o token OAuth para qualquer um dos três mecanismos de pesquisa. Em vez disso, use outro navegador da Web.<p>Selecione **[!UICONTROL Recuperar token]** para iniciar o processo de autenticação OAuth2. Você será solicitado a fazer logon em sua conta de pesquisa do Google Ads ou Microsoft Advertising usando suas credenciais. Dependendo da sua escolha, o processo será um pouco diferente: <ul><li>Anúncios do Google: fornecer a ID de conta da Google</li><li>Microsoft Advertising: forneça sua ID de conta e a ID de conta do gerente.</li></ul>Consulte [Localizar ID da Conta](aa-locate-account-id.md) para obter mais informações sobre essas IDs. Depois de fazer logon, o campo **[!UICONTROL token do OAuth]** será exibido como **[!UICONTROL Recuperado]**. |

1. Na seção **[!UICONTROL Rastreamento]**, forneça informações sobre como rastrear os dados usando a implementação do Adobe Analytics. O rastreamento é uma etapa necessária para aumentar os dados do Adobe Analytics corretamente com os dados do mecanismo de pesquisa.
Preencha as **[!UICONTROL Configurações de rastreamento]** seguindo estas diretrizes:

   | Configuração | Descrição |
   | --- | --- |
   | Tipo | <ul><li>**Automático**: permite que o mecanismo do Adobe Advertising decida como os parâmetros de rastreamento são anexados aos modelos de rastreamento/URLs de destino do. O [!UICONTROL Rastreamento de Tipo Automático] é a abordagem mais simples, mas pode não resultar no melhor conjunto de dados integrado.<br>**Importante:** Para configurar uma conta de mecanismo de pesquisa com o [!UICONTROL Rastreamento de Tipo Automático], você será responsável pelas seguintes ações:<ul><li>O parâmetro e valor `s_kwcid` são adicionados aos modelos de rastreamento da conta ou às URLs da página de aterrissagem na conta que está sendo adicionada. O parâmetro e valor são inseridos no final do URL. Pode ser necessária uma ação adicional se o servidor Web exigir um determinado par de `key=value` no final da URL. Ou é necessária uma atualização para dar suporte a qualquer novo par `key=value` na URL. **Observação**: saiba se você deve adicionar este parâmetro à sua [Política de Segurança de Conteúdo](https://experienceleague.adobe.com/en/docs/id-service/using/reference/csp).</li><li>Além disso, palavras-chave podem ser inseridas no URL inicial como parte do valor `s_kwcid`. Se as palavras-chave contiverem caracteres especiais ou símbolos, confirme se o servidor da Web é compatível com esses caracteres. Um exemplo de caracteres especiais comuns é `+`, que é usado em palavras-chave de &quot;Grande correspondência modificada&quot;.</li></ul></li><li>**Manual**: permite gerenciar como os parâmetros de rastreamento são adicionados aos modelos de rastreamento/URLs de destino do mecanismo de pesquisa. [Consulte estes exemplos de rastreamento manual de cada mecanismo de pesquisa](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md).</li></ul> |

1. Selecione **[!UICONTROL Salvar]**.
1. Um aviso de isenção de responsabilidade exibe uma lista de avisos. Confirme que leu e compreende este contrato. Marque a caixa de seleção e selecione **[!UICONTROL OK]**.

   Agora você é levado para a [Interface do usuário de gerenciamento](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md) das Contas do Advertising, onde sua conta recém-criada deve ser listada.

>[!NOTE]
>
>Espere pelo menos 24 horas até que os dados do mecanismo de pesquisa comecem a preencher os relatórios do Analytics.
