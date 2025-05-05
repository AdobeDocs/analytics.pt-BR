---
description: Etapas que descrevem como criar uma solicitação do data warehouse.
title: Configurar um destino de relatório para uma solicitação do data warehouse
feature: Data Warehouse
exl-id: 3c7faea3-4d90-4274-88f3-e9337c94155f
source-git-commit: d213befd0fd8d530d95b8d3ac3c4f3b808558244
workflow-type: tm+mt
source-wordcount: '1970'
ht-degree: 83%

---

# Configurar um destino de relatório para uma solicitação do data warehouse

Há várias opções de configuração disponíveis ao criar uma solicitação do data warehouse. As informações a seguir descrevem como configurar um destino de relatório para a solicitação.

Para obter informações sobre como começar a criar uma solicitação, bem como links para outras opções de configuração importantes, consulte [Criar uma solicitação do data warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

>[!NOTE]
>
>Considere o seguinte ao configurar um destino de relatório:
>
>* Recomendamos o uso de uma conta na nuvem ou de um email como destino do seu relatório. [Contas de FTP e SFTP herdadas](#legacy-destinations) estão disponíveis, mas não são recomendadas.
>
>* Todas as contas em nuvem configuradas anteriormente estão disponíveis para uso no data warehouse. Você pode configurar contas em nuvem de qualquer uma das seguintes maneiras:
>
>   * Ao configurar [feeds de dados](/help/export/analytics-data-feed/create-feed.md)
>   
>   * Ao [importar dados de classificação do Adobe Analytics](/help/components/locations/locations-manager.md) (as contas podem ser usadas, mas não os locais configurados nessas contas.)
>   
>   * No gerenciador de locais, em [Componentes > Locais](/help/components/locations/configure-import-accounts.md).
>
>* As contas em nuvem estão associadas à sua conta de usuário do Adobe Analytics. Outros usuários não podem usar ou exibir contas na nuvem configuradas por você.
>
>* É possível editar qualquer local criado no gerenciador de locais em [Componentes > Locais](/help/components/locations/configure-import-accounts.md)

Configure o destino para o qual enviar os relatórios do data warehouse.

1. Caso ainda não o tenha feito, crie uma solicitação no Adobe Analytics selecionando **[!UICONTROL Ferramentas]** > **[!UICONTROL Data warehouse]** > [!UICONTROL **Adicionar**].

   Para obter detalhes adicionais, consulte [Criar uma solicitação do data warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Na página Nova solicitação do data warehouse, selecione a guia [!UICONTROL **Destino do relatório**].

   ![Guia Destino do relatório](assets/dw-report-destination.png)

1. (Condicional) Caso já tenha configurado uma conta de nuvem (e um destino nessa conta) no Adobe Analytics, ela poderá ser usada como destino do relatório:

   >[!NOTE]
   >
   >As contas estão disponíveis somente se você as tiver configurado ou se tiverem sido compartilhadas com uma organização da qual você faça parte.
   >
   >A opção [!UICONTROL **Mostrar todos os destinos**] está disponível para administradores do sistema. Habilite essa opção se desejar ter acesso a todas as contas e locais que foram criados por qualquer usuário na organização.

   1. Selecione a conta no menu suspenso [!UICONTROL **Conta**].

      Todas as contas em nuvem configuradas em qualquer uma das seguintes áreas do Adobe Analytics estão disponíveis para uso:

      * Ao importar dados de classificação do Adobe Analytics, conforme descrito em [Esquema](/help/components/classifications/sets/manage/schema.md).

        No entanto, os locais configurados para a importação de dados de classificação não podem ser usados. Em vez disso, adicione um novo destino, conforme descrito abaixo.

      * Ao configurar contas e locais na área “Locais”, conforme descrito em [Configurar contas de importação e exportação na nuvem](/help/components/locations/configure-import-accounts.md) e [Configurar locais de importação e exportação na nuvem](/help/components/locations/configure-import-locations.md).

   1. Selecione o destino associado à conta no menu suspenso [!UICONTROL **Selecionar destino**]. <!-- Is this correct? -->

1. (Condicional) Se você não tiver acesso a uma conta na nuvem já configurada no Adobe Analytics, será possível configurá-la:

   1. Selecione o menu suspenso [!UICONTROL **Conta**] e selecione [!UICONTROL **Adicionar conta**].

   1. Na caixa de diálogo Adicionar conta, especifique as seguintes informações:

      | Campo | Função |
      |---------|----------|
      | [!UICONTROL **Nome da conta de localização**] | O nome da conta de localização. Este nome aparece ao criar um local |
      | [!UICONTROL **Descrição da conta de localização**] | Forneça uma breve descrição da conta para ajudar a diferenciá-la de outras contas do mesmo tipo. |
      | [!UICONTROL **Disponibilizar a conta para todos os usuários em sua organização**] | Habilite essa opção para permitir que outros usuários em sua organização usem a conta.<p>Considere o seguinte ao compartilhar contas:</p><ul><li>As contas compartilhadas não podem ter o compartilhamento cancelado.</li><li>As contas compartilhadas podem ser editadas somente pelo proprietário da conta.</li><li>Qualquer pessoa pode criar um local para a conta compartilhada.</li></ul> |
      | [!UICONTROL **Tipo de conta**] | Selecione o tipo de conta na nuvem. Recomendamos ter uma única conta de cada tipo, com os vários locais necessários contidos nessa conta.<p>Os administradores do sistema podem limitar os tipos de conta que os usuários podem criar, conforme descrito em [Configurar se os usuários podem criar contas](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts). Se você não puder criar contas conforme descrito nesta seção, entre em contato com o administrador do sistema.</p> |

   1. Na seção [!UICONTROL **Propriedades da conta**], especifique informações específicas para o tipo de conta selecionado.

      Para obter instruções de configuração, expanda a seção abaixo que corresponde ao [!UICONTROL **Tipo de conta**] selecionado. (Tipos de conta herdada adicionais também estão disponíveis, mas não são recomendados.)

      **Tipos de conta**

      +++ARN de função do Amazon S3

      Para configurar uma conta do Amazon S3 Role ARN, especifique as seguintes informações:

      | Campo | Função |
      |---------|----------|
      | [!UICONTROL **ARN de função**] | Você deve fornecer um ARN (Amazon Resource Name) de função que a Adobe possa usar para obter acesso à conta do Amazon S3. Para fazer isso, crie uma política de permissão IAM para a conta de origem, anexe a política a um usuário e crie uma função para a conta de destino. Para obter informações específicas, consulte [esta documentação do AWS](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |

      {style="table-layout:auto"}

      +++

      +++Google Cloud Platform

      Para configurar uma conta da Google Cloud Platform, especifique as seguintes informações:

      | Campo | Função |
      |---------|----------|
      | [!UICONTROL **ID do projeto**] | Sua ID de projeto da Google Cloud. Consulte a [documentação da Google Cloud sobre como obter uma ID de projeto](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

      {style="table-layout:auto"}

      +++

      +++Azure SAS

      Para configurar uma conta do Azure SAS, especifique as seguintes informações:

      | Campo | Função |
      |---------|----------|
      | [!UICONTROL **ID do aplicativo**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações se localizam na guia **Visão geral** do aplicativo. Para obter mais informações, consulte a [documentação do Microsoft Azure sobre como registrar um aplicativo na plataforma de identidade da Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **ID do locatário**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações se localizam na guia **Visão geral** do aplicativo. Para obter mais informações, consulte a [documentação do Microsoft Azure sobre como registrar um aplicativo na plataforma de identidade da Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **URI do cofre de chaves**] | <p>O caminho para o token SAS no cofre de chaves do Azure.  Para configurar o Azure SAS, você deve armazenar um token SAS como um segredo usando o Cofre de Chaves do Azure. Para obter informações, consulte a [documentação do Microsoft Azure sobre como definir e recuperar um segredo do cofre de chaves do Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Depois que o URI do cofre de chaves for criado, adicione uma política de acesso no Cofre de Chaves para conceder permissão ao aplicativo do Azure que você criou. Para obter informações, consulte a [documentação do Microsoft Azure sobre como atribuir uma política de acesso do cofre de chaves](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p><p>Ou</p><p>Se você quiser conceder uma função de acesso diretamente sem criar uma política de acesso, consulte a [documentação do Microsoft Azure sobre como atribuir funções do Azure usando o portal do Azure](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal). Isso adiciona a atribuição de função para a ID do aplicativo acessar o URI do cofre de chaves. </p> |
      | [!UICONTROL **Nome secreto do cofre de chaves**] | O nome secreto criado ao adicionar o segredo ao Cofre de Chaves do Azure. No Microsoft Azure, essas informações estão localizadas no Cofre de Chaves que você criou, na página de configurações do **Cofre de Chaves**. Para obter informações, consulte a [documentação do Microsoft Azure sobre como definir e recuperar um segredo do cofre de chaves do Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
      | [!UICONTROL **Segredo da conta de localização**] | Copie o segredo do aplicativo do Azure que você criou. No Microsoft Azure, essas informações se localizam na guia **Certificados e segredos** do aplicativo. Para obter mais informações, consulte a [documentação do Microsoft Azure sobre como registrar um aplicativo na plataforma de identidade da Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

      +++

      +++Azure RBAC

      Para configurar uma conta do Azure RBAC, especifique as seguintes informações:

      | Campo | Função |
      |---------|----------|
      | [!UICONTROL **ID do aplicativo**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações se localizam na guia **Visão geral** do aplicativo. Para obter mais informações, consulte a [documentação do Microsoft Azure sobre como registrar um aplicativo na plataforma de identidade da Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **ID do locatário**] | Copie essa ID do aplicativo do Azure que você criou. No Microsoft Azure, essas informações se localizam na guia **Visão geral** do aplicativo. Para obter mais informações, consulte a [documentação do Microsoft Azure sobre como registrar um aplicativo na plataforma de identidade da Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
      | [!UICONTROL **Segredo da conta de localização**] | Copie o segredo do aplicativo do Azure que você criou. No Microsoft Azure, essas informações se localizam na guia **Certificados e segredos** do aplicativo. Para obter mais informações, consulte [documentação do Microsoft Azure sobre como registrar um aplicativo na plataforma de identidade da Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

      {style="table-layout:auto"}

      +++

      +++Email

      >[!NOTE]
      >
      >Contas de email podem ser usadas apenas com [Feeds de Dados](/help/export/analytics-data-feed/create-feed.md). (Contas de email sem suporte no [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) ou [Conjuntos de classificações](/help/components/classifications/sets/overview.md)).

      Para configurar uma conta do Azure RBAC, especifique as seguintes informações:

      | Campo | Função |
      |---------|----------|
      | [!UICONTROL **Destinatários**] | É possível enviar notificações por email a usuários específicos quando o relatório é enviado. Especifique um único endereço de email ou uma lista separada por vírgulas de endereços de email. |

      {style="table-layout:auto"}

      +++

1. Continue configurando sua solicitação do data warehouse na guia [!UICONTROL **Opções de relatório**]. Para obter mais informações, consulte [Configurar opções de relatório para uma solicitação do data warehouse](/help/export/data-warehouse/create-request/dw-request-report-options.md).

## Tipos de conta herdada

>[!IMPORTANT]
>
>Os destinos descritos nesta seção são herdados e não são recomendados. Em vez disso, use um dos seguintes destinos ao criar um destino do data warehouse: Amazon S3, Google Cloud Platform, Azure RBAC, Azure SAS ou Email. Consulte as informações acima para obter detalhes sobre cada um desses destinos recomendados.

As informações a seguir fornecem informações de configuração para cada um dos destinos herdados:

### FTP

Os dados do data warehouse podem ser entregues em um local FTP da Adobe ou hospedado pelo cliente. Requer um host FTP, nome de usuário e senha. Use o campo de caminho para colocar arquivos de feed em uma pasta. As pastas já devem existir; os feeds exibem um erro se o caminho especificado não existir.

Use as seguintes informações ao preencher os campos disponíveis:

#### Campos da conta

* [!UICONTROL **Nome da conta**]: o nome da conta FTP.

* [!UICONTROL **Descrição da conta**]: uma descrição da conta FTP.

* [!UICONTROL **Nome do host**]: insira o URL de destino do FTP desejado. Por exemplo, `ftp.company.com`.

  >[!NOTE]
  >
  >  Não inclua `ftp://` no início do URL.

* [!UICONTROL **Nome de usuário**]: digite o nome de usuário para fazer logon no site FTP.

* [!UICONTROL **Senha e confirmação de senha**]: digite a senha para fazer logon no site FTP.

#### Campos de local

* [!UICONTROL **Nome do local**]: o nome do local na conta FTP para o qual você deseja enviar os arquivos.

* [!UICONTROL **Descrição do local**]: uma descrição do local na conta FTP.

* [!UICONTROL **Caminho do diretório**]: o caminho para o local na conta FTP.

### SFTP

O SFTP é compatível com o data warehouse. Isso exige que um host SFTP, nome de usuário e site de destino contenham uma chave pública RSA ou DSA válida. Você pode baixar a chave pública apropriada ao criar o destino do data warehouse.

Use as seguintes informações ao preencher os campos disponíveis:

#### Campos da conta

* [!UICONTROL **Nome da conta**]: o nome da conta FTP.

* [!UICONTROL **Descrição da conta**]: uma descrição da conta FTP.

* [!UICONTROL **Nome do host**]: insira o URL de destino do SFTP desejado. Por exemplo, `sftp.company.com`.

  >[!NOTE]
  >
  >  Não inclua `sftp://` no início do URL.

* [!UICONTROL **Nome de usuário**]: digite o nome de usuário para fazer logon no site SFTP.

* [!UICONTROL **Usar extensões de arquivo temporárias durante o upload**]: quando habilitada, a extensão de arquivo `.part` é usada durante o processo de upload. Mantenha essa opção habilitada, a menos que o servidor SFTP proíba a alteração de nomes dos arquivos após a conclusão do upload.

* [!UICONTROL **Chaves públicas**]: baixe a chave pública apropriada ao criar o destino do data warehouse.

#### Campos de local

* [!UICONTROL **Nome do local**]: o nome do local na conta SFTP para o qual você deseja enviar os arquivos.

* [!UICONTROL **Descrição do local**]: uma descrição do local na conta SFTP.

* [!UICONTROL **Caminho do diretório**]: o caminho para o local na conta SFTP.

Para obter informações adicionais sobre a configuração de SFTP, consulte [Enviar solicitações do data warehouse para servidores SFTP](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md).

### S3

Você pode enviar dados do warehouse diretamente para buckets do Amazon S3. Este tipo de destino requer um nome de bucket, uma ID de chave de acesso e uma chave secreta. Consulte [Requisitos de nomenclatura de bucket do Amazon S3](https://docs.aws.amazon.com/pt_br/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) nos documentos do Amazon S3 para obter mais informações.

O usuário fornecido para fazer upload dos dados do data warehouse precisa ter as seguintes [permissões](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/API/API_Operations_Amazon_Simple_Storage_Service.html):

* s3:GetObject
* s3:PutObject
* s3:PutObjectAcl

As 16 regiões AWS padrão a seguir são compatíveis (usando o algoritmo de assinatura apropriado, quando necessário):

* us-east-2
* us-east-1
* us-west-1
* us-west-2
* ap-south-1
* ap-northeast-2
* ap-southeast-1
* ap-southeast-2
* ap-northeast-1
* ca-central-1
* eu-central-1
* eu-west-1
* eu-west-2
* eu-west-3
* eu-north-1
* sa-east-1

>[!NOTE]
>
>A região cn-north-1 não é compatível.

### Azure Blob

O data warehouse é compatível com destinos do Azure Blob. Requer um contêiner, uma conta e uma chave. A Amazon criptografa automaticamente os dados em repouso. Os dados são descriptografados automaticamente ao baixá-los. Consulte [Criar uma conta de armazenamento](https://docs.microsoft.com/pt-br/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) nos documentos do Microsoft Azure para obter mais informações.

>[!NOTE]
>
>Você deve implementar seu próprio processo para gerenciar o espaço em disco no destino do data warehouse. A Adobe não exclui dados do servidor.
