---
title: Requisitos de segurança para servidores FTP e SFTP
description: Saiba mais sobre os requisitos de segurança para servidores FTP e SFTP.
feature: Data Configuration and Collection
role: Admin
TQID: 'https://experienceleague.adobe.com/qbBCeUihfvRTQm7LvR8jylRWf8rRlzFoZfs62l0fito'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 1933
ht-degree: 100%

---

# Requisitos de segurança para servidores FTP e SFTP

Esta página aborda os requisitos de segurança para servidores FTP e SFTP existentes que recebem dados fornecidos pelos feeds de dados do Adobe Analytics ou pelo Data Warehouse.

* **Servidores FTP existentes**: devem ser atualizados para usar SFTP, conforme descrito na seção abaixo, [Atualizar servidores FTP para usar SFTP](#upgrade-ftp-servers-to-use-sftp).

  A atualização de FTP para SFTP é um requisito, pois o SFTP permite maior segurança.

  Como alternativa, para um nível mais alto de segurança, é possível fazer a transição para um destino na nuvem moderno. (Para mais informações, consulte [Configurar contas de importação e exportação na nuvem](https://experienceleague.adobe.com/pt-br/docs/analytics/components/locations/configure-import-accounts).)

* **Servidores SFTP existentes (e servidores SFTP recém-atualizados)**: é necessário substituir senhas antigas, conforme descrito na seção abaixo, [Rotacione a senha SFTP](#rotate-your-sftp-password).

  A rotação regular da senha SFTP é uma prática recomendada de segurança que ajuda a proteger os dados.

>[!IMPORTANT]
>
>Considere as seguintes situações antes de concluir as etapas deste artigo.
>
>* **A Adobe recomenda a transição para um destino na nuvem moderno, em vez de atualizar para SFTP, se possível.**
>FTP e SFTP são tipos de destino herdados. Em vez de atualizar contas FTP para SFTP e rotacionar senhas SFTP conforme descrito neste artigo, a Adobe recomenda mudar para um tipo de destino na nuvem moderno (como Amazon S3, Google Cloud Platform ou Azure). Esses destinos na nuvem oferecem um nível mais alto de segurança. Para mais informações, consulte [Configurar contas de importação e exportação na nuvem](https://experienceleague.adobe.com/pt-br/docs/analytics/components/locations/configure-import-accounts).
>
>* **Se as contas FTP e SFTP forem usadas exclusivamente para Classificações, migre para os conjuntos de Classificações.**
>Se a conta FTP ou SFTP for usada exclusivamente para Classificações, migre de **Importador de classificações** para os **Conjuntos de classificações**, em vez de atualizar contas FTP para SFTP e rotacionar senhas SFTP conforme descrito neste artigo. O Importador de classificações estará obsoleto e não mais acessível após **31 de agosto de 2026**. Para mais informações, consulte [Visão geral dos Conjuntos de classificação](https://experienceleague.adobe.com/pt-br/docs/analytics/components/classifications/sets/overview).

## Pré-requisitos

### Inventariar contas FTP

É necessário concluir as etapas de atualização do SFTP nesta página para cada site FTP usado com os feeds de dados ou o Data Warehouse.

Dessa forma, todas as contas FTP que estão recebendo dados para os feeds de dados ou o Data Warehouse devem ser identificadas. Essas informações são exibidas nas configurações de FTP, conforme descrito na seção [Tipos de conta herdada](/help/components/locations/configure-import-accounts.md#configure-a-location-account) do artigo [Configurar contas de importação e exportação na nuvem](/help/components/locations/configure-import-accounts.md).

Para cada conta, reúna as seguintes informações:

* **Host**: o nome de host do servidor FTP ao qual a conta se conecta (por exemplo, `ftp.omniture.com`, `ftp2.omniture.com` e assim por diante).

* **Porta**: ao usar um servidor SFTP hospedado pela Adobe, os clientes SFTP se conectam na porta 22. As conexões FTP não seguras usam a porta 21.

* **Nome de usuário**: o nome de usuário usado para fazer logon no servidor FTP.

* **Segredo da conta de localização**: o segredo da conta atual. Esse é o segredo da conta (senha) usada atualmente ao baixar dados entregues no local FTP. Essas informações não estão disponíveis na interface do Adobe Analytics.

### Confirme se é possível atualizar credenciais nas ferramentas

Certifique-se de que pode atualizar as senhas SFTP em qualquer ferramenta ou script usado para conexão com o site SFTP (por exemplo, um cliente SFTP, script automatizado ou plataforma de terceiros).

Todos os clientes devem se conectar via SFTP com senha como fallback.

## Atualizar servidores FTP para usar o SFTP

>[!IMPORTANT]
>
>Se os dados FTP são entregues a um parceiro terceirizado (por exemplo, uma empresa de consultoria ou um fornecedor de análises), fale com ele antes de seguir as etapas deste artigo.

### Etapa 1: gere as chaves SSH da organização para baixar dados

Esta seção descreve como gerar as chaves SSH da organização (um par de chaves públicas/privadas) que são usadas para **baixar dados** do servidor SFTP.

>[!NOTE]
>
>Em uma etapa futura, você baixará outra chave pública fornecida pela Adobe. Isso faz parte de um segundo par de chaves públicas/privadas, que é usado pela Adobe para **fazer upload de dados** para o servidor SFTP.

Para configurar a transferência segura no download de dados do servidor FTP:

1. Faça login na estação de trabalho em que você baixou os dados do servidor FTP.

1. Gere um par de chaves públicas/privadas para usar na transferência segura.

   Ao usar um servidor SFTP hospedado pela Adobe, a Adobe oferece suporte a chaves RSA e ed25519.

   * **Em um ambiente Linux**: execute o seguinte comando para gerar o par de chaves ed25519:

     ```
     ssh-keygen -t ed25519 -C "your-comment-or-email"
     ```

     Se sua política não permitir o uso de chaves ed25519, execute o seguinte comando para gerar o par de chaves RSA:

     ```
     ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
     ```

   * **Em um ambiente Windows**: use PuTTYgen.

1. Crie um arquivo com o nome [!DNL `authorized_keys`] (sem extensão).

1. Copie o conteúdo da chave pública para o arquivo [!DNL `authorized_keys`].

1. Em uma etapa futura, você voltará a este arquivo [!DNL `authorized_keys`] para adicionar a chave pública da Adobe, que é usada pela Adobe para fazer upload de dados para o servidor SFTP. Em seguida, você adicionará o arquivo [!DNL `authorized_keys`] ao servidor SFTP.

### Etapa 2: criar uma nova conta de localização SFTP no Adobe Analytics

Crie uma nova conta de localização SFTP para substituir cada conta FTP existente.

Ao criar uma nova conta de localização SFTP, você deve usar o mesmo nome de host e nome de usuário usados na conta FTP que ela está substituindo.

>[!NOTE]
>
>Em uma etapa futura, você configurará essa nova conta de localização para ser usada como destino para seus Feeds de dados e entregas do Data Warehouse.

#### Criar a conta SFTP

1. No Adobe Analytics, acesse [!UICONTROL **Componentes**] > [!UICONTROL **Localizações**].

1. Selecione a guia [!UICONTROL **Contas de localização**].

1. Selecione [!UICONTROL **Adicionar conta**].

1. No menu suspenso [!UICONTROL **Tipo de conta**], selecione [!UICONTROL **SFTP (legado)**].

1. Preencha os campos a seguir:

   | Nome do campo | Função |
   |---------|----------|
   | [!UICONTROL **Nome do host**] | Nome do host SFTP (por exemplo, `ftp.omniture.com`). |
   | [!UICONTROL **Port**] | A porta do firewall pela qual os dados são enviados. Esta é a porta 22 para conexões SFTP hospedadas pela Adobe. |
   | [!UICONTROL **Nome de usuário**] | O nome de usuário SFTP. Use o mesmo nome de usuário que você usou para a conta FTP. |

1. Selecione [!UICONTROL **Salvar**].

1. Na caixa de diálogo [!UICONTROL **Conta criada**], baixe a chave pública RSA ou ed25519 e clique em [!UICONTROL **OK**]. Essa é a chave pública SSH usada pela Adobe para fazer upload de dados para o servidor SFTP. (Você usará essa chave na seguinte seção, [Adicionar a chave pública SSH da Adobe ao servidor SFTP](#add-adobes-ssh-public-key-to-the-sftp-server).)

1. Repita esse processo para cada conta SFTP que deseja criar.

1. Continue com a seguinte seção, [Fazer upload da chave pública para o servidor SFTP](#upload-the-public-key-to-the-sftp-server).

#### Adicione a chave pública SSH da Adobe ao arquivo [!DNL `authorized_keys`] e carregue-a para o servidor FTP

A chave pública que você acabou de baixar na Etapa 7 da seção anterior faz parte de um par de chaves públicas/privadas usado pela Adobe para **fazer upload de dados** para o servidor SFTP.

Você precisa adicionar esta chave pública ao mesmo arquivo [!DNL `authorized_keys`] em que adicionou anteriormente a chave de download da sua organização (aquela que você gerou na [Etapa 1: Gerar as chaves SSH da sua organização para baixar dados](#step-1-generate-your-organizations-ssh-keys-for-downloading-data)).

Para adicionar a chave pública SSH da Adobe ao arquivo [!DNL `authorized_keys`] e carregá-la no servidor FTP:

1. Faça login na estação de trabalho em que você baixou os dados do servidor FTP.

1. Abra o arquivo [!DNL `authorized_keys`] e adicione a chave de upload da Adobe a ele. Este arquivo já deve conter a chave de download da sua organização da [Etapa 1: gerar as chaves SSH da sua organização para baixar dados](#step-1-generate-your-organizations-ssh-keys-for-downloading-data).

1. Faça o upload do arquivo [!DNL `authorized_keys`] para o servidor FTP:

   1. Conecte-se ao servidor FTP e faça logon com seu nome de usuário e senha.
Pode ser um servidor FTP hospedado pela Adobe ou seu próprio servidor FTP.
   1. Crie um diretório [!DNL .ssh] (caso ele ainda não exista).
   1. Faça upload do arquivo [!DNL `authorized_keys`] para o diretório [!DNL .ssh].

1. Atualize as configurações do firewall para permitir conexões de entrada do servidor SFTP. Ao usar um servidor SFTP hospedado pela Adobe, permita conexões de entrada de intervalos IP da Adobe na porta 22.

1. Teste a conexão fazendo logon no servidor usando o cliente SFTP.

1. Repita esse processo para cada conta SFTP criada na seção anterior, [Criar a conta SFTP](#create-the-sftp-account).

1. Continue com a seguinte seção, [Adicionar uma localização na conta](#add-a-location-within-the-account).

#### Adicionar uma localização na conta

1. Na guia [!UICONTROL **Localizações**], selecione [!UICONTROL **Adicionar localização**].

1. Especifique um nome, uma descrição e se essa localização será usada com Feeds de dados ou Data Warehouse.

1. No campo [!UICONTROL **Conta de localização**], selecione a conta que acabou de criar.

1. No campo [!UICONTROL **Caminho do diretório**], especifique o caminho para o diretório no servidor SFTP. As pastas no caminho já devem existir; caso contrário, ocorre um erro. Por exemplo, `/folder_name/folder_name`.

1. Selecione [!UICONTROL **Salvar**].

1. Repita esse processo para cada conta SFTP criada.

Para obter instruções detalhadas, consulte [Configurar locais de importação e exportação na nuvem](https://experienceleague.adobe.com/pt-br/docs/analytics/components/locations/configure-import-locations).

### Etapa 3: editar Feeds de dados e solicitações do Data Warehouse para usar o novo destino SFTP

Atualize todas as solicitações agendadas existentes de Feeds de dados e Data Warehouse que enviam dados para destinos FTP para usar os novos destinos SFTP criados.

#### Editar feeds de dados

Edite cada feed de dados agendado que esteja configurado com o destino FTP antigo para usar o novo destino SFTP:

1. No Adobe Analytics, selecione [!UICONTROL **Administrador**] > [!UICONTROL **Feeds de dados**].

1. Localize o feed de dados que deseja editar. Para localizar um feed de dados, você pode [filtrar e pesquisar a lista de feeds de dados](#filter-and-search-the-list-of-data-feeds).

1. Selecione o feed de dados na coluna [!UICONTROL **Nome do feed**].

   A página [!UICONTROL **Editar _feed_name_**] é exibida.

1. Na seção [!UICONTROL **Destino**], no campo [!UICONTROL **Conta**], use o menu suspenso para selecionar o novo destino SFTP que você criou.

1. No campo [!UICONTROL **Localização**], use o menu suspenso para selecionar a localização na conta SFTP.

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

1. No campo [!UICONTROL **Localização**], use o menu suspenso para selecionar a localização na conta SFTP.

1. Selecione [!UICONTROL **Salvar alterações**].

Para obter informações mais detalhadas, consulte [Editar solicitações](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests) em [Gerenciar solicitações do Data Warehouse](/help/export/data-warehouse/data-warehouse-requests-manage.md).

### Etapa 4: atualizar as configurações do firewall

Caso ainda não o tenha feito, será necessário atualizar as configurações do firewall da seguinte maneira:

* **Ao usar os servidores FTP da Adobe**: é necessário atualizar as configurações do firewall para permitir conexões de **saída** na porta 22.

* **Ao usar seu próprio servidor FTP**: é necessário atualizar as configurações do firewall para permitir a conexão de **entrada** em qualquer porta em que você estiver hospedando o serviço, que normalmente é a porta 22.

Você também deve remover regras antigas específicas de FTP, como permitir conexões de entrada na porta 21. (O FTP usa a porta 21, além de um intervalo de portas adicionais para transferência de dados. Como prática recomendada de segurança, você pode remover esse acesso desnecessário por meio do firewall.)

### Etapa 5: verifique se os feeds de dados programados e as solicitações do Data Warehouse estão sendo entregues corretamente

Depois de atualizar cada solicitação existente do Feed de dados e do Data Warehouse para usar a nova conta e o novo local SFTP, aguarde a próxima entrega agendada. Verifique se os dados chegam ao novo destino conforme esperado.

### Etapa 6: girar a senha no servidor SFTP atualizado

Depois de atualizar um servidor FTP para SFTP, você também deve girar a senha SFTP, conforme descrito na seção a seguir, [Girar a senha SFTP](#rotate-your-sftp-password).

## Girar a senha do SFTP

Uma senha SFTP serve como um método de autenticação de fallback se a autenticação baseada em chave falhar.

Gire a senha do SFTP logo após atualizar do FTP para o SFTP. Ela deve continuar sendo girada regularmente, de acordo com as políticas estabelecidas.

1. Entre em contato com o Atendimento ao cliente da Adobe e solicite uma nova senha.

1. Para cada conta SFTP, forneça o **Nome do host** e o **Nome do usuário**.

   O Atendimento ao cliente gera uma nova senha para cada conta FTP.

1. Atualize a senha em qualquer cliente que usar para se conectar ao servidor SFTP.


