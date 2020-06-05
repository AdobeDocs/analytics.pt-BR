---
title: Configurar uma conta publicitária
uuid: 4e37caa3-e4a5-43ad-97c0-12db62ad5283
translation-type: tm+mt
source-git-commit: 0345a71bd2dd99410658cc858fe05ee2751d0013
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 81%

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

   <table id="table_B3BE66B7D4C54766B8FFD2C6DCD657AF"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Configuração </th> 
      <th colname="col2" class="entry"> Descrição </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Tipo </p> </td> 
      <td colname="col2"> <p>Há duas opções: Google AdWords e Microsoft Bing Ads. </p> <p>Observação: o Yahoo Gemini foi absorvido pelo Microsoft Bing em 31 de março de 2019. Como consequência, a opção de conta de publicidade do Yahoo Gemini não está mais disponível.  </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome da conta </p> </td> 
      <td colname="col2"> <p>Há a opção para definir este nome de conta com o nome que desejar. Este é o nome amigável da conta que aparecerá na interface do usuário. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Token de OAuth </p> </td> 
      <td colname="col2"> <p>Observação: OAuth é um padrão aberto para delegação de acesso, geralmente usado como uma maneira de conceder a sites ou aplicativos da Web o acesso às respectivas informações em outros sites, sem fornecer as senhas. </p> <p>Observação: você perceberá que será direcionado para um URL de terceiros (efrontier.com). A Adobe usa o efrontier para potencializar o processo de autenticação do OAuth em todos os três mecanismos de pesquisa. </p> <p>Observação: se você usar o Internet Explorer 11 (ou anterior), não será possível recuperar o token OAuth para qualquer um dos três mecanismos de pesquisa. Em vez disso, use outro navegador da Web. </p> <p>Clicar em <span class="uicontrol">Recuperar token</span> inicia o processo de autenticação do OAuth2. Isso significa que você será solicitado a fazer logon em sua conta de pequisa do Google/Bing usando suas credenciais. Dependendo do mecanismo de pesquisa escolhido, o processo será um pouco diferente: </p> 
        <ul id="ul_FC9B5612F6554495B04C357CB0AB72EB"> 
        <li id="li_CD54231BFF134F83B3B5B14B34A0E1D2">Google AdWords: fornecer ID de conta do Google. </li> 
        <li id="li_89B9D54BAA914E5DB2959B193489582E">Microsoft Bing: fornecer ID de conta de cliente do Bing. </li> 
        </ul> <p>Consulte <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md"  > Localizar sua ID de conta</a> para obter mais informações sobre as IDs. </p> <p>Depois de fazer logon, o campo Token de OAuth exibirá  
        <systemoutput>
          Recuperado
        </systemoutput>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Na seção **[!UICONTROL Rastreamento]**, forneça informações sobre como os dados do Mecanismo de pesquisa são monitorados por sua implementação do Adobe Analytics. Essa é uma etapa obrigatória para aumentar adequadamente os dados do Adobe Analytics com os dados do Mecanismo de pesquisa.
Preencha as **[!UICONTROL Configurações de rastreamento]** seguindo as instruções a seguir:

   | Configuração | Descrição |
   |--- |--- |
   | Tipo | <ul><li>**Automático:** Permite que o Advertising Cloud Engine decida como os parâmetros de rastreamento são anexados aos modelos/URLs de destino do Search Engine. Essa é a abordagem mais simples, mas pode não resultar no melhor conjunto de dados integrado.<br>**Importante:**Para configurar uma conta de mecanismo de pesquisa em &#39;Modo automático&#39;, você é responsável por realizar as seguintes ações:<br>- O parâmetro e o valor &quot;s_kwcid&quot; serão adicionados aos modelos de rastreamento de conta ou URLs de landing page na conta que está sendo adicionada. Ele será inserido ao final do URL. Como resultado, pode ser necessária uma ação adicional de sua parte se o servidor da Web solicitar um determinado par chave=valor ao final do URL OU uma atualização para dar suporte a um novo par chave=valor no URL.** Observação:**Saiba mais sobre se você deve adicionar esse parâmetro à sua Política[de segurança de](https://docs.adobe.com/content/help/en/id-service/using/reference/csp.html)conteúdo.<br>- Além disso, as palavras-chave podem ser inseridas no URL inicial como parte do valor &quot;s_kwcid&quot;, portanto, se contiverem caracteres ou símbolos especiais, confirme se o servidor da Web pode suportar esses caracteres (um exemplo de caracteres especiais comuns é &quot;+&quot;, que é usado em palavras-chave &quot;Ampla correspondência modificada&quot;).</li><li>**Manual:** Permite gerenciar como os parâmetros de rastreamento são adicionados aos modelos de rastreamento/URLs de destino do Mecanismo de pesquisa. [Consulte estes exemplos de rastreamento manual de cada mecanismo de pesquisa](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md).</li></ul> |

1. Na seção **[!UICONTROL Mapeamento]**, selecione quais conjuntos de relatórios vincular a esta conta de mecanismo de pesquisa. É necessário fornecer pelo menos um conjunto de relatórios antes de poder salvar a conta publicitária. É possível mapear várias contas a diversos conjuntos de relatórios (1:1, 1:Vários, Vários:Vários). Observe que os dados acessados pelo AMO do mecanismo de pesquisa são copiados para qualquer conjunto de relatório, de maneira que não há separação de dados.

   >[!IMPORTANT]
   >
   >Somente conjuntos de relatórios que foram [mapeados para uma organização da Experience Cloud](https://docs.adobe.com/content/help/pt-BR/core-services/interface/about-core-services/report-suite-mapping.html) estarão disponíveis para seleção. Caso não veja seu conjunto de relatórios listado, consulte [Solução de problemas do Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md).

   Para as **[!UICONTROL Configurações de mapeamento]** que seguem essas instruções:

   <table id="table_AF876DC40F97403882C0AA528BD204FF"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Configuração </th> 
      <th colname="col2" class="entry"> Descrição </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Conjunto de relatórios  Mapeamento </p> </td> 
      <td colname="col2"> <p>O mapeamento do conjunto de relatórios determina o conjunto de dados que é vinculado a esta conta de mecanismo de pesquisa. Ou seja, determina a quais conjuntos de relatórios os dados do mecanismo de pesquisa são enviados. </p> <p>Caso não veja o conjunto de relatórios listado, você pode <a href="https://docs.adobe.com/content/help/pt-BR/core-services/interface/about-core-services/report-suite-mapping.html"  >mapear seu conjunto de relatórios para uma organização da Experience Cloud</a> usando essa ferramenta. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clique em **[!UICONTROL Salvar]**.
1. Depois de salvar, um aviso de isenção de responsabilidade exibe uma lista de advertências. É solicitado que confirme que leu e entendeu este contrato. Clique na caixa de seleção, em seguida em **[!UICONTROL OK]**.

   Agora você é encaminhado para a [interface do usuário de gerenciamento](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md) das contas publicitárias, onde sua conta recém-criada deve estar listada.

>[!NOTE] É necessário esperar pelo menos 24 horas até que os dados do mecanismo de pesquisa comecem a preencher os relatórios do Analytics.

