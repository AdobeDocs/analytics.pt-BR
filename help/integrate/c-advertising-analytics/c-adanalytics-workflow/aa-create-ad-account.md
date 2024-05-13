---
title: Como configurar uma conta publicitária no Advertising Analytics
description: Este artigo explica como criar novas contas publicitárias e mapear várias contas a vários conjuntos de relatórios.
feature: Advertising Analytics
exl-id: f593c714-e85f-4000-85b2-6294cad81e25
source-git-commit: c53b533a1d037ab3ed811bcc0960418f037a708f
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 31%

---

# Configurar uma conta publicitária

Os administradores do Adobe Analytics podem criar novas contas publicitárias e mapear várias contas a vários conjuntos de relatórios (1 : 1, 1 : muitos, muitos : muitos).

Além disso, os administradores podem [conceder acesso a não administradores](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) para configuração de contas publicitárias.

<!--
![](assets/aa_accounts.png)
-->

1. No Adobe Analytics, navegue até **[!UICONTROL Admin]** > **[!UICONTROL Contas publicitárias]**.
1. (Somente para primeiro uso) Aceite os termos do Contrato de Licença do Usuário Final.
1. Selecionar **[!UICONTROL + Adicionar]**.
1. A variável [!UICONTROL Nova configuração de mecanismo de pesquisa] é exibida:

   ![](assets/aa-new-se-account.png)

1. Preencha o **[!UICONTROL Configurações do mecanismo de pesquisa]** seguindo estas diretrizes:

   | Configuração | Descrição |
   | --- | --- |
   | **[!UICONTROL Tipo]** | Você tem duas opções: **[!UICONTROL Google Adwords]** e **[!UICONTROL Bing Ads]**.  Observação: o Yahoo Gemini foi absorvido pelo Microsoft Bing em 31 de março de 2019. Como consequência, a opção de conta de publicidade do Yahoo Gemini não está mais disponível. |
   | Nome da conta | Você pode optar por definir esse nome de conta como qualquer nome que lhe convenha.  Nome da conta é o nome amigável da conta que aparece na interface do usuário do. |
   | Token de OAuth | **Nota**: OAuth é um padrão aberto para delegação de acesso, geralmente usado como uma maneira de conceder a sites ou aplicativos da Web o acesso a informações em sites, sem fornecer senhas. Você percebe que é roteado para um URL de terceiros (efrontier.com). O Adobe usa o Adobe Media Optimizer para alimentar o processo de autenticação OAuth para todos os três mecanismos de pesquisa. Se você usa o Internet Explorer 11 (ou anterior), não será possível recuperar o token OAuth para qualquer um dos três mecanismos de pesquisa. Em vez disso, use outro navegador da Web.<p>Selecionar **[!UICONTROL Recuperar token]** para iniciar o processo de autenticação do OAuth2. Você será solicitado a fazer logon em sua conta de pesquisa do Google/Bing usando suas credenciais. Dependendo da sua escolha, o processo será um pouco diferente: <ul><li>Google AdWords: fornecer ID de conta do Google</li><li>Microsoft Bing: fornecer ID de conta de cliente do Bing.</li></ul>Consulte [Localizar sua ID de conta](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md) para obter informações sobre essas IDs. Depois de fazer logon, o campo **[!UICONTROL token do OAuth]** será exibido como **[!UICONTROL Recuperado]**. |

1. No **[!UICONTROL Rastreamento]** forneça informações sobre como rastrear os dados usando a implementação do Adobe Analytics. O rastreamento é uma etapa necessária para aumentar os dados do Adobe Analytics corretamente com os dados do mecanismo de pesquisa.
Preencha as **[!UICONTROL Configurações de rastreamento]** seguindo as instruções a seguir:

   | Configuração | Descrição |
   | --- | --- |
   | Tipo | <ul><li>**Automático**: permite que o mecanismo do Advertising Cloud decida como os parâmetros de rastreamento são anexados aos URLs de destino/modelos de rastreamento do. [!UICONTROL Rastreamento de tipo automático] O é a abordagem mais simples, mas pode não resultar no melhor conjunto de dados integrado.<br>**Importante:** Para configurar uma conta de mecanismo de pesquisa com [!UICONTROL Rastreamento de tipo automático], você será responsável pelas seguintes ações:<ul><li>A variável `s_kwcid` O parâmetro e o valor são adicionados aos modelos de rastreamento da conta ou aos URLs da página inicial na conta que está sendo adicionada. O parâmetro e valor são inseridos no final do URL. Pode ser necessária uma ação adicional se o servidor da Web exigir um determinado `key=value` emparelhe no final do URL. Ou uma atualização para oferecer suporte a novos `key=value` O par de no URL é obrigatório. **Nota**: saiba se você deve adicionar esse parâmetro ao seu [Política de segurança de conteúdo](https://experienceleague.adobe.com/en/docs/id-service/using/reference/csp).</li><li>Além disso, palavras-chave podem ser inseridas no URL inicial como parte do valor `s_kwcid`. Se as palavras-chave contiverem caracteres especiais ou símbolos, confirme se o servidor da Web é compatível com esses caracteres. Um exemplo de caracteres especiais comuns é `+`, que é usado em palavras-chave de &quot;Grande correspondência modificada&quot;.</li></ul></li><li>**Manual**: permite gerenciar como os parâmetros de rastreamento são adicionados aos URLs de destino/modelos de rastreamento do mecanismo de pesquisa. [Consulte estes exemplos de rastreamento manual de cada mecanismo de pesquisa](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md).</li></ul> |

1. No **[!UICONTROL Mapeamento]** selecione um ou mais conjuntos de relatórios a serem vinculados a esta conta de mecanismo de pesquisa. É necessário fornecer pelo menos um conjunto de relatórios antes de poder salvar a conta publicitária. Você pode mapear várias contas para vários conjuntos de relatórios (1 : 1, 1 : muitos, muitos : muitos). Observe que os dados obtidos pelo Adobe Media Optimizer do mecanismo de pesquisa são simplesmente copiados para qualquer conjunto de relatórios mapeado, de modo que não há divisão de dados.

   >[!IMPORTANT]
   >
   >Somente conjuntos de relatórios que foram mapeados para uma organização da Experience Cloud estarão disponíveis para seleção. Caso não veja seu conjunto de relatórios listado, consulte [Solução de problemas do Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md).

   Para as **[!UICONTROL Configurações de mapeamento]** que seguem essas instruções:

   | Configuração | Descrição |
   | --- | --- |
   | Mapeamento do conjunto de relatórios | O mapeamento do conjunto de relatórios determina o conjunto de dados que é vinculado a esta conta de mecanismo de pesquisa. Ou seja, determina a quais conjuntos de relatórios os dados do mecanismo de pesquisa são enviados. |


1. Selecione **[!UICONTROL Salvar]**.
1. Um aviso de isenção de responsabilidade exibe uma lista de avisos. Confirme que leu e compreende este contrato. Marque a caixa de seleção e selecione **[!UICONTROL OK]**.

   Agora você é encaminhado para a [interface do usuário de gerenciamento](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md) das contas publicitárias, onde sua conta recém-criada deve estar listada.

>[!NOTE]
>
>É necessário esperar pelo menos 24 horas até que os dados do mecanismo de pesquisa comecem a preencher os relatórios do Analytics.
