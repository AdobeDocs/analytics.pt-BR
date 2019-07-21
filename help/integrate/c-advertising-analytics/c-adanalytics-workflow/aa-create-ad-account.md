---
seo-title: Configurar uma conta de publicidade
title: Configurar uma conta de publicidade
uuid: 4 e 37 caa 3-e 4 a 5-43 ad -97 c 0-12 db 62 ad 5283
translation-type: tm+mt
source-git-commit: 463e28e9d710cc41e4ab4ace5e3861b8ae8fbdcc

---


# Configurar uma conta de publicidade

Os administradores do Adobe Analytics podem criar novas contas publicitárias e mapear diversas contas a vários conjuntos de relatórios (1:1, 1:Vários, Vários:Vários).

Além disso, os administradores podem [conceder acesso a não administradores](../../../integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) para configuração de contas publicitárias.

![](assets/aa_accounts.png)

1. In Adobe Analytics, navigate to **[!UICONTROL Admin]** &gt; **[!UICONTROL Advertising Accounts]**.
1. (Somente para primeiro uso) Aceite os termos do Contrato de Licença do Usuário Final.
1. Clique em **[!UICONTROL + Adicionar]**.
1. A caixa de diálogo [!UICONTROL Nova conta de mecanismo de pesquisa] é exibida:

   ![](assets/aa_new_se_account.png)

1. Preencha as **[!UICONTROL Configurações do mecanismo de pesquisa]seguindo as instruções a seguir:**

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
      <td colname="col2"> <p>Você tem 2 opções: Google adwords e Microsoft Bing Ads. </p> <p>Observação: o Yahoo Gemini foi absorvido pelo Microsoft Bing em 31 de março de 2019. Como consequência, a opção de conta de publicidade do Yahoo Gemini não está mais disponível.  </p> </td> 
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
        </ul> <p>Consulte <a href="../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md#concept_F7F67448F3B44342967E0419E96F384D" format="dita" scope="local"> Localizar sua ID de conta</a> para obter mais informações sobre as IDs. </p> <p>Após o logon com êxito, o campo do token oauth será exibido 
        <systemoutput>
          Recuperado
        </systemoutput>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Na seção **[!UICONTROL Rastreamento], forneça informações sobre como os dados do Mecanismo de pesquisa são monitorados por sua implementação do Adobe Analytics.** Essa é uma etapa obrigatória para aumentar adequadamente os dados do Adobe Analytics com os dados do Mecanismo de pesquisa.
Preencha as **[!UICONTROL Configurações de rastreamento]seguindo as instruções a seguir:**

   <table id="table_1AB4E31456E84ABF8209B02058259C4D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Configuração </th> 
      <th colname="col2" class="entry"> Descrição </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Tipo </p> </td> 
      <td colname="col2"> 
        <ul id="ul_1C5A0502A4984E57A08417A91CCD6FFE"> 
        <li id="li_5736E38286FF494ABDDC6E85281D7F2A"> <span class="uicontrol"> Automático</span>: permite que o mecanismo da Advertising Cloud decida como os parâmetros de rastreamento são anexados aos modelos de rastreamento/URLs de destino do Mecanismo de pesquisa. Essa é a abordagem mais simples, mas pode não resultar no melhor conjunto de dados integrado. <p>Importante: para configurar uma conta de mecanismo de pesquisa no “Modo automático”, você será responsável pelas seguintes ações: 
          <ul id="ul_4FF9D1E3CC4E452BA339E0A725D29FEE"> 
            <li id="li_6F3A6D6259C0420CB7E6FD2C26A1B6E0">O parâmetro e valor "s_kwcid" será adicionado aos modelos de rastreamento da conta ou aos URLs de página de aterrissagem na conta que está sendo adicionada. Ele será inserido ao final do URL. Como resultado, pode ser necessária uma ação adicional de sua parte se o servidor da Web solicitar um determinado par chave=valor ao final do URL OU uma atualização para dar suporte a um novo par chave=valor no URL. </li> 
            <li id="li_A04D4AA31A934392808639E46C86573F">Além disso, palavras-chave podem ser inseridas no URL de aterrissagem como parte do valor "s_kwcid". Dessa forma, se elas apresentarem caracteres especiais ou símbolos, confirme se seu servidor da Web suporta esses caracteres (um exemplo de um caractere especial é o "+" usado em palavras-chave de “Grande correspondência modificada”). </li> 
          </ul> </p> </li> 
        <li id="li_EAA7A7CA1E584854A7EC1E43E13B63FE"><span class="uicontrol"> Manual</span>: permite gerenciar como os parâmetros de rastreamento são adicionados aos URLs de destino/modelos de rastreamento do Mecanismo de pesquisa. <a href="../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md#concept_87B28BA9E7F84BA5972F69E6F3482A33" format="dita" scope="local"> Consulte estes exemplos de rastreamento manual de cada mecanismo de pesquisa</a>. </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

1. Na seção **[!UICONTROL Mapeamento], selecione quais conjuntos de relatórios vincular a esta conta de mecanismo de pesquisa.** É necessário fornecer pelo menos um conjunto de relatórios antes de poder salvar a conta publicitária. É possível mapear várias contas a diversos conjuntos de relatórios (1:1, 1:Vários, Vários:Vários). Observe que os dados acessados pelo AMO do mecanismo de pesquisa são copiados para qualquer conjunto de relatório, de maneira que não há separação de dados.

   >[!IMPORTANT]
   >
   >Only report suites that have been [mapped to an Experience Cloud organization](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html) will be available for selection. If you do not see your report suite listed, refer to [Troubleshoot Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md).

   Para as **[!UICONTROL Configurações de mapeamento]que seguem essas instruções:**

   <table id="table_AF876DC40F97403882C0AA528BD204FF"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Configuração </th> 
      <th colname="col2" class="entry"> Descrição </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Mapeamento do conjunto de relatórios </p> </td> 
      <td colname="col2"> <p>O mapeamento do conjunto de relatórios determina o conjunto de dados que é vinculado a esta conta de mecanismo de pesquisa. Ou seja, determina a quais conjuntos de relatórios os dados do mecanismo de pesquisa são enviados. </p> <p>Caso não veja o conjunto de relatórios listado, você pode <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html" format="html" scope="external">mapear seu conjunto de relatórios para uma organização da Experience Cloud</a> usando essa ferramenta. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Clique em **[!UICONTROL Salvar]**.
1. Depois de salvar, um aviso de isenção de responsabilidade exibe uma lista de advertências. É solicitado que confirme que leu e entendeu este contrato. Clique na caixa de seleção, em seguida em **[!UICONTROL OK]**.

   Agora você é encaminhado para a [interface do usuário de gerenciamento](../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md#concept_531B99165A4E47B4B8849376B532AFDB) das contas publicitárias, onde sua conta recém-criada deve estar listada.

>[!NOTE]
>
>Você deve esperar pelo menos 24 horas antes dos dados do mecanismo de pesquisa começarem a preencher seus relatórios do Analytics.

