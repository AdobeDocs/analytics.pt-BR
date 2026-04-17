---
title: Requisitos de segurança para servidores FTP e SFTP
description: Saiba mais sobre os requisitos de segurança para servidores FTP e SFTP.
feature: Data Configuration and Collection
role: Admin
source-git-commit: 26ae4edacbc3591d4d3358afe009bf7831d45efb
workflow-type: tm+mt
source-wordcount: '1899'
ht-degree: 2%

---

# Requisitos de segurança para servidores FTP e SFTP

Esta página aborda os requisitos de segurança para servidores FTP e SFTP existentes que recebem dados entregues pelos feeds de dados da Adobe Analytics ou pela Data Warehouse.

* **Servidores FTP existentes**: devem ser atualizados para usar o SFTP, conforme descrito na seção abaixo, [Atualizar servidores FTP para usar o SFTP](#upgrade-ftp-servers-to-use-sftp).

  A atualização de FTP para SFTP é um requisito, pois o SFTP permite maior segurança.

  Como alternativa, para um nível mais alto de segurança, você pode fazer a transição para um destino de nuvem moderno. (Para obter mais informações, consulte [Configurar contas de importação e exportação da nuvem](https://experienceleague.adobe.com/pt-br/docs/analytics/components/locations/configure-import-accounts).)

* **Servidores SFTP existentes (e servidores SFTP recém-atualizados)**: é necessário girar senhas antigas, conforme descrito na seção abaixo, [Girar a senha SFTP](#rotate-your-sftp-password).

  A rotação regular da senha SFTP é uma prática recomendada de segurança que ajuda a proteger seus dados.

>[!IMPORTANT]
>
>Considere as seguintes situações antes de concluir as etapas deste artigo.
>
>* **A Adobe recomenda fazer a transição para um destino de nuvem moderno, em vez de atualizar para SFTP, se possível.**
>FTP e SFTP são tipos de destino herdados. Em vez de atualizar contas FTP para SFTP e girar senhas SFTP conforme descrito neste artigo, a Adobe recomenda mudar para um tipo de destino de nuvem moderno (como Amazon S3, Google Cloud Platform ou Azure). Esses destinos em nuvem oferecem um nível mais alto de segurança. Para obter mais informações, consulte [Configurar contas de importação e exportação da nuvem](https://experienceleague.adobe.com/pt-br/docs/analytics/components/locations/configure-import-accounts).
>
>* **Se as contas FTP e SFTP forem usadas exclusivamente para Classificações, migre para os conjuntos de Classificações.**
>Se sua conta FTP ou SFTP for usada exclusivamente para Classificações, você deverá migrar do **Importador de classificações** para os **Conjuntos de classificações**, em vez de atualizar contas FTP para SFTP e girar senhas SFTP conforme descrito neste artigo. O importador de classificação será substituído e não estará mais acessível após **31 de agosto de 2026**. Para obter mais informações, consulte [Visão geral dos conjuntos de classificação](https://experienceleague.adobe.com/pt-br/docs/analytics/components/classifications/sets/overview).

## Pré-requisitos

### Inventariar suas contas FTP

Os processos descritos nesta página ao atualizar servidores FTP para usar o SFTP devem ser concluídos para cada site FTP usado para feeds de dados e Data Warehouse.

Dessa forma, você deve identificar todas as contas FTP que estão recebendo dados para feeds de dados ou Data Warehouse. Essas informações são mostradas nas configurações de FTP, conforme descrito na seção [Tipos de conta herdada](/help/components/locations/configure-import-accounts.md#configure-a-location-account) do artigo [Configurar contas de importação e exportação da nuvem](/help/components/locations/configure-import-accounts.md).

Para cada conta, reúna as seguintes informações:

* **Host**: o nome de host do servidor FTP ao qual sua conta se conecta (por exemplo, `ftp.omniture.com`, `ftp2.omniture.com` e assim por diante).

* **Porta**: ao usar um servidor SFTP hospedado pela Adobe, os clientes SFTP se conectam na porta 22. As conexões FTP não seguras usam a porta 21.

* **Nome de usuário**: o nome de usuário usado para fazer logon no servidor FTP.

* **Segredo da conta do local**: o segredo da conta atual para a conta. Esse é o segredo da conta (senha) que você usa atualmente ao baixar dados entregues no local FTP. Essas informações não estão disponíveis na interface do Adobe Analytics.

### Confirme se você pode atualizar credenciais em suas ferramentas

Atualize as senhas SFTP em qualquer ferramenta ou script usado para conexão com o site SFTP (por exemplo, um cliente SFTP, script automatizado ou plataforma de terceiros).

Todos os clientes devem se conectar via SFTP com senha como fallback.

## Atualizar servidores FTP para usar o SFTP

>[!IMPORTANT]
>
>Se os dados de FTP forem entregues a um parceiro terceirizado (por exemplo, uma empresa de consultoria ou um fornecedor de análises), fale com ele antes de seguir as etapas deste artigo.

### Etapa 1: gere as chaves SSH de sua organização para baixar dados

Esta seção descreve como gerar as chaves SSH da sua organização (um par de chaves públicas/privadas) que são usadas para **baixar dados** do servidor SFTP.

>[!NOTE]
>
>Em uma etapa futura, você baixará outra chave pública fornecida pelo Adobe. Isso faz parte de um segundo par de chaves públicas/privadas, que é usado pelo Adobe para **carregar dados** para o servidor SFTP.

Para configurar a transferência segura para baixar dados do servidor FTP:

1. Faça logon na estação de trabalho em que você baixou os dados do servidor FTP.

1. Gerar um par de chaves públicas/privadas para usar na transferência segura.

   Ao usar um servidor FTP hospedado pela Adobe, a Adobe aceita chaves RSA e ed25519.

   * **Em um ambiente Linux**: execute o seguinte comando para gerar o par de chaves ed25519:

     ```
     ssh-keygen -t ed25519 -C "your-comment-or-email"
     ```

     Se sua política não permitir que você use chaves ed25519, execute o seguinte comando para gerar o par de chaves RSA:

     ```
     ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
     ```

   * **Em um ambiente Windows**: use PuTTYgen.

1. Crie um arquivo com o nome [!DNL `authorized_keys`] (sem extensão).

1. Copie o conteúdo da chave pública no arquivo [!DNL `authorized_keys`].

1. Em uma etapa futura, você voltará a este arquivo [!DNL `authorized_keys`] para adicionar a chave pública do Adobe, que é usada pelo Adobe para carregar dados para o servidor SFTP. Em seguida, você adicionará o arquivo [!DNL `authorized_keys`] ao servidor SFTP.

### Etapa 2: criar uma nova conta de localização SFTP no Adobe Analytics

Crie uma nova conta de localização SFTP para substituir cada conta FTP existente.

Ao criar uma nova conta de localização SFTP, você deve usar o mesmo nome de host e nome de usuário usados na conta FTP existente que ela está substituindo.

>[!NOTE]
>
>Em uma etapa futura, você configurará essa nova conta de localização para ser usada como destino para seus Feeds de dados e deliveries do Data Warehouse.

#### Criar a conta SFTP

1. No Adobe Analytics, vá para [!UICONTROL **Componentes**] > [!UICONTROL **Locais**].

1. Selecione a guia [!UICONTROL **Contas de localização**].

1. Selecione [!UICONTROL **Adicionar conta**].

1. No campo suspenso [!UICONTROL **Tipo de conta**], selecione [!UICONTROL **SFTP (herdado)**].

1. Preencha os campos a seguir:

   | Nome do campo | Função |
   |---------|----------|
   | [!UICONTROL **Nome do host**] | Seu nome de host SFTP (por exemplo, `ftp.omniture.com`). |
   | [!UICONTROL **Port**] | A porta do firewall pela qual os dados serão enviados. Esta é a porta 22 para conexões SFTP hospedadas pela Adobe. |
   | [!UICONTROL **Nome de usuário**] | Seu nome de usuário SFTP. Use o mesmo nome de usuário que você usou para sua conta FTP. |

1. Selecione [!UICONTROL **Salvar**].

1. Na caixa de diálogo [!UICONTROL **Conta criada**], baixe a chave pública RSA ou ed25519 e selecione **[!UICONTROL OK]**. Essa é a chave pública SSH usada pelo Adobe para fazer upload de dados para o servidor SFTP. (Você usará essa chave na seguinte seção, [Adicionar a chave pública SSH do Adobe ao servidor SFTP](#add-adobes-ssh-public-key-to-the-sftp-server).)

1. Repita esse processo para cada conta SFTP que deseja criar.

1. Continue com a seguinte seção, [Faça upload da chave pública para o servidor SFTP](#upload-the-public-key-to-the-sftp-server).

#### Adicione a chave pública SSH do Adobe ao arquivo `authorized_keys` e carregue-a para o servidor FTP

A chave pública que você acabou de baixar na Etapa 7 da seção anterior faz parte de um par de chaves públicas/privadas usado pelo Adobe para **carregar dados** para o servidor SFTP.

Você precisa adicionar esta chave pública ao mesmo arquivo `authorized_keys` em que adicionou anteriormente a chave de download da sua organização (aquela gerada em [Etapa 1: Gerar a chave de download da sua organização e adicioná-la ao seu servidor FTP](#step-1-generate-your-organizations-download-key-and-add-it-to-your-ftp-server)).

Para adicionar a chave pública SSH do Adobe ao arquivo `authorized_keys` e carregá-la no servidor FTP:

1. Faça logon na estação de trabalho em que você baixou os dados do servidor FTP.

1. Abra o arquivo [!DNL `authorized_keys`] e adicione a chave de upload do Adobe a ele. Este arquivo já deve conter a chave de download da sua organização da [Etapa 1: gere a chave de download da sua organização e adicione-a ao seu servidor FTP](#step-1-generate-your-organizations-download-key-and-add-it-to-your-ftp-server).

1. Carregue o arquivo [!DNL `authorized_keys`] no servidor FTP:

   1. Conecte-se ao servidor FTP e faça logon com seu nome de usuário e senha.\
      Pode ser um servidor FTP hospedado pela Adobe ou seu próprio servidor FTP.
   1. Crie um diretório [!DNL .ssh] (caso ele ainda não exista).
   1. Faça upload do arquivo [!DNL `authorized_keys`] para o diretório [!DNL .ssh].

1. Atualize as configurações do firewall para permitir conexões de entrada do servidor SFTP. Ao usar um servidor SFTP hospedado pela Adobe, permita conexões de entrada de intervalos IP da Adobe na porta 22.

1. Teste a conexão fazendo logon no servidor usando o cliente SFTP.

1. Repita esse processo para cada conta SFTP criada na seção anterior, [Criar a conta SFTP](#create-the-sftp-account).

1. Continue com a seguinte seção, [Adicionar um local na conta](#add-a-location-within-the-account).

#### Adicionar uma localização na conta

1. Na guia **Locais**, selecione **Adicionar local**.

1. Especifique um nome, uma descrição e se esse local será usado com Feeds de dados ou Data Warehouse.

1. No campo [!UICONTROL **Conta de localização**], selecione a conta que acabou de criar.

1. No campo [!UICONTROL **Caminho do diretório**], especifique o caminho para o diretório no servidor SFTP. As pastas no caminho já devem existir; caso contrário, ocorrerá um erro. Por exemplo, `/folder_name/folder_name`.

1. Selecione **Salvar**.

1. Repita esse processo para cada conta SFTP criada.

Para obter instruções detalhadas, consulte [Configurar locais de importação e exportação da nuvem](https://experienceleague.adobe.com/pt-br/docs/analytics/components/locations/configure-import-locations).

### Etapa 3: Editar feeds de dados e solicitações do Data Warehouse para usar o novo destino SFTP

Atualize todas as solicitações agendadas existentes de Feeds de dados e Data Warehouse que enviem dados para destinos FTP para usar os novos destinos SFTP criados.

#### Editar feeds de dados

Edite cada feed de dados agendado que esteja configurado com o destino FTP antigo para usar o novo destino SFTP:

1. No Adobe Analytics, selecione [!UICONTROL **Administrador**] > [!UICONTROL **Feeds de dados**].

1. Localize o feed de dados que deseja editar. Para localizar um feed de dados, você pode [filtrar e pesquisar a lista de feeds de dados](#filter-and-search-the-list-of-data-feeds).

1. Selecione o feed de dados na coluna [!UICONTROL **Nome do feed**].

   A página [!UICONTROL **Editar _feed_name_**] é exibida.

1. Na seção [!UICONTROL **Destino**], no campo [!UICONTROL **Conta**], use o menu suspenso para selecionar o novo destino SFTP criado.

1. No campo [!UICONTROL **Local**], use o menu suspenso para selecionar o local na conta SFTP.

1. Selecione [!UICONTROL **Salvar**].

Para obter informações mais detalhadas, consulte [Editar um feed de dados](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed) em [Gerenciar feeds de dados](/help/export/analytics-data-feed/df-manage-feeds.md).

#### Editar solicitações do Data Warehouse

Edite cada solicitação agendada do Data Warehouse configurada com o destino FTP antigo para usar o novo destino SFTP:

1. No Adobe Analytics, selecione [!UICONTROL **Ferramentas**] > [!UICONTROL **Data Warehouse**].

1. Na página do Data Warehouse, selecione a solicitação que deseja editar.

   ![Gerenciar uma solicitação](assets/dw-manage-request.png)

1. Selecione [!UICONTROL **Editar**].

1. Selecione a guia [!UICONTROL **Destino do relatório**].

1. No campo [!UICONTROL **Conta**], use o menu suspenso para selecionar o novo destino SFTP criado.

1. No campo [!UICONTROL **Local**], use o menu suspenso para selecionar o local na conta SFTP.

1. Selecione [!UICONTROL **Salvar alterações**].

Para obter informações mais detalhadas, consulte [Editar solicitações](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests) em [Gerenciar solicitações do Data Warehouse](/help/export/data-warehouse/data-warehouse-requests-manage.md).

### Etapa 4: atualizar as configurações do firewall

Caso ainda não o tenha feito, será necessário atualizar as configurações do firewall da seguinte maneira:

* **Ao usar os servidores FTP da Adobe**: é necessário atualizar as configurações do firewall para permitir conexões de **saída** na porta 22.

* **Ao usar seu próprio servidor FTP**: é necessário atualizar as configurações do firewall para permitir a conexão de **entrada** em qualquer porta em que você estiver hospedando o serviço, que normalmente é a porta 22.

Você também deve remover regras antigas específicas de FTP, como permitir conexões de entrada na porta 21. (O FTP usa a porta 21, além de um intervalo de portas adicionais para transferência de dados. Como prática recomendada de segurança, você poderá remover esse acesso desnecessário por meio do firewall.)

### Etapa 5: certifique-se de que os feeds de dados programados e as solicitações do Data Warehouse estejam sendo entregues corretamente

Depois de atualizar cada solicitação existente do Feed de dados e do Data Warehouse para usar a nova conta e o novo local SFTP, aguarde o próximo delivery agendado. Verifique se os dados chegam ao novo destino conforme esperado.

### Etapa 6: girar a senha no servidor SFTP atualizado

Depois de atualizar um servidor FTP para SFTP, você também deve girar a senha SFTP, conforme descrito na seção a seguir, [Girar a senha SFTP](#rotate-your-sftp-password).

## Girar sua senha SFTP

Uma senha SFTP serve como um método de autenticação de fallback se a autenticação baseada em chave falhar.

Gire a senha SFTP logo após atualizar do FTP para SFTP. Ele deve continuar sendo girado regularmente, de acordo com as políticas estabelecidas.

1. Entre em contato com o Atendimento ao cliente da Adobe e solicite uma nova senha.

1. Para cada conta SFTP, forneça o **Nome do host** e o **Nome do usuário**.

   O Atendimento ao cliente gerará uma nova senha para cada conta FTP.

1. Atualize a senha em qualquer cliente que usar para se conectar ao servidor SFTP.


<!--
< **_Ignore everything after this_** >

-------

## Set up a new SFTP server or upgrade your existing FTP server

## Upgrade your FTP server to use SFTP where files are delivered or FTP account to use SFTP

Set up an SFTP server where Data Feed and Data Warehouse files can be delivered. This could beYou first need to upgrade your FTP server to use SFTP To upgrade an FTP account to use SFTP, follow the steps in [Connect to an FTP account with SFTP](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md).

## Create an SFTP account

## Rotate the passphrase on SFTP accounts


 
Adobe recommends that you periodically rotate the account secrets (passwords) on your FTP accounts that are associated with Data Feeds and Data Warehouse. 
 
Regular rotation of account secrets is a security best practice that helps protect your data. 
 
To ensure uninterrupted reception of data, follow the steps in [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets) prior to changing any account secrets.  
 
>[!IMPORTANT] 
> 
>If your FTP data is delivered to a third-party partner (for example, a consulting firm or Adobe Analytics vendor), coordinate with them before rotating account secrets. The third-party partner will need to update their own tools and scripts with the new account secrets immediately after the new account secrets are provided by your FTP host provider (either Adobe or another provider).

## When rotating account secrets is not necessary 
 
### Transition from FTP to a cloud destination 
 
FTP and SFTP are legacy destination types. Rather than rotating FTP account secrets, Adobe recommends moving to a modern cloud destination type (such as Amazon S3, Google Cloud Platform, or Azure), which provide a higher level of security. For more information, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/pt-br/docs/analytics/components/locations/configure-import-accounts). 
 
### Transition from the Classifications importer to Classification sets 
 
If your FTP account is used exclusively for Classifications, you should migrate from the **Classifications importer** to **Classification sets**, rather than rotating your FTP account secrets. The Classification importer will be deprecated and no longer accessible after **August 31, 2026**. For more information, see [Classification sets overview](https://experienceleague.adobe.com/pt-br/docs/analytics/components/classifications/sets/overview). 

## Prepare to rotate account secrets 
 
Complete the following steps before attempting to rotate FTP account secrets: 
 
### Step 1: Inventory your FTP accounts 
 
Identify all FTP accounts that are receiving data for Data Feeds or Data Warehouse. This information is shown in your FTP configuration settings, as described in the [Legacy account types](/help/components/locations/configure-import-accounts.md#configure-a-location-account) section of the article [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md). 
 
For each account, gather the following information: 
 
* **Host**: The FTP destination of the host your account connects to (for example, `ftp.omniture.com`, `ftp2.omniture.com`, and so forth). 
 
* **Port**: SFTP clients connect on port 22. FTP connections that are non-secure use port 21. 
 
* **Username**: The username used to log in to the FTP site. 
 
* **location account secret**: The current account secret for the account. This is the account secret (password) that you use currently when downloading data delivered to your FTP location. This information is not available from the Adobe Analytics interface. 
 
 
### Step 2: Confirm that you can update credentials in your tools 
 
Make sure you can update the FTP account secret in whatever tool or script you use to connect to the FTP site (for example, an FTP client, automated script, or third-party platform). 
 
### Step 3: Create FTP cloud location accounts with your current credentials 
 
Create new FTP cloud location accounts to replace your existing FTP location accounts. These new accounts will be used as the destination for your Data Feeds and Data Warehouse deliveries.  
 
When creating the new FTP accounts, you must use the same hostname, username, and account secret that are used in your existing FTP accounts. 
 
#### Create each FTP account 
 
1. In Adobe Analytics, go to **Components** > **Locations**. 
 
1. Select the **Location accounts** tab. 
 
1. Select **Add account**. 
 
1. In the **Account type** drop-down field, select **FTP (legacy)**. 
 
1. Complete the following fields: 

   | Field name | Function |
   |---------|----------|
   | **Hostname** |  Your Adobe FTP hostname (for example, `ftp.omniture.com`). | 
   | **Port** | SFTP clients connect on port 22. FTP connections that are non-secure use port 21. | 
   | **Username** | Your current FTP username. |
   | **Location account secret** | Your current FTP account secrets (password).  |
 
1. Select **Save**. 
 
Repeat this process for each FTP account. 
 
For detailed instructions, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/pt-br/docs/analytics/components/locations/configure-import-accounts). 
 
#### Add a location within the account 
 
1. On the **Locations** tab, select **Add location**. 
 
1. Specify a name, description, and whether this location will be used with Data Feeds or Data Warehouse. 
 
1. In the [!UICONTROL **Location account**] field, select the account you just created. 
 
1. In the [!UICONTROL **Directory path**] field, specify the path to the directory on the FTP server. Folders must already exist; feeds throw an error if the specified path does not exist. For example, `/folder_name/folder_name`. 
 
1. Select **Save**. 
 
Repeat this process for each location. 
 
For detailed instructions, see [Configure cloud import and export locations](https://experienceleague.adobe.com/pt-br/docs/analytics/components/locations/configure-import-locations). 
 
### Step 4: Reference the new FTP cloud accounts from any scheduled Data Feeds and Data Warehouse requests 
 
Update any existing scheduled Data Feeds and Data Warehouse requests to use the FTP cloud accounts you created.  
 
* **Data Feeds**: Go to **Admin** > **Data Feeds**, edit each scheduled  Data Feed that uses an FTP account, then change the destination to the newly created FTP cloud account. 
 
  For detailed instructions, see [Edit a data feed](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md). 
 
* **Data Warehouse**: Go to **Tools** > **Data Warehouse**, edit each scheduled Data Warehouse request that uses an FTP account, then change the report destination to the newly created FTP cloud account. 
 
  For detailed instructions, see [Edit requests](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests) in [Manage Data Warehouse requests](/help/export/data-warehouse/data-warehouse-requests-manage.md). 
 
### Step 5: Ensure that scheduled Data Feeds and Data Warehouse requests are being delivered correctly. 
 
After updating each existing Data Feed and Data Warehouse request to use the new FTP account and location, wait for the next scheduled delivery. Verify that data arrives at the new destination as expected. 

## Request a new account secret 
 
>[!IMPORTANT] 
>
>Before requesting a new account secret, consider the following:
>
>* The steps in this section apply only if you are using an Adobe-provided FTP account. For example, the FTP hostname is `ftp.omniture.com`, `ftp2.omniture.com` or similar.   If your FTP hostname is not provided by Adobe, please contact your FTP host provider for details on changing the account secret.
> 
>* Request a new account secret only after you complete all the preparation steps described in [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets). 
>
>* After Adobe Customer Care or your third-party FTP host provider provides a new account secret, the old account secret is immediately invalidated. There is no way to revert to the previous account secret. 
>
 
To request a new account secret from Adobe: 
 
1. Contact Adobe Customer Care. 
 
1. For each FTP account, provide the **Hostname** and **Username** for each account that needs a new account secret. 
 
   Customer Care will generate a new account secret for each FTP account. 

1. Continue immediately with the following section, [After you receive the new account secret](#after-you-receive-the-new-account-secret).
 
## After you receive the new account secret 
 
Act immediately after receiving the new credentials. Any delay results in failed deliveries for active Data Feeds and Data Warehouse requests. 
 
### Step 1: Update your tools and scripts 
 
Update the FTP account secret in any tool, script, or automated process that connects to the FTP account. Make sure all team members and third-party partners who access the account are notified. 
 
### Step 2: Update your cloud location accounts 
 
1. In Adobe Analytics, go to **Components** > **Locations**. 

1. Select the **Location accounts** tab. 

1. Find the FTP account that you created in Step 3 of section, [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets).

1. Select **Edit details**. 

1. Enter the new account secret and confirm it. 

1. Select **Save**. 
 
Repeat this process for each account that was reset. 

For more detailed information about this process, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/pt-br/docs/analytics/components/locations/configure-import-accounts).
 
### Step 3: Test your connections 
 
Verify that your Data Feeds or Data Warehouse requests that use the FTP account are working correctly with the new account secret. 
 
>[!TIP] 
> 
>If your current tools use SFTP with SSH keys that haven't been recently rotated, consider rotating those keys as well.

 
## Troubleshooting 
 
If something goes wrong after the account secret is rotated and you cannot restore connectivity, you can create a new FTP account. After the new account is set up, point your Data Feed or Data Warehouse request to the new account and update your cloud location accordingly. 

For information about how to create an FTP account, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/pt-br/docs/analytics/components/locations/configure-import-accounts).

To set up secure transfer with your FTP server: 

1. Generate a public/private key pair to use for secure transfer.

   This process differs depending on whether your FTP server is Adobe-hosted or self-hosted:

   +++ For an Adobe-hosted FTP server:

   Generate a public/private key pair: 
   
      * **In a Linux environment**: Run the following command to generate the ed25519 key pair: 

        ```
        ssh-keygen -t ed25519 -C "your-comment-or-email"
        ```

        If your policy does not allow you to use ed25519 keys, run the following command to generate the RSA key pair (**Note:** The RSA key typically applies to customers who operate under FIPS 186-4, as ed25519 is first supported in the newer FIPS 186-5):

        ```
        ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
        ```

      * **In a Windows environment**: Use PuTTYgen.

   +++

   +++ For a self-hosted FTP server: 
   
   If you want to set up secure transfer with your own FTP server, you must have an SFTP hostname, username, and SFTP account within Adobe Analytics that contains a valid RSA or ed25519 public key from Adobe. This key must be installed on your SFTP server. You download this public key as part of the process of [creating the SFTP account](#create-the-sftp-account).

   +++

1. Create a file named [!DNL `authorized_keys`] (no extension).



3 basic steps: Set up SFTP on customer side, then on Adobe side, then change passphrase. 

1. FTP site: ftp.omniture.com - Using username/password to connect. Adobe uses the same username/password to connect to the site.

2. user can then upload their public key to that server, then start connecting to that server with their private key using SFTP. (They also need to open Port 22 in the firewall and they would close the other ports they don't need.)

3. In Locations, create a new location, use the same username. 

4. After they create that location, we give them our public key, and they have to install it on their SFTP server.

5. Then they switch all their data feeds to use the new Location. And then we'll use SFTP to send the data. 

6. Then they call Customer Care to get new passphrase (rotate passphrase), and then they change the passphrase on their side. Passphrase is only used if SSH fails (they have the wrong keys--a bad actor could use bad keys and then use the password. But they don't have to coordinate the switching of the passphrase with installation of SFTP. )


If they're using a third-party to do this, the third-party would need to set up SFTP - This is the same as we have documented right now. It doesn't have to be immediate, though, like we were assuming before. 


If it's they're own FTP site, it would be the same. They would need to start using SFTP with their FTP server, then get our public key and install it on their server. Shouldn't matter if the FTP site is hosted by Adobe or not. 

-->

