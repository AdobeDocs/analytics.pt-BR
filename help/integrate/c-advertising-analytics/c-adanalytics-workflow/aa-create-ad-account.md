---
title: Como configurar uma conta publicitária no Advertising Analytics
description: Este artigo explica como criar novas contas publicitárias e mapear várias contas a vários conjuntos de relatórios.
feature: Advertising Analytics
exl-id: f593c714-e85f-4000-85b2-6294cad81e25
source-git-commit: cf0f528f1ccb0346786c017b4d0d48dd5ab6dfc2
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 25%

---

# Configurar uma conta publicitária

Os administradores do Adobe Analytics podem criar novas contas publicitárias e mapear várias contas a vários conjuntos de relatórios (1 : 1, 1 : muitos, muitos : muitos).

Além disso, os administradores podem [conceder acesso a não administradores](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) para configuração de contas publicitárias.

<!--
![](assets/aa_accounts.png)
-->

1. No Adobe Analytics, navegue até **[!UICONTROL Admin]** > **[!UICONTROL Contas publicitárias]**.
1. (Somente para primeiro uso) Aceite os termos do Contrato de Licença do Usuário Final.
1. Selecione **[!UICONTROL + Adicionar]**.
1. A caixa de diálogo [!UICONTROL Nova configuração do mecanismo de pesquisa] é exibida.

   ![](assets/aa-new-se-account.png)

1. Preencha as **[!UICONTROL Configurações do mecanismo de pesquisa]** seguindo estas diretrizes:

   | Configuração | Descrição |
   | --- | --- |
   | **[!UICONTROL Tipo]** | Você tem duas opções: **[!UICONTROL Google Adwords]** e **[!UICONTROL Bing Ads]**.  Observação: o Yahoo Gemini foi absorvido pelo Microsoft Bing em 31 de março de 2019. Como consequência, a opção de conta de publicidade do Yahoo Gemini não está mais disponível. |
   | Nome da conta | Você pode optar por definir esse nome de conta como qualquer nome que lhe convenha.  Nome da conta é o nome amigável da conta que aparece na interface do usuário do. |
   | Token de OAuth | **Observação**: OAuth é um padrão aberto para delegação de acesso, geralmente usado como uma maneira de conceder a sites ou aplicativos da Web o acesso a informações em sites, sem fornecer senhas. Você percebe que é roteado para um URL de terceiros (efrontier.com). O Adobe usa o Adobe Media Otimizer para potencializar o processo de autenticação OAuth para todos os três mecanismos de pesquisa. Se você usa o Internet Explorer 11 (ou anterior), não será possível recuperar o token OAuth para qualquer um dos três mecanismos de pesquisa. Em vez disso, use outro navegador da Web.<p>Selecione **[!UICONTROL Recuperar token]** para iniciar o processo de autenticação OAuth2. Você será solicitado a fazer logon em sua conta de pesquisa do Google/Bing usando suas credenciais. Dependendo da sua escolha, o processo será um pouco diferente: <ul><li>Google AdWords: fornecer ID de conta do Google</li><li>Microsoft Bing: fornecer ID de conta de cliente do Bing.</li></ul>Consulte [Localizar ID da Conta](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md) para obter mais informações sobre essas IDs. Depois de fazer logon, o campo **[!UICONTROL token do OAuth]** será exibido como **[!UICONTROL Recuperado]**. |

1. Na seção **[!UICONTROL Rastreamento]**, forneça informações sobre como rastrear os dados usando a implementação do Adobe Analytics. O rastreamento é uma etapa necessária para aumentar os dados do Adobe Analytics corretamente com os dados do mecanismo de pesquisa.
Preencha as **[!UICONTROL Configurações de rastreamento]** seguindo as instruções a seguir:

   | Configuração | Descrição |
   | --- | --- |
   | Tipo | <ul><li>**Automático**: permite que o mecanismo da Advertising Cloud decida como os parâmetros de rastreamento são anexados aos modelos de rastreamento/URLs de destino do. [!UICONTROL O Rastreamento automático de tipos] é a abordagem mais simples, mas pode não resultar no melhor conjunto de dados integrado.<br>**Importante:** para configurar uma conta de mecanismo de pesquisa com [!UICONTROL Rastreamento de Tipo Automático], você será responsável pelas seguintes ações:<ul><li>O parâmetro e valor `s_kwcid` são adicionados aos modelos de rastreamento da conta ou às URLs da página de aterrissagem na conta que está sendo adicionada. O parâmetro e valor são inseridos no final do URL. Pode ser necessária uma ação adicional se o servidor Web exigir um determinado par de `key=value` no final da URL. Ou é necessária uma atualização para dar suporte a qualquer novo par `key=value` na URL. **Observação**: saiba se você deve adicionar este parâmetro à sua [Política de Segurança de Conteúdo](https://experienceleague.adobe.com/en/docs/id-service/using/reference/csp).</li><li>Além disso, palavras-chave podem ser inseridas no URL inicial como parte do valor `s_kwcid`. Se as palavras-chave contiverem caracteres especiais ou símbolos, confirme se o servidor da Web é compatível com esses caracteres. Um exemplo de caracteres especiais comuns é `+`, que é usado em palavras-chave de &quot;Grande correspondência modificada&quot;.</li></ul></li><li>**Manual**: permite gerenciar como os parâmetros de rastreamento são adicionados aos modelos de rastreamento/URLs de destino do mecanismo de pesquisa. [Consulte estes exemplos de rastreamento manual de cada mecanismo de pesquisa](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md).</li></ul> |

1. Selecione **[!UICONTROL Salvar]**.
1. Um aviso de isenção de responsabilidade exibe uma lista de avisos. Confirme que leu e compreende este contrato. Marque a caixa de seleção e selecione **[!UICONTROL OK]**.

   Agora você é encaminhado para a [interface do usuário de gerenciamento](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md) das contas publicitárias, onde sua conta recém-criada deve estar listada.

>[!NOTE]
>
>É necessário esperar pelo menos 24 horas até que os dados do mecanismo de pesquisa comecem a preencher os relatórios do Analytics.
