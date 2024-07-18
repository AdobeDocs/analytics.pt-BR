---
description: Como migrar contas de usuário do Analytics como Enterprise ou Federated IDs para o Adobe Admin Console.
title: Migrar contas de usuário do Analytics para Enterprise e Federated IDs
feature: Admin Tools
exl-id: 988ed685-4eca-4b0b-a653-9c6a156852f1
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 97%

---

# Migrar contas de usuário do Analytics para Enterprise e Federated IDs

Como migrar contas de usuário do Analytics como Enterprise ou Federated IDs para o Adobe Admin Console.

## Pré-requisitos  {#prereqs}

Pré-requisitos para gerenciar usuários no Adobe Admin Console.

Para novos domínios e diretórios, siga os passos para:

* Configurar um diretório
* Configurar domínios
* Vincular domínios em diretórios

Consulte [Configurar um sistema de identidade](https://helpx.adobe.com/br/enterprise/using/set-up-identity.html) para obter ajuda.

Se um diretório já foi criado em outra organização por outra unidade comercial ou equipe, siga os passos em [confiabilidade de diretório](https://helpx.adobe.com/br/enterprise/using/set-up-identity.html#Directorytrusting) para estabelecer o diretório na organização que você está usando para o Analytics.

## Migrar contas do usuário para Enterprise e Federated IDs {#task-0cfb3e4400fd4ab58e4d9704528b05fa}

Neste procedimento, você poderá:

* Baixar uma lista de login do usuário de **[!UICONTROL Analytics]** > **[!UICONTROL Usuários e ativos do Analytics]**.

* Baixar uma lista de usuários atuais em **[!UICONTROL Admin Console]** > **[!UICONTROL Usuários]**.

* Compare as listas (procurando duplicatas para evitar sobrescrever os dados da conta no Adobe Admin Console).
* Carregue um [!DNL .csv] concluído (em **[!UICONTROL Admin Console]** > **[!UICONTROL Usuários]**) com Enterprise ID ou Federated ID de usuários para o Adobe Admin Console.

Se precisar migrar contas de usuário com Adobe ID para uma Enterprise ID ou Federated ID, contate o Atendimento ao cliente da Adobe e solicite uma [mudança de identidade de usuário em massa](https://helpx.adobe.com/br/enterprise/using/bulk-operations.html).

**Para migrar contas do usuário**

1. Baixe o arquivo de logins do usuário do Analytics ([!DNL User Logins List.tab]) no Gerenciamento de usuários do Analytics usando um dos seguintes métodos (dependendo se você já migrou os usuários).
   1. *Antes de migrar,* vá até **[!UICONTROL Admin]** > **[!UICONTROL Gerenciamento de usuários (herdado)]** > **[!UICONTROL Editar usuários]** e clique em **[!UICONTROL Baixar relatório]**.

      ![](/help/admin/admin/user-management2/user-migration/assets/download-report.png)

      O link Baixar relatório exibe somente os clientes que não migraram usuários.

   1. *Se você já migrou usuários,* vá até **[!UICONTROL Analytics]** > **[!UICONTROL Usuários e ativos do Analytics]**.

      ![Informações da etapa](/help/admin/admin/user-management2/user-migration/assets/admin-analytics-users-assets.png)

   1. Na página [!DNL Users], selecione os usuários e, em seguida, clique em **[!UICONTROL Exportar para CSV]**.

      ![Informações da etapa](/help/admin/admin/user-management2/user-migration/assets/export-csv-migrate.png)

   1. Abra o arquivo [!DNL User List.csv] baixado no Excel.

      Esteja preparado para copiar os valores *`Email`*, *`First Name`* e *`Last Name`* para um arquivo [!DNL sample.csv] (descrito na próxima etapa).

      >[!IMPORTANT]
      >
      >Os valores no arquivo CSV devem ser delimitados por vírgulas.

      >[!TIP]
      >
      >Durante essa etapa, a Adobe recomenda a simplificação de sua lista de usuários para garantir que apenas os usuários com uma ID de email válida sejam incluídos na migração de Enterprise ou Federated ID.

1. No [!UICONTROL Admin Console], baixe uma lista de usuários do Adobe Admin Console:

   1. Acesse [!UICONTROL Admin Console] > **[!UICONTROL Usuários]** e, em seguida, clique em [Exportar a lista de usuários para CSV](https://helpx.adobe.com/br/enterprise/using/users.html).

      ![](/help/admin/admin/user-management2/user-migration/assets/export-csv.png)

   1. Compare os dois arquivos: os usuários existentes do Adobe Admin Console no arquivo [!DNL .csv] exportado ([!DNL sample.csv], neste exemplo) com os usuários no arquivo [!DNL User Logins List.csv] do Analytics.

      >[!IMPORTANT]
      >
      >Caso encontre duplicatas, exclua todas no arquivo [!DNL User Logins List.csv] do Analytics. Essa etapa ajuda a impedir a sobreposição de permissões do usuário da Experience Cloud no Adobe Admin Console e fornece uma lista de contas para migração.

1. Baixe o modelo CSV no Adobe Admin Console:
   1. Na guia Usuários, clique em **[!UICONTROL Adicionar usuários ao CSV]** e **[!UICONTROL Baixar modelo CSV]**.

      ![Informações da etapa](/help/admin/admin/user-management2/user-migration/assets/add-users-csv.png)

   1. Selecione **[!UICONTROL Modelo padrão]**.

      Esta etapa baixa um arquivo de modelo [!DNL sample.csv].

      ![](/help/admin/admin/user-management2/user-migration/assets/download-csv-template.png)

1. Copie os valores de coluna *`Email`*, *`First Name`* e *`Last Name`* de [!DNL User Logins List.tab] para as colunas correspondentes no modelo [!DNL sample.csv].

   **Exemplo de arquivo do modelo**

   ![](/help/admin/admin/user-management2/user-migration/assets/sample.png)

1. No modelo ([!DNL sample.csv]), preencha os seguintes campos obrigatórios:

<table id="table_1B5EEFDB5BD8436EB760BE5FFAB1CF02"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrição </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Email </p> </td> 
   <td colname="col2"> <p>Copiado de <span class="filepath">User Logins List.tab</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Primeiro nome </p> </td> 
   <td colname="col2"> <p>Copiado de <span class="filepath">User Logins List.tab</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sobrenome </p> </td> 
   <td colname="col2"> <p>Copiado de <span class="filepath">User Logins List.tab</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tipo de identidade </p> </td> 
   <td colname="col2"> <p><span class="term"> Federated ID</span> ou <span class="term"> Enterprise ID</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Domínio </p> </td> 
   <td colname="col2"> <p>Verifique se os domínios na coluna <span class="term"> Domínio</span> e <span class="term"> Email</span> correspondem ao(s) domínio(s) estabelecido(s) nos pré-requisitos</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Código do país </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

Para obter mais informações sobre os campos no arquivo [!DNL .csv], consulte o [formato de arquivo CSV](https://helpx.adobe.com/br/enterprise/using/users.html).

>[!NOTE]
>
>Outras colunas, como [!UICONTROL Configurações de Produto] e [!UICONTROL Funções administrativas], podem ficar em branco.

1. Na guia Usuários do Adobe Admin Console, faça upload do arquivo de modelo clicando em **[!UICONTROL Adicionar usuário por CSV]** (como mostrado na Etapa 3).
1. No Analytics, execute a ferramenta de migração (conforme descrito em [Migrar contas de usuário do Analytics](/help/admin/admin/user-management2/user-migration/t-migrate-users.md).
1. Clique em **[!UICONTROL Migrar]** > **[!UICONTROL Migrar como Enterprise IDs]**.

   ![Informações da etapa](/help/admin/admin/user-management2/user-migration/assets/migrate-as-enterprise.png)

   Ao clicar em **[!UICONTROL Migrar]**, o usuário é vinculado à conta da Enterprise ID/Federated ID no Adobe Admin Console. As permissões da conta de usuário herdada no Analytics correspondem às permissões concedidas ao login da Enterprise/Federated ID em **[!UICONTROL Admin Console]** > **[!UICONTROL Analytics]** > **[!UICONTROL Perfis de produto]**. A ID do usuário exibida no bucket de Migração concluída. Você pode desabilitar o acesso ao [!DNL my.omniture.com] herdado.

   Depois de migrar os usuários, o status na coluna Status da migração muda de **[!UICONTROL Não iniciado]** para **[!UICONTROL Migrado]**.

   Os usuários da Adobe ID que aparecem na ferramenta de migração também podem ser migrados no processo. Eles ainda devem fazer logon com a Adobe ID até a identidade ser trocada. Contate o atendimento ao cliente da Adobe para obter ajuda com uma troca de identidade.
