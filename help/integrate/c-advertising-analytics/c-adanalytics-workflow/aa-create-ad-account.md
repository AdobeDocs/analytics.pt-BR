---
title: Como configurar uma conta publicitária no Advertising Analytics
description: Permite criar novas contas publicitárias e mapear várias contas a vários conjuntos de relatórios.
feature: Advertising Analytics
exl-id: f593c714-e85f-4000-85b2-6294cad81e25
source-git-commit: 58bb3ab5787de893917c95946266088ccd1f00d4
workflow-type: tm+mt
source-wordcount: '822'
ht-degree: 93%

---

# Configurar uma conta publicitária

Os administradores do Adobe Analytics podem criar novas contas publicitárias e mapear diversas contas a vários conjuntos de relatórios (1:1, 1:Vários, Vários:Vários).

Além disso, os administradores podem [conceder acesso a não administradores](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) para configuração de contas publicitárias.

![](assets/aa_accounts.png)

1. No Adobe Analytics, navegue até **[!UICONTROL Admin]** > **[!UICONTROL Contas publicitárias]**.
1. (Somente para primeiro uso) Aceite os termos do Contrato de Licença do Usuário Final.
1. Clique em **[!UICONTROL + Adicionar]**.
1. A caixa de diálogo [!UICONTROL Nova conta de mecanismo de pesquisa] é exibida:

   ![](assets/aa_new_se_account.png)

1. Preencha as **[!UICONTROL Configurações do mecanismo de pesquisa]** seguindo as instruções a seguir:

   | Configuração | Descrição |
   | --- | --- |
   | Tipo | Há duas opções: Google AdWords e Microsoft Bing Ads.  Observação: o Yahoo Gemini foi absorvido pelo Microsoft Bing em 31 de março de 2019. Como consequência, a opção de conta de publicidade do Yahoo Gemini não está mais disponível. |
   | Nome da conta | Há a opção para definir este nome de conta com o nome que desejar. Este é o nome amigável da conta que aparecerá na interface do usuário. |
   | Token de OAuth | **Observação:** OAuth é um padrão aberto para delegação de acesso, geralmente usado como uma maneira de conceder a sites ou aplicativos da Web o acesso às respectivas informações em outros sites, sem fornecer as senhas. Você observará que será direcionado para um URL de terceiros (efrontier.com). A Adobe usa o efrontier para potencializar o processo de autenticação do OAuth em todos os três mecanismos de pesquisa. Se usar o Internet Explorer 11 (ou anterior), você não poderá recuperar o token OAuth para qualquer um dos três mecanismos de pesquisa. Em vez disso, use outro navegador da Web.<p>Clicar em **[!UICONTROL Recuperar token]** inicia o processo de autenticação do OAuth2. Isso significa que você será solicitado a fazer logon em sua conta de pequisa do Google/Bing usando suas credenciais. Dependendo do mecanismo de pesquisa escolhido, o processo será um pouco diferente: <ul><li>Google AdWords: fornecer ID de conta do Google</li><li>Microsoft Bing: fornecer ID de conta de cliente do Bing.</li></ul>Consulte [Localizar sua ID de conta](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md) para obter mais informações sobre as IDs. Depois de fazer logon, a variável **[!UICONTROL Token de OAuth]** exibições de campo **[!UICONTROL Recuperado]**. |

1. Na seção **[!UICONTROL Rastreamento]**, forneça informações sobre como os dados do Mecanismo de pesquisa são monitorados por sua implementação do Adobe Analytics. Essa é uma etapa obrigatória para aumentar adequadamente os dados do Adobe Analytics com os dados do Mecanismo de pesquisa.
Preencha as **[!UICONTROL Configurações de rastreamento]** seguindo as instruções a seguir:

   | Configuração | Descrição |
   | --- | --- |
   | Tipo | <ul><li>**Automático**: permite que o mecanismo da Advertising Cloud decida como os parâmetros de rastreamento são anexados aos modelos de rastreamento/URLs de destino do Mecanismo de pesquisa. Essa é a abordagem mais simples, mas pode não resultar no melhor conjunto de dados integrado.<br>**Importante:** para configurar uma conta de mecanismo de pesquisa no “Modo automático”, você é responsável por realizar as seguintes ações:<br>- O parâmetro &quot;s_kwcid&quot; e o valor serão adicionados aos modelos de rastreamento de conta ou URLs da página inicial na conta que está sendo adicionada. Ele será inserido ao final do URL. Como resultado, pode ser necessária uma ação adicional de sua parte se o servidor da Web solicitar um determinado par chave=valor ao final do URL OU uma atualização para dar suporte a um novo par chave=valor no URL. **Observação:** saiba se você deve adicionar esse parâmetro à sua [Política de segurança de conteúdo](https://experienceleague.adobe.com/docs/id-service/using/reference/csp.html?lang=pt-BR).<br>- Além disso, palavras-chave podem ser inseridas no URL de conversão como parte do valor &quot;s_kwcid&quot;. Dessa forma, se elas apresentarem caracteres especiais ou símbolos, confirme se seu servidor da Web suporta esses caracteres (um exemplo de um caractere especial é o &quot;+&quot; usado em palavras-chave de “Grande correspondência modificada”).</li><li>**Manual**: permite gerenciar como os parâmetros de rastreamento são adicionados aos URLs de destino/modelos de rastreamento do Mecanismo de pesquisa. [Consulte estes exemplos de rastreamento manual de cada mecanismo de pesquisa](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md).</li></ul> |

1. Na seção **[!UICONTROL Mapeamento]**, selecione quais conjuntos de relatórios vincular a esta conta de mecanismo de pesquisa. É necessário fornecer pelo menos um conjunto de relatórios antes de poder salvar a conta publicitária. É possível mapear várias contas a diversos conjuntos de relatórios (1:1, 1:Vários, Vários:Vários). Observe que os dados acessados pelo AMO do mecanismo de pesquisa são copiados para qualquer conjunto de relatório, de maneira que não há separação de dados.

   >[!IMPORTANT]
   >
   >Somente conjuntos de relatórios que foram mapeados para uma organização da Experience Cloud estarão disponíveis para seleção. Caso não veja seu conjunto de relatórios listado, consulte [Solução de problemas do Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md).

   Para as **[!UICONTROL Configurações de mapeamento]** que seguem essas instruções:

   | Configuração | Descrição |
   | --- | --- |
   | Mapeamento do conjunto de relatórios | O mapeamento do conjunto de relatórios determina o conjunto de dados que é vinculado a esta conta de mecanismo de pesquisa. Ou seja, determina a quais conjuntos de relatórios os dados do mecanismo de pesquisa são enviados. |


1. Clique em **[!UICONTROL Salvar]**.
1. Depois de salvar, um aviso de isenção de responsabilidade exibe uma lista de advertências. É solicitado que confirme que leu e entendeu este contrato. Clique na caixa de seleção, em seguida em **[!UICONTROL OK]**.

   Agora você é encaminhado para a [interface do usuário de gerenciamento](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md) das contas publicitárias, onde sua conta recém-criada deve estar listada.

>[!NOTE]
>
>É necessário esperar pelo menos 24 horas até que os dados do mecanismo de pesquisa comecem a preencher os relatórios do Analytics.
