---
description: Configurar a conta de importação na nuvem e o local onde os dados de classificação podem ser carregados
keywords: Analysis Workspace
title: Configurar contas de importação e exportação na nuvem
feature: Classifications
exl-id: 40d3d3f1-1047-4c37-8caf-6b0aabaa590a
source-git-commit: 6cf277667230a56da9793deb550df1980f1d33b0
workflow-type: tm+mt
source-wordcount: '1470'
ht-degree: 56%

---

# Configurar contas de importação e exportação na nuvem

<!-- This page is almost duplicated with the "Configure cloud export locations" article in CJA. Differences are that Snowflake isn't supported here and there is a Suffix field for each account type. -->

>[!NOTE]
>
>Considere o seguinte ao criar e editar contas: <ul><li>Os administradores do sistema podem impedir que os usuários criem contas, conforme descrito em [Configurar se os usuários poderão criar contas](/help/components/locations/locations-manager.md#configure-whether-users-can-create-accounts). Se você não puder criar contas conforme descrito nesta seção, entre em contato com o administrador do sistema.</li><li>Uma conta só pode ser editada pelo usuário que a criou ou por um administrador do sistema.</li></ul>

É possível configurar uma conta na nuvem usada para qualquer uma ou todas as seguintes finalidades:

* Exportando arquivos usando [Feeds de Dados](/help/export/analytics-data-feed/create-feed.md)
* Exportando relatórios usando [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Importando esquemas usando [Conjuntos de classificações](/help/components/classifications/sets/overview.md)

Você precisa configurar o Adobe Analytics com as informações necessárias para acessar sua conta da nuvem. Esse processo consiste em adicionar e configurar a conta (como a função ARN do Amazon S3, a Plataforma da Google Cloud e assim por diante) conforme descrito neste artigo e, em seguida, adicionar e configurar o local nessa conta (como uma pasta na conta), conforme descrito em [Configurar locais de importação e exportação da nuvem](/help/components/locations/configure-import-locations.md).

Para obter informações sobre como exibir e excluir contas existentes, consulte [Gerenciador de locais](/help/components/locations/locations-manager.md).

Para configurar uma conta de importação ou exportação na nuvem:

1. No Adobe Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Locais**].
1. Na página [!UICONTROL Locais], selecione a guia [!UICONTROL **Contas de locais**].
1. (Condicional) Se você for um administrador do sistema, poderá habilitar a opção [!UICONTROL **Exibir contas para todos os usuários**] para exibir as contas criadas por todos os usuários em sua organização.
   ![exibir contas para todos os usuários](assets/accounts-all-users.png)
1. Para criar uma nova conta, selecione [!UICONTROL **Adicionar conta**].

   A caixa de diálogo [!UICONTROL **Detalhes da conta de localização**] é exibida.

   Ou

   Para editar uma conta existente, localize a conta que deseja editar e selecione o botão [!UICONTROL **Editar detalhes**].

   A caixa de diálogo [!UICONTROL **Adicionar conta**] é exibida.

1. Especifique as seguintes informações:

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
   | [!UICONTROL **URI do cofre de chaves**] | <p>O caminho para o token SAS no cofre de chaves do Azure.  Para configurar o Azure SAS, você deve armazenar um token SAS como um segredo usando o Cofre de Chaves do Azure. Para obter informações, consulte a [documentação do Microsoft Azure sobre como definir e recuperar um segredo do cofre de chaves do Azure](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Depois que o URI do cofre de chaves for criado, adicione uma política de acesso no Cofre de Chaves para conceder permissão ao aplicativo do Azure que você criou. Para obter informações, consulte a [documentação do Microsoft Azure sobre como atribuir uma política de acesso do cofre de chaves](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
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

   **Tipos de conta herdada**

   Esses tipos de contas herdadas estão disponíveis apenas ao exportar dados com [Feeds de Dados](/help/export/analytics-data-feed/create-feed.md) e [Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md). Estas opções não estão disponíveis ao importar dados com [Conjuntos de classificações](/help/components/classifications/sets/manage/schema.md).

   +++FTP

   Os dados do feed de dados podem ser entregues a um Adobe ou local FTP hospedado pelo cliente. Requer um host FTP, nome de usuário e senha. Use o campo de caminho para colocar arquivos de feed em uma pasta. As pastas já devem existir; os feeds exibem um erro se o caminho especificado não existir.

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Host**] | Insira o URL de destino FTP desejado. Por exemplo, `ftp://ftp.omniture.com`. |
   | [!UICONTROL **Caminho**] | Pode ser deixado em branco. |
   | [!UICONTROL **Nome de usuário**] | Insira o nome de usuário para fazer logon no site FTP. |
   | [!UICONTROL **Senha e senha de confirmação**] | Digite a senha para fazer logon no site FTP. |

   {style="table-layout:auto"}

+++

   +++SFTP

   O suporte SFTP para feeds de dados está disponível. Exige que um host SFTP, nome de usuário e site de destino contenham uma chave pública RSA ou DSA válida. Você pode baixar a chave pública apropriada ao criar o feed.

+++

   +++S3

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

+++

   +++Blob do Azure

   O Data Warehouse oferece suporte aos destinos do Azure Blob. Requer um contêiner, uma conta e uma chave. A Amazon criptografa automaticamente os dados em repouso. Os dados são descriptografados automaticamente ao baixá-los. Consulte [Criar uma conta de armazenamento](https://docs.microsoft.com/pt-br/azure/storage/common/storage-quickstart-create-account?tabs=azure-portal#view-and-copy-storage-access-keys) nos documentos do Microsoft Azure para obter mais informações.

   >[!NOTE]
   >
   >Você deve implementar seu próprio processo para gerenciar o espaço em disco no destino do data warehouse. A Adobe não exclui dados do servidor.

+++

1. Selecione [!UICONTROL **Salvar**].

1. Continuar com [Configurar locais de importação e exportação da nuvem](/help/components/locations/configure-import-locations.md).
